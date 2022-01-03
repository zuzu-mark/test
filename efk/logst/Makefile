all:
	kubectl get po,svc,pv,cm -n kube-logging
d:
	kubectl apply -k .
dd:
	kubectl delete -k .

p:
	kubectl port-forward svc/kibana 5601:5601 -n kube-logging &

ps:
	ps axu | grep kubectl | grep port-f

