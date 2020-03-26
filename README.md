# Infraestrutura Kubernetes 

# Downloads 
Baixar kubernetes e MiniKube

# Crie um Diretorio na sua pasta raiz chamada Kubernets
mkdir .../kubernetes
touch aplicacao.yml

# Criando o arquivo aplicacao.yml

    apiVersion: v1
    kind: Pod // Criando o container
      name: aplicacao-noticias // Nome do Container
    spec: // especificando o seu conteiners 
      containers:
          -name: container-aplicacao
          image: image/teste
          ports:
            ContainerPort:80
            
 
# Criando o arquivo deployment-aplicacao.yml (Monitorar o pod)
    apiVersion: v1
     kind: deployment
     metedata:
        name: aplicacao-noticias-deployment
      spec:
        selector:
            matchLabels
                name: aplicacao-noticias-pod
      template:
          metadata:
              Labels
                name: aplicacao-noticias-pod
          containers:
              -name: container-aplicacao
               image: image/teste
               ports:
                  ContainerPort:80
            
         
    
# Criando seu primeiro Pods
navegue ate .../kubernetes/
$ kubectl create -f aplicacao.yml (vai criar um container)
$ kubectl get pods (Ver os pods que estão rodando)
$ kubectl describe pods (mostra todos os pods que estão rodando)

# Criando seu primeiro Monitorador Pods

navegue ate .../kubernetes/
$ kubectl create -f deployment-aplicacao.yml (vai criar um container)
$ kubectl get pods (Ver os pods que estão rodando)
$ kubectl describe pods (mostra todos os pods que estão rodando)

$kubectl get pod




# Arquitetura Kubernetes


![Murilo](https://i.snipboard.io/hqsjYO.jpg)

# Serviço LoadBalancer
![Murilo](https://snipboard.io/LPMz42.jpg)

## Criando o arquivo service-aplicacao-noticias.yml (Serviço LoadBalancer)
![Murilo](https://i.snipboard.io/fMSu7K.jpg)


            apiVersion: apps/v1beta1
            kind: Deployment
                metadata:
                    name: nginx-deployment
            spec:
               template:
                    metadata:
                        labels:
                            name: nginx
             spec:
                replicas: 3
                containers:
        -           name: container-kubernetes
                       image: nginx


# Comandos Mais Utilizados

## para listar os pods
    kubectl get pods

## tbm funcionar para deployments e services, por exemplo:
    kubectl get services

## para detalhes de um pod
    kubectl describe pod <nome-pod>

## o comando describe tbm funciona para deployment e service, por exemplo:
    kubectl describe service <nome>

## para criar pod, deployment ou service a partir de um arquivo yml
    kubectl create -f <nome-arquivo-yml>

## para remover pod, deployment ou service a partir de um arquivo yml
    kubectl delete -f <nome-arquivo-yml>

## para remover um pod
    kubectl delete pod <nome-pod>

## para remover um deployment
    kubectl delete deployment <nome-deployment>

## para remover um service
      kubectl delete service <nome-service>
    
## para pedir um URL de acesso

    minikube service servico-aplicacao-sistema --url
    
# Parametrização de CPU e memória de cada Pod

a configuração para tal é feita no container através de um elemento resources onde podemos especificar requests e limits
requests é o valor o container está garantido de ter


limits é o máximo permitido o que o container terá disponível

    resources:
    requests:
    memory: "16Mi"
    cpu: "100m"
    limits:
    memory: "32Mi"
    cpu: "200m"




