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

1. Baixar a máquina virtual que já tem incluso todas as dependências.
2. Fazer a instalação do BB-Gen

step 1: $ sudo apt-get install git

step 2: $ git clone --recursive https://github.com/intrig-unicamp/BB-Gen.git

step 3: $ cd BB-Gen

step 4: $ sudo ./dependencies.sh

step 5: $ cd p4-hlir

step 6: $ sudo python setup.py install

step 7: $ cd ..

step 8: $ python main.py

3. Rodar um exemplo .p4
4. Fazer a captura do tráfego
