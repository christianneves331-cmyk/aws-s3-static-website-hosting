# aws-s3-static-website-hosting
Projeto de hospedagem de site estático no Amazon S3 focado em políticas de bucket (JSON) e governança de acesso.

Projeto AWS: Hospedagem de Site Estático (S3 vs. Amplify)

Este repositório documenta a implementação de um site estático utilizando o Amazon S3, focando em conceitos de governança de dados e permissões de acesso em nuvem.

Objetivo Técnico
A AWS oferece o serviço Amplify para automação de sites, mas este projeto utilizou deliberadamente o Amazon S3 para explorar as camadas de segurança e permissões de bucket (Bucket Policies), fundamentais para o entendimento da infraestrutura base.

Serviços e Configurações Aplicadas:

Amazon S3: Criação e configuração de bucket na região us-east-1.

Static Website Hosting: Ativação do recurso de hospedagem nativa para o arquivo index.html.

Gerenciamento de Acesso: Configuração de Public Access Blocks e exposição controlada.

Governança e Segurança (IAM):
Abaixo, a Bucket Policy implementada via JSON para permitir a leitura pública dos objetos, aplicando conceitos de ARN (Amazon Resource Name):

{
"Version": "2012-10-17",
"Statement": [
{
"Sid": "PublicReadGetObject",
"Effect": "Allow",
"Principal": "",
"Action": "s3:GetObject",
"Resource": "arn:aws:s3:::amazontestsite-christian/"
}
]
}

Resultados:
O ambiente foi validado com sucesso através do endpoint gerado pela AWS, servindo o conteúdo diretamente do Amazon S3. Este exercício consolida conhecimentos em permissões granulares e segurança de objetos na nuvem.
