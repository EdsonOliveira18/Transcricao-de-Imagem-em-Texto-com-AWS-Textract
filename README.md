# **Transcrevendo uma Imagem em Texto com AWS Textract**

![AWS Textract](images\logo.png)

## **O que é AWS Textract?**
AWS Textract é um serviço de reconhecimento de texto da Amazon Web Services que permite extrair automaticamente texto impresso e manuscrito de documentos digitalizados, imagens e PDFs. Além de texto simples, ele também identifica estruturas complexas, como tabelas e formulários.

## **Aplicações do AWS Textract**
- Digitalização de documentos e automação de processos administrativos.
- Extração de dados de documentos financeiros, como faturas e recibos.
- Processamento de formulários e relatórios para análise de dados.

## **Passos para Realizar o Projeto**

### **Passo 1: Configurando o AWS Textract**
1. **Acessar o console AWS Textract:**
   - Faça login na sua conta AWS.
   - Navegue até o serviço "Textract" no painel de serviços da AWS.

2. **Carregar a imagem/documento:**
   - No console do AWS Textract, selecione a opção "Analyze Document".
   - Faça o upload do documento (em formato PNG, TIFF, JPEG ou PDF).

3. **Escolher o tipo de análise:**
   - O Textract oferece diferentes opções de análise:
     - **Detectar somente texto**: Apenas extrai o conteúdo textual.
     - **Analisar tabelas e formulários**: Identifica tabelas e campos de formulário no documento.

### **Passo 2: Processando a Imagem com Textract via SDK**
Se preferir automatizar o processo, você pode usar o **AWS SDK** em Python:

```python
import boto3

# Criar o cliente Textract
textract = boto3.client('textract')

# Carregar a imagem
with open('documento.jpg', 'rb') as documento:
    response = textract.detect_document_text(Document={'Bytes': documento.read()})

# Exibir o texto extraído
for item in response['Blocks']:
    if item['BlockType'] == 'LINE':
        print(item['Text'])
```

### **Passo 3: Exibindo os Resultados**
- O AWS Textract retorna uma estrutura de dados que contém o texto extraído, incluindo as coordenadas de onde o texto foi encontrado na imagem.
- Você pode formatar e exibir esse texto em uma interface de usuário, ou salvá-lo em um banco de dados.

### **Passo 4: Gerando um Relatório**
Após a extração, você pode gerar um relatório com os seguintes detalhes:
- **Imagem original**.
- **Texto extraído**.
- **Análise de tabelas e formulários**, se aplicável.

## **Imagens Explicativas**
### 1. Exemplo da aplicação da solução AWS Textract
![Interface do Console AWS Textract](images\example.png)

### 2. Exemplo de Fluxo Automatizado utilizando as soluções da AWS
![Exemplo de Fluxo Automatizado utilizando as soluções da AWS](images\example.png)

## **Insights e Possibilidades**
Durante o desenvolvimento deste projeto, percebi que o AWS Textract oferece uma grande variedade de aplicações no processamento de documentos, especialmente para empresas que lidam com um grande volume de informações em papel.

### **Principais Insights:**
1. **Automatização de Processos:** Com o uso de Textract e algumas integrações via SDK, é possível automatizar completamente a digitalização e o processamento de documentos.
2. **Escalabilidade:** Como parte do ecossistema AWS, o Textract permite escalonar a aplicação conforme a demanda, garantindo eficiência em grandes volumes.
3. **Personalização:** A API do Textract retorna dados detalhados, permitindo que você personalize a extração e o uso das informações conforme as necessidades do projeto.

### **Possíveis Extensões:**
- **Integração com Power BI:** Os dados extraídos podem ser usados para criar relatórios interativos.
- **Análise de Sentimento:** Após a extração, é possível utilizar serviços de machine learning, como AWS Comprehend, para analisar o conteúdo textual.
- **Validação de Documentos:** A integração com sistemas de verificação de documentos pode automatizar processos de validação em áreas como finanças e seguros.

---
Este projeto demonstra o potencial de automação que ferramentas como AWS Textract oferecem. Se você gostou deste conteúdo, sinta-se à vontade para contribuir ou sugerir melhorias no repositório!

## Onde me encontrar

[![Linkedin](https://img.shields.io/badge/-Edson-blue?style=flat-square&logo=Linkedin&logoColor=white&link=www.linkedin.com/in/edson-oliveira-9a580a231)](www.linkedin.com/in/edson-oliveira-9a580a231)
[![Gmail Badge](https://img.shields.io/badge/-eedsoncarlos359@gmail.com-006bed?style=flat-square&logo=Gmail&logoColor=white&link=mailto:eedsoncarlos359@gmail.com)](mailto:eedsoncarlos359@gmail.com)
[![GitHub](https://img.shields.io/github/followers/EdsonOliveira18?label=follow&style=social)](https://github.com/EdsonOliveira18)
