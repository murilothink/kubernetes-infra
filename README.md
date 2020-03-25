# Kubernetes_Command

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


# Comandos Mais Utilizados

$ kubectl get nodes (Por exemplo, você pode listar os nodes do seu cluster usando:)


$kubectl explain node (Caso queira entender melhor aquele recurso, use o comando explain:)

$kubectl get pods     





## Informações sobre os pods, service, deployments etc recebemos pelo comando kubectl get ..., por exemplo


$kubectl get deployments


$kubectl get services

e

$kubectl get pod <nome-do-pod>
  
  
$kubectl get deployment <nome-do-deployment>
  
  
$kubectl get service <nome-do-service>
  
  
$kubectl logs <nome-pod-name> (Por fim, podemos ver os logs de um Pod com o comando.)
  
  
$kubectl delete pods <nome do pods>
    
    
    
    
    




