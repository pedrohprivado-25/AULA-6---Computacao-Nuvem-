# Aula 6 – Computação em Nuvem
## Configuração e Armazenamento Persistente

### Introdução

Nesta aula, aprendemos um pouco mais sobre como funciona o armazenamento de dados e as configurações dentro do Kubernetes. Também vimos a importância de não depender somente dos arquivos que ficam dentro de um Pod, pois ele pode ser excluído ou substituído durante o funcionamento de uma aplicação.

Durante a explicação da professora, estudamos alguns recursos que ajudam a manter as configurações organizadas e os dados salvos, mesmo quando precisamos criar outro Pod.

### O que vimos na aula?

Durante o conteúdo teórico, estudamos os seguintes assuntos:

- **ConfigMap:** aprendemos que ele serve para guardar configurações e informações que podem ser utilizadas pelos containers, sem precisar alterar a imagem da aplicação.
- **Volumes:** vimos como podemos disponibilizar um espaço para guardar arquivos e acessar esses dados dentro de um container.
- **PersistentVolume (PV):** entendemos que representa um espaço de armazenamento disponível no Kubernetes.
- **PersistentVolumeClaim (PVC):** aprendemos que funciona como uma solicitação para utilizar um espaço de armazenamento.
- **Persistência de dados:** vimos por que é importante manter os arquivos salvos mesmo quando um Pod é excluído ou substituído.
- **Stateless e Stateful:** conhecemos a diferença entre aplicações que não precisam guardar informações entre as requisições e aquelas que precisam manter seus dados.

### O que fizemos nas aulas práticas?

Durante a prática, utilizamos o Kubernetes Playground pelo Killercoda para realizar algumas configurações e testar o funcionamento dos recursos estudados.

**1. Criando um ConfigMap e utilizando o Nginx**

Começamos verificando os Nodes do ambiente e depois criamos um ConfigMap com uma página HTML.

Em seguida, criamos um Pod utilizando o Nginx e conectamos o ConfigMap a ele. Depois fizemos um teste para verificar se a página estava sendo carregada corretamente.

Com isso, conseguimos entender como podemos deixar as configurações separadas da aplicação.

**2. Configurando o armazenamento persistente**

Depois trabalhamos com o armazenamento de dados. Criamos um PersistentVolume (PV) com capacidade de 100Mi e um PersistentVolumeClaim (PVC) solicitando 50Mi.

Após isso, criamos um Pod utilizando a imagem BusyBox e conectamos o armazenamento através do PVC, deixando os arquivos disponíveis dentro da pasta `/dados`.

**3. Testando a persistência dos dados**

Nessa parte, tentamos criar um arquivo chamado `mensagem.txt`, mas tivemos um erro no comando de gravação e não conseguimos concluir esse primeiro teste.

Mesmo assim, continuamos a atividade e criamos outro Pod para verificar o armazenamento.

**4. Realizando o desafio prático**

No desafio, conseguimos realizar o teste de persistência com sucesso.

Criamos um arquivo chamado `grupo.txt` dentro do Pod `pod-dados-2`, colocamos os nomes dos integrantes e depois excluímos esse Pod.

Em seguida, criamos um terceiro Pod, chamado `pod-dados-3`, utilizando o mesmo PVC.

Ao verificar os arquivos, encontramos o `grupo.txt` e conseguimos abrir seu conteúdo normalmente.

Essa foi a parte mais importante da prática, pois conseguimos observar que o arquivo continuou salvo mesmo depois da exclusão do Pod anterior.

**5. Finalizando a atividade**

Depois de concluir os testes, realizamos a limpeza do ambiente, removendo os Pods, o ConfigMap, o PVC e o PV que havíamos criado.

Também verificamos se os recursos tinham sido removidos corretamente.

### O que aprendi com essa aula?

Com essa aula, consegui entender melhor que uma aplicação não deve depender somente dos arquivos armazenados dentro de um Pod, pois ele pode ser substituído e os dados locais podem ser perdidos.

Também aprendi a diferença entre PV e PVC, como utilizar um ConfigMap e como conectar um armazenamento a um Pod.

O que mais me chamou a atenção foi o desafio prático, porque conseguimos criar um arquivo, excluir o Pod e depois acessar esse mesmo arquivo através de outro Pod.

Foi uma aula importante para entender melhor como funciona o armazenamento na computação em nuvem e como podemos manter os dados de uma aplicação mesmo quando precisamos substituir seus recursos.

---

**Disciplina:** Computação em Nuvem  
**Aula:** 6 – Configuração e Armazenamento Persistente  
**Professora:** Simone

