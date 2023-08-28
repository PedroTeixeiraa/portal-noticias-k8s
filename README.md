# Projeto de Estudo de K8S - Portal de Notícias

Este é o repositório do meu projeto pessoal de estudo inicial sobre Kubernetes, focado na criação de um portal de notícias. Neste projeto, estou explorando os conceitos fundamentais do Kubernetes, como a configuração de serviços, pods e o uso de ConfigMaps.

![foto1](https://github.com/PedroTeixeiraa/portal-noticias-k8s/assets/54821438/b1223820-c91e-46bd-b6a4-0d9a786eb8a2)
![foto2](https://github.com/PedroTeixeiraa/portal-noticias-k8s/assets/54821438/b567771f-7dbb-47ee-b894-04a0f4660787)

## Estrutura do Projeto
O projeto é composto por três principais componentes: o banco de dados, o portal de notícias e o sistema de gerenciamento. Cada componente é implementado usando serviços, pods e ConfigMaps, demonstrando diferentes aspectos do Kubernetes.
![foto3](https://github.com/PedroTeixeiraa/portal-noticias-k8s/assets/54821438/f19d09ca-2bbb-4920-b891-793bf423ae4e)
### Banco de Dados (db)

- `configmap.yaml`: Configura as chaves do banco de dados usando um ConfigMap.
- `pod.yaml`: Define o Pod responsável pelo banco de dados.
- `service.yaml`: Cria um Service do tipo ClusterIP para o banco de dados.

### Portal de Notícias (portal)

- `configmap.yaml`: Configura qualquer configuração específica do portal usando um ConfigMap.
- `pod.yaml`: Define o Pod que lida com a exibição de notícias.
- `service.yaml`: Cria um Service do tipo NodePort para o portal de notícias.

### Sistema de Gerenciamento (sistema)

- `configmap.yaml`: Configura as configurações do sistema usando um ConfigMap.
- `pod.yaml`: Define o Pod responsável pela funcionalidade de gerenciamento.
- `service.yaml`: Cria um Service do tipo NodePort para o sistema de gerenciamento.

## Conceitos Explorados

Durante o desenvolvimento deste projeto, explorei os seguintes conceitos do Kubernetes:

- Criação de Services para expor Pods para dentro e fora do cluster.
- Utilização de diferentes tipos de Services: ClusterIP para acesso interno e NodePort para acesso externo.
- Implantação de Pods para executar as diferentes partes do sistema.
- Uso de ConfigMaps para injetar configurações nos Pods.

## Como Executar o Projeto

Para executar este projeto em seu ambiente local, siga estas etapas:

### Pré-requisitos

Certifique-se de ter as seguintes ferramentas instaladas:

- [Minikube](https://minikube.sigs.k8s.io/docs/start/): Uma ferramenta para executar um cluster Kubernetes localmente.
- [kubectl](https://kubernetes.io/docs/tasks/tools/): A interface de linha de comando para interagir com clusters Kubernetes.

### Passos

1. Inicie o cluster Minikube usando o seguinte comando:

   ```bash
   minikube start
   ```
2. Aplique as definições de recursos YAML para configurar os componentes do projeto:
    ```bash
    kubectl apply -f db/configmap.yaml
    kubectl apply -f db/pod.yaml
    kubectl apply -f db/service.yaml

    kubectl apply -f portal/configmap.yaml
    kubectl apply -f portal/pod.yaml
    kubectl apply -f portal/service.yaml

    kubectl apply -f sistema/configmap.yaml
    kubectl apply -f sistema/pod.yaml
    kubectl apply -f sistema/service.yaml
    ```
3. Verifique o status dos Pods usando o seguinte comando:
   ```bash
   kubectl get pods
   ```

4. Obtenha o IP para acessar o portal de notícias e o sistema de gerenciamento:
    ```bash
    kubectl get nodes -o wide
    portal de noticias - http://[INTERNAL_IP]:30000
    sistema de gerenciamento - http://[INTERNAL_IP]:30001
    ```

5. Observação: Para encerrar o cluster Minikube, execute o seguinte comando:
    ```bash
      minikube stop
    ```

## Contribuição

Contribuições são bem-vindas! Se você quiser colaborar com melhorias, correções de bugs ou adição de novos recursos, fique à vontade para abrir issues ou enviar pull requests.

## Licença

Este projeto é licenciado sob a Licença MIT. Consulte o arquivo [LICENSE](https://github.com/PedroTeixeiraa/portal-noticias-k8s/blob/master/LICENSE) para mais detalhes.

## Contato

Se você tiver alguma dúvida ou precisar de suporte, sinta-se à vontade para entrar em contato via email: pedroteixeiraalves007@gmail.com.
    