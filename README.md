# k8s-datadog-agent

1- Instalar o Kind
2- Construir a imagem docker das aplicações
3- Adicionar a imagem localmente no cluster através do  minikube image load python-flask
4- instalar o agente datadog com Helm no cluster (https://docs.datadoghq.com/containers/kubernetes/installation/?tab=helm)
    helm install datadog-agent -f datadog-values.yaml datadog/datadog -n datadog
    Dificuldade para instalar o agente datadog, ele está dando esse erro ao iniciar o pod do agente: (pkg/runtime/runtime.go:36 in SetMaxProcs) | runtime: error auto-setting maxprocs: path "/kubelet.slice/kubelet-kubepods.slice/kubelet-kubepods-besteffort.slice/kubelet-kubepods-besteffort-podf6ec7293_3d26_407f_8861_8593e009f36e.slice/cri-containerd-d5a41c7c2ea9956c57b5c72dc267b1dae12f3dfc5e36021dffd3dd8082f59571.scope" is not a descendant of mount point root "/kubelet" and cannot be exposed from "/host/sys/fs/cgroup/cpuset/kubelet"

    Problema de erro com o cgroups


