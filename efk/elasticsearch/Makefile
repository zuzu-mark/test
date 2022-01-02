all:
	kubectl get po,svc,pv,cm -n kube-logging
ns:
	kubectl create ns kube-logging
d:
	kubectl apply -k .
dd:
	kubectl delete -k .
c:
	kubectl exec -it elasticsearch-0 -n kube-logging -- bin/elasticsearch-setup-passwords auto -b

p:
	kubectl port-forward statefulsets/elasticsearch 9200:9200 -n kube-logging &

ps:
	ps axu | grep kubectl | grep port-f

cl:
	curl http://elastic:L3ZhHsoO5TpNUEUJ0E3k@localhost:9200


