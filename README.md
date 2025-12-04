# 📊 Simulando Ameaças Digitais: Ransomware e Keylogger para Estudo
Este repositório documenta a conclusão do **Desafio Prático de Cibersegurança** da [Dio](https://web.dio.me/track/santander-ciberseguranca-2025), com o objetivo de **experimentar, compreender e documentar** o funcionamento de malwares em um ambiente 100% controlado e seguro.

<p align="center">
  <a href="https://web.dio.me/track/4f411d51-fbae-475b-91e4-560f2fcc1137" target="_blank">
  <img
    src="https://img.shields.io/static/v1?label=DIO&message=Education&color=E94D5F&labelColor=202024" alt="DIO Project" />
</p>
    
<br>

# 1. 📋 Introdução e Contexto do Desafio:
**1.1 O projeto foi dividido em três partes principais:**
1. Implementação de Ransomware Simulado;
2. Implementação de Keylogger Simulado;
3. Reflexão e Estratégias de Defesa.

**1.2 Tecnologias Utilizadas e Ambiente:**
1. Python 3;
2. Módulos principais: `[cryptography, pynput, smtplib]`;
3. Ambiente: `[Windows + Visual studio code]`.

`⚠️ Recomendação: Executar sempre em máquina virtual isolada.`

<br>

# 2. 🔐 Implementação 1: Ransomware Simulado

**2.1 Objetivo:**

Reproduzir o ciclo inicial de um ataque de ransomware: infecção, criptografia e notificação do “resgate”.

**2.2 Funcionamento Geral:**

O arquivo `ransomware.py` realiza:

- Criptografia: uso do algoritmo **[Fernet]** para cifrar arquivos .txt dentro da pasta Teste_de_Ransomware;

- Geração de chave: A chave de criptografia é gerada e armazenada em `Ransomware.py`;

- Captura de Alvos: O script varre o diretório `Teste_de_Ransomware` buscando arquivo com a extensão `.txt` para criptografar.

- Notificação de Resgate: Criação do arquivo `leia isso.txt` simulando instruções de recuperação.

**Para fins educacionais, o script descriptografar.py permite reverter a operação, evitando perda real de dados.**

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/ae74936f-8ad6-41d3-b47a-85173dfc969d" />

> **⚠️ Aviso:** Este código é estritamente educacional. Execute-o apenas em máquinas virtuais isoladas ou em ambientes de teste seguros usando a rede host-only.

<br>

# 3. ⌨️ Implementação 2: Keylogger Simulado

**3.1 Funcionamento Geral:**

O arquivo keylogger.py implementa:

- Captura de teclas: Via `pynput.keyboard` usando a função on_press(key);

- Tratamento de caracteres: key.char, Key.space, Key.enter e etc;

- Filtragem: Teclas de controle (Shift, Ctrl, Alt, Caps Lock) são ignoradas;

- Registro: Tudo é salvo em log.txt em modo append;

- Exfiltração: módulo separado com smtplib simula envio do log para e-mail.

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/fac54287-9183-40ce-bd92-4ce57c047d03" />

<br><br>

# 4. 🛡️ Reflexão sobre Defesa e Mitigação:
A simulação prática de Ransomware e Keylogger revela a importância de uma **Estratégia de Defesa em Camadas**. A mitigação dessas ameaças exige medidas que vão desde o nível de infraestrutura até a conscientização do usuário.

**4.1 Defesa Específica Contra Ransomware:**

- Backup 3-2-1: três cópias, duas mídias, uma offline. É a defesa mais decisiva.

- Princípio do Menor Privilégio: reduzir permissões limita o impacto.

- Segmentação de Rede: isola dados críticos e impede propagação lateral.

**4.2 Contra Keylogger:**

- EDR/Antivírus: detectam hooks suspeitos e comportamentos de exfiltração.

- Teclado Virtual: frustra keyloggers que dependem de captura física.

- Firewall: impedir tráfego SMTP suspeito corta o canal de envio.

**4.3 Mitigação Focada no Fator Humano:**
A maioria dos ataques de malware começa com o **Fator Humano**.

* **Conscientização do Usuário (Phishing):** O Ransomware e o Keylogger frequentemente entram através de e-mails de **phishing** ou *malvertising*. Treinamento contínuo ajuda os usuários a identificarem anexos e links maliciosos.
* **Patch Management:** Manter o **Sistema Operacional** e todos os aplicativos (navegadores, Java, Adobe) atualizados. Muitas vezes, o malware explora vulnerabilidades de softwares desatualizados para ser executado.
* **Software de Segurança Atualizado:** Garantir que o Antivírus e o EDR estejam sempre rodando com as **definições de vírus mais recentes**.

<br>

## 5. ✅ Conclusão:

Este projeto permitiu que eu:

* Compreendesse o ciclo de ataques de **Ransomware** e **Keylogger**;  
* Entender as técnicas de **mitigação e defesa em camadas**, desde backups até EDR e conscientização do usuário.  
* Desenvolver **habilidades práticas** de análise de malware e reforçar a importância de **uso ético** do conhecimento adquirido.


> **⚠️ Obs:** Ele reforça que estudar ameaças digitais deve sempre ser feito em laboratórios isolados, com responsabilidade e atenção à ética na cibersegurança.

<br>

## Política de Uso Ético
Este projeto foi criado apenas para fins educacionais, como parte do estudo sobre Ransomware e Keylogger.  
O uso indevido deste código fora de laboratório é proibido.
Para detalhes completos sobre responsabilidades, limites e boas práticas, consulte: 👉 [Política de Uso Ético](./Security.md)

<br>

<h2> 🔗 Compartilhe com a comunidade 🧡 </h2>

Por favor, se esse conteúdo te ajudou, não esqueça de compartilhar 😁

[![GitHub Repo stars](https://img.shields.io/badge/share%20on-twitter-03A9F4?logo=twitter)](https://twitter.com/share?url=https://github.com/Luhrodrigues45/Simulacao-Ransomware-Keylogger) [![GitHub Repo stars](https://img.shields.io/badge/share%20on-facebook-1976D2?logo=facebook)](https://www.facebook.com/sharer/sharer.php?u=https://github.com/Luhrodrigues45/Simulacao-Ransomware-Keylogger) [![GitHub Repo stars](https://img.shields.io/badge/share%20on-linkedin-3949AB?logo=linkedin)](https://www.linkedin.com/shareArticle?url=https://github.com/Luhrodrigues45/Simulacao-Ransomware-Keylogger)
