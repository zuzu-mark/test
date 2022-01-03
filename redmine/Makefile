
SVC:=redmine
PORT:=9081
SUBDIR:=

get:
	kubectl get po,svc,ingress -A
ex:
	kubectl port-forward service/$(SVC)-svc $(PORT) &
kill:
	ps axu | grep port-for | grep $(PORT) | awk '{print $$2}' | xargs kill 2>/dev/null || true
ps:
	ps axu | grep port-for | grep $(PORT) | grep -v grep
cur:
	curl localhost:$(PORT)/$(SUBDIR)



dep:
	kubectl get po -A | grep mysql | grep Running
del:
	-kubectl delete -f main.yml
add: del dep
	#sudo cp $$(pwd)/../minikube_dir/$(SVC)/
	-kubectl apply -f main.yml


## shared-only
DST:=$$(pwd)/../minikube_dir
DIR1:=files
DIR2:=plugins
DIR3:=themes
DIR:=$(DST)/$(SVC)/$(DIR1)
DIR+=$(DST)/$(SVC)/$(DIR2)
DIR+=$(DST)/$(SVC)/$(DIR3)

define F
   sudo rm -frd $(1)
   sudo mkdir -p $(1)
   sudo chmod -R 777 $(1)
#sudo cp -rf $$(pwd)/../$(DIR2)/* $(DST)/$(DIR1)/

endef

xs := $(DIR)
init:
	  $(foreach x,$(xs),$(call F,$(x)))
		sudo cp config.ru $$(pwd)/../minikube_dir/redmine/plugins/
