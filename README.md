# my-simple-pipeline
developer productivity by implementing the right CI/CD strategy for your business


# Prompt die KUBECONFIG weergeeft als deze gezet is

prompt() {
   if [ ! -z $KUBECONFIG ]; 
      then PS1="[$(basename ${KUBECONFIG}) \w]\$ ";
      else PS1="[\u@\h \W]\$ "
   fi 
}
PROMPT_COMMAND=prompt 

[ -f ~/.kubectl_aliases ] && source ~/.kubectl_aliases
function kubectl() { echo "+ kubectl $@">&2; command kubectl $@; }

alias setminikube='export KUBECONFIG=~/.kube/minikubeconfig'
alias setdev='export KUBECONFIG=~/.kube/lpc-dev-config.yaml'
alias setcicd='export KUBECONFIG=~/.kube/lpc-cicd-config.yaml'
alias setot1='export KUBECONFIG=~/.kube/lpc-ot1-config.yaml'
alias setot2='export KUBECONFIG=~/.kube/lpc-ot2-config.yaml'
alias setoff='export KUBECONFIG=""'

source <(kubectl completion bash)
Een voorbeeld .bashrc zodat je met een alias kan schakelen naar het juiste cluster en in je promt ziet met welk cluster je verbonden bent.
