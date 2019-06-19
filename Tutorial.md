# Organização das pastas e suas descrições

/PCAP - Bandeiras

/Diário BEST PRACTICES - Arquivo de boas práticas

/p4-hlir @ a30208c - submodule HLIR

/lib - Condicões de licença

/examples/p4_src - P4 exemplos

/deliver - Formato final do paper

/figures - Imagens e desenhos de workflow

/scr - códigos P4





# Execução

BB-Gen funciona em SO baseados em Linux, então caso você use um SO diferente, pode começar o tutorial desde o primeiro paso se não vai direito para o passo 4. 
Orienta-se seguir os passos do mesmo jeito que foram fornecidos aqui.

1. Baixar o Virtualbox: https://www.virtualbox.org/
2. Baixar a máquina virtual que já tem incluso todas as dependências: https://drive.google.com/uc?id=1f22-DYlUV33DsR88_MeMb4s7-1NX_ams&export=download
3. Importar a nova máquina virtual ao virtualbox
4. Fazer a instalação do BB-Gen pelo terminal.

    step 1: $ sudo apt-get install git
    
    step 2: $ sudo apt-get remove --auto-remove python-scapy

    step 3: $ git clone --recursive https://github.com/intrig-unicamp/BB-Gen.git

    step 4: $ cd BB-Gen

    step 5: $ sudo ./dependencies.sh

    step 6: $ cd p4-hlir

    step 7: $ sudo python setup.py install

    step 8: $ cd ..

    step 9: $ python main.py

5. Rodar um exemplo .p4

Foram disponibilizados varios exemplos .p4 que podem ser usados para testar o BB-Gen. A forma de rodar um programa .p4 é a seguinte:

python main.py -p4 examples/p4_src/l3_fwd_ipv6.p4 -n 1000 --performance

Todos os exemplos que podem ser usados estão na pasta /home/p4/BB-Gen/examples/p4_src

6. Abrir o wireshark 
7. Ir na pasta /home/p4/BB-Gen/PCAP
8. Analisar os PCAPs gerados no wireshark


