# Projeto Simulando Malwares - Versão de Curta.

# Ransonware:
Como aluna, eu percebi na prática que a parte de ransomware do desafio não é sobre como criar um malware real, e sim **mostrar o comportamento* que um ataque desse tipo teria. Tudo de forma controlada e segura. A ideia aqui, é entender o impacto que um ransomware causa quando criptografa arquivos e impede o acesso ao conteúdo da vítima.

Na simulação, o script sequestra esses arquivos e embaralha o conteúdo como se estivesse criptografando. Isso mostra como em um ataque real, os dados deixam de fazer sentido para o usuário. Esse processo deixa bem claro como o ransomware funciona no mundo real: Ele compromete arquivos essenciais e cria dependência total da chave para restaurar tudo. Ao ver isso funcionando mesmo em teste, fica evidente porque backups e segurança preventiva são tão importantes. A simulação ajuda a compreender a mecânica do ataque sem expor ninguém a riscos.

Obs: O projeto ainda será editado com imagens e comandos da aula, amanhã, dia 30/11, no momento estou apenas colocando aqui, o entendimento do desafio.

# Keylogger:
Na parte de keylogger, o objetivo não é capturar teclas de forma invisível ou maliciosa, e sim **entender o conceito de registro de digitação** de um jeito totalmente seguro e controlado.

A lógica é simples: O script pede que eu digite algo e cada vez que eu envio uma linha, ele registra no arquivo de log. Isso mostra como, em um keylogger verdadeiro, cada tecla pressionada poderia ser gravada e enviada para um atacante. Essa abordagem deixa claro o perigo desses softwares no mundo real e o motivo de existir tanta preocupação com eles.

Essa simulação reforça a importância de detectar comportamentos suspeitos, revisar processos em execução, evitar instalar programas desconhecidos e usar camadas extras de proteção, como autenticação de dois fatores. Ao ver a mecânica básica funcionando, mesmo em uma versão inofensiva, fica muito mais fácil compreender como a coleta de informações acontece em ataques reais.
