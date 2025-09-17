# [Ubuntu Server 22.04.5 LTS para Desenvolvimento Web](https://drive.google.com/file/d/1ao-DTVxa-F2rjLcGhSuizaH5d9XG-4mX/view?usp=drive_link)

Este repositório documenta a configuração de uma máquina virtual baseada no **Ubuntu Server 22.04.5 LTS**, projetada para hospedar e desenvolver aplicações **Laravel** (PHP) e **ReactJS** (Node.js), utilizando **MySQL** como banco de dados e **Apache** como servidor web.

A VM é configurada para simular um ambiente de produção otimizado para desenvolvimento local, com foco em segurança básica e facilidade de uso.

## ✨ Destaques da Configuração

  * **Sistema Operacional:** Ubuntu Server 22.04.5 LTS
  * **Servidor Web:** Apache2
  * **Linguagens/Runtimes:**
      * PHP (versão compatível com Laravel 11+)
      * Node.js (LTS) com npm
  * **Banco de Dados:** MySQL Server
  * **Ferramentas Essenciais:**
      * Composer (gerenciador de dependências PHP)
      * Git (controle de versão)
      * `unzip`, `curl`, `wget`
  * **Conectividade:**
      * Acesso SSH configurado (com autenticação via chave, se implementado)
      * Firewall (UFW) configurado para proteção básica
  * **Otimizações (se aplicável):**
      * Configuração de `php.ini` para desenvolvimento
      * Hosts virtuais Apache para múltiplos projetos (configuráveis)
      * PHP-FPM para melhor performance com Apache (se configurado)

## 🌐 Configuração de Rede e Acesso

  * **Porta Padrão:** Acesso SSH na porta padrão `22` (ou porta personalizada, se alterada).
  * **Serviços Web:** Apache escutando na porta `80` (HTTP) e `443` (HTTPS, se configurado).
  * **Proteção:** Firewall UFW configurado para permitir apenas o tráfego essencial (SSH, HTTP, HTTPS) de fontes confiáveis ou redes internas.
  * **Usuário `admin`:** Um usuário administrativo (`admin` ou similar) com privilégios `sudo` e acesso SSH é configurado para gerenciamento do sistema.

## 🔐 Segurança Básica Implementada

  * **Firewall (UFW):** Ativado e configurado para limitar o acesso a portas específicas.
  * **SSH:** Desativado login root direto, uso de autenticação via chave SSH (recomendado), e porta SSH alterada (opcional, se configurada).
  * **MySQL:** Instalação segura do MySQL (com `mysql_secure_installation`).
  * **Atualizações:** Configuração para atualizações automáticas de segurança (opcional).

## 📦 Como Usar o Arquivo `.ova` (Importar a VM)

1.  **Baixe o arquivo `.ova`:** Você precisará do arquivo `ubuntu_server_22.04.5_dev_env.ova` (ou nome similar) que não está neste repositório devido ao seu tamanho.
2.  **Abra seu VirtualBox/VMware:** Inicie seu software de virtualização (VirtualBox é o mais comum para `.ova`).
3.  **Importar Appliance:** Vá em `File > Import Appliance...` (ou equivalente).
4.  **Selecione o arquivo `.ova`:** Navegue até o local onde você salvou o arquivo `.ova` e selecione-o.
5.  **Ajuste as configurações (opcional):** Revise as configurações de CPU, RAM e rede conforme necessário para sua máquina host. Recomenda-se um mínimo de 2GB de RAM e 2 CPUs.
6.  **Inicie a VM:** Após a importação, inicie a máquina virtual.

## ⚙️ Acessando e Gerenciando a VM

  * **Login SSH:**

    ```bash
    ssh admin@<IP_DA_SUA_VM>
    ```

    (Substitua `<IP_DA_SUA_VM>` pelo endereço IP da sua VM, que você pode encontrar usando `ip a` dentro da VM após o login inicial via console).

  * **Credenciais:**

      * **Usuário SSH:** `admin` (ou o usuário que você configurou)
      * **Senha SSH:** [Sua senha de usuário ou chave SSH configurada]
      * **Usuário MySQL:** `root`
      * **Senha MySQL:** [Sua senha de root do MySQL]

    **Atenção:** Mantenha suas credenciais seguras e nunca as exponha em um repositório público.

  * **Apache:** Os arquivos dos seus projetos Laravel e React devem ser configurados em hosts virtuais Apache, geralmente na pasta `/var/www/html` ou subdiretórios específicos para cada projeto.

## 📝 Scripts e Configurações Relevantes (Opcional)

Este repositório pode conter (ou pode ser expandido para conter) scripts e arquivos de configuração que foram usados para configurar a VM, por exemplo:

  * `scripts/install_php.sh`: Script para instalar PHP e extensões.
  * `scripts/install_nodejs.sh`: Script para instalar Node.js e npm.
  * `configs/apache_vhost_template.conf`: Um modelo para configurações de hosts virtuais do Apache.
  * `configs/ufw_rules.sh`: Script para configurar as regras do firewall UFW.

## 📚 Recursos Adicionais

  * [Documentação Oficial do Ubuntu Server 22.04 LTS](https://ubuntu.com/server/docs)
  * [Documentação do Apache HTTP Server](https://httpd.apache.org/docs/)
  * [Documentação do MySQL](https://dev.mysql.com/doc/)
  * [Documentação do PHP](https://www.php.net/manual/pt_BR/)
  * [Documentação do Node.js](https://nodejs.org/docs/)

-----
