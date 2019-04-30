# NextionDriver (para MMDVMHost) (Este repositório não é da minha autoria)

O objetivo deste programa é fornecer controle adicional para layouts de exibição do Nextion diferentes dos layouts fornecidos pelo MMDVMHost. Ele faz isso assente entre o MMDVMHost e o Nextion Display. Este programa pega os comandos, enviados pelo MMDVMHost e traduz, altera, adiciona ou remove esses comandos.

Como o programa tem que ler o MMDVM.ini para conhecer o Layout (para definir a taxa de transmissão) e outros parâmetros (por exemplo, para saber a freqüência e localização), os parâmetros para o NextionDriver também estão localizados no arquivo de configuração MMDVM, em uma secção extra [NextionDriver].

Como dito acima, o programa NextionDriver irá alterar os comandos conforme necessário e adiciona informação extra (ex .: temperatura, informação de TG, ...) e envia isto para a exibição no Nextion.

Este programa também verifica a interface de rede regularmente, e mostrará o endereço IP mais recente, para que você possa verificar se o endereço IP foi alterado.

Quando os arquivos 'groups.txt' e 'stripped.csv' estiverem presentes, nomes de usuários e de grupos de conversação serão procurados e enviados para o display. NOTA 1: ambos os arquivos devem ser classificados em ordem crescente de IDs! NOTA 2: para que a pesquisa de dados do usuário funcione, você DEVE desativar a consulta DMRID de MMDVMHost

O programa também tem a capacidade de receber comandos de exibição Nextion. Dessa forma, é possível fornecer botões em um layout e fazer algo no host quando esse botão é pressionado. Pode-se, por exemplo, criar uma página de 'sistema' no Nextion com informações do sistema e botões para reiniciar o MMDVMHost, reinicializar ou desligar o host, ...

Sim, é possível (quando o NextionDriver está instalado e a correr) iniciar / parar / reiniciar o MMDVMHost com botões no display do Nextion!

Quando o Nextion está conectado à porta serial do modem, o NextionDriver V1.03 e posterior podem endereçar essa porta. Como funciona? Normalmente, os dados para o monitor vão diretamente do MMDVMHost para o modem, marcados como dados para a porta serial. O modem passará os dados para a porta serial. Ao ativar dados transparentes, podemos injetar dados no MMDVMHost e marcá-los como dados para a exibição (isso só pode ser feito ativando o sendFrameType).

Os dados do Nextion (ao pressionar os botões) serão tratados de forma semelhante e sairão do MMDVMHost como dados transparentes. IMPORTANTE: o firmware do modem tem que passar dados do monitor para o MMDVMHost para que isso funcione!
