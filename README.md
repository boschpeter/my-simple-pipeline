# my-simple-pipeline
developer productivity by implementing the right CI/CD strategy for your business

Kubernetes verovert de wereld van de app-ontwikkeling razendsnel. Tegen 2022 zal meer dan 75% van de wereldwijde organisaties containertoepassingen in productie hebben.

De basisprincipes van Kubernetes en praktische ervaring met de verschillende componenten, mogelijkheden en oplossingen, waaronder Azure Kubernetes Service. 
Ga van nul naar ... met Kubernetes om uw bedrijf klaar te stomen voor toekomstig succes van app-ontwikkeling


# Prompt die KUBECONFIG weergeeft als deze gezet is.  Geerten Schram

[Setting up a Kubernetes build pipeline](https://www.youtube.com/watch?v=5irsAdKoEBU&list=PLLasX02E8BPCrIhFrc_ZiINhbRkYMKdPT&index=6)


````

Een voorbeeld .bashrc zodat je met een alias kan schakelen naar het juiste cluster en in je promt ziet met welk cluster je verbonden bent.


prompt() {
   if [ ! -z $KUBECONFIG ]; 
      then PS1="[$(basename ${KUBECONFIG}) \w]\$ ";
      else PS1="[\u@\h \W]\$ "
   fi 
}
PROMPT_COMMAND=prompt [ -f ~/.kubectl_aliases ] && source ~/.kubectl_aliases

function kubectl() { echo "+ kubectl $@">&2; command kubectl $@; }

alias setminikube='export KUBECONFIG=~/.kube/minikubeconfig'
alias setdev='export KUBECONFIG=~/.kube/lpc-dev-config.yaml'
alias setcicd='export KUBECONFIG=~/.kube/lpc-cicd-config.yaml'
alias setot1='export KUBECONFIG=~/.kube/lpc-ot1-config.yaml'
alias setot2='export KUBECONFIG=~/.kube/lpc-ot2-config.yaml'
alias setoff='export KUBECONFIG=""'

source <(kubectl completion bash)
````


Why you should care about containers
https://www.youtube.com/watch?v=EUitQ8DaZW8&list=PLLasX02E8BPCrIhFrc_ZiINhbRkYMKdPT
Understand how containers provide a lightweight immutable infrastructure for application deployment and more 
efficient utilization of underlying resources in this video of why containers matter. 

How Kubernetes works
https://www.youtube.com/watch?v=daVUONZqn88&list=PLLasX02E8BPCrIhFrc_ZiINhbRkYMKdPT&index=2  
Learn about the key concepts in Kubernetes, including pod, deployment, replica set, scheduler and load balancer. 


Setting up a Kubernetes build pipeline
https://www.youtube.com/watch?v=5irsAdKoEBU&list=PLLasX02E8BPCrIhFrc_ZiINhbRkYMKdPT&index=6
Learn how security and associated checks and balances play a key role in setting up a Kubernetes build pipeline
