# Guia Completo para Configuração de Servidor Proxy Debian 11

### JONATAS SILVA PERAZA, MANUELA LUCH SILVA - INB0243-3- 2023324602 2023317063

**NOTA IMPORTANTE: Este guia foi elaborado seguindo as diretrizes apresentadas pelo professor Adamo Dal Berto durante as aulas.**

Para implementar seu servidor proxy, execute os procedimentos descritos a seguir:

## Configuração Inicial da Máquina Virtual

1. **Iniciando o Oracle VM VirtualBox:**
   - Abra o aplicativo Oracle VM VirtualBox em seu sistema.
   
   <img width="1914" height="1079" alt="image" src="https://github.com/user-attachments/assets/295b2845-4ba7-4e00-ac5f-c850e0a66148" />


2. **Criação de Nova VM:**
   - Selecione *Novo* para começar a configuração de uma nova máquina virtual.
   
   <img width="582" height="196" alt="image" src="https://github.com/user-attachments/assets/f24a21b6-73bc-46a8-a8a6-8cad7551efdb" />


3. **Definindo Parâmetros Básicos:**
   - Complete os campos *Name* e *Folder* com o nome desejado e localização do servidor em sua máquina.
   - Mantenha o campo *ISO Image* vazio por enquanto.
   - Escolha **Linux** em **Tipo**, **Debian** em *Subtype* e **Debian 11 Bookworm (64-bit)** em *Version* para garantir compatibilidade, segurança e estabilidade.
   
   <img width="1018" height="732" alt="image" src="https://github.com/user-attachments/assets/d151bc97-7208-400d-a5bb-8417fec6fea5" />



4. **Prosseguindo:**
   - Clique em *Next* para continuar.

5. **Configuração de Recursos de Hardware:**
   - Defina **2048 MB** em *Base Memory*. Esta quantidade de RAM é adequada para ambientes de teste ou servidores de pequeno porte. Assegure-se de não ultrapassar a RAM disponível no host.
   - Configure *Processors* para **1 CPU**. Um núcleo será suficiente para testes e cargas leves.
   
   <img width="1027" height="759" alt="image" src="https://github.com/user-attachments/assets/8c55326a-35be-4fdb-b0c6-043f649526d1" />


6. **Avançando:**
   - Clique em *Next* para prosseguir.

7. **Criação do Armazenamento Virtual:**
   - Estabeleça o tamanho do disco em **20 GB**. Este espaço comportará o sistema operacional e dados necessários.
   
   <img width="1010" height="742" alt="image" src="https://github.com/user-attachments/assets/c0e3a3d1-4e08-4f8e-a5a1-5d4f7c4c6d0a" />


8. **Continuando:**
   - Clique em *Next* para avançar.

9. **Finalização da Configuração Inicial:**
   - Revise o resumo das configurações apresentado pelo VirtualBox.
   - Se as especificações estiverem corretas, clique em *Finish* para criar a máquina virtual.
   - A nova VM aparecerá no painel lateral do VirtualBox.
   
   <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/adcde5ab-9d89-47b8-af63-c76ae92b12b6" />


## Otimização das Configurações da VM

10. **Acessando Configurações Avançadas:**
    - Selecione a VM criada e clique em *Configurações*.
    - Um painel de configurações será aberto para personalização detalhada.

    **Desabilitando o Drive de Disquete:**
    - Acesse a aba *Sistema*, sub-menu *Motherboard*.
    - Na seção Boot Order, desmarque *Floppy* para economizar recursos.
    
    <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/68b748ce-0885-4ef2-92e4-84bff361c041" />


    **Desativando Recursos de Áudio:**
    - Navegue até *Audio*.
    - Desmarque *Enable Audio* para reduzir consumo de recursos.
    
    <img width="964" height="585" alt="image" src="https://github.com/user-attachments/assets/6b64efc4-86ec-4d5f-94e6-af4b194aa365" />


    **Configurando Suporte USB:**
    - Vá até a aba *USB*.
    - Selecione *USB 2.0 (OHCI + EHCI) Controller* para compatibilidade com dispositivos USB 2.0.
    
    <img width="1918" height="1076" alt="image" src="https://github.com/user-attachments/assets/cbadf5fd-3946-45cf-b645-f89b75602216" />


11. **Salvando Configurações:**
    - Clique em *Ok* para aplicar todas as alterações.

## Instalação do Sistema Operacional

12. **Inicializando a VM:**
    - Com a máquina selecionada, clique em *Start* para iniciar o boot.
    
    <img width="339" height="222" alt="image" src="https://github.com/user-attachments/assets/506f3e76-9845-4282-8327-a4cc0f41e45a" />


13. **Obtendo a ISO do Debian 12:**
    - Baixe a imagem ISO do Debian 1q através do link oficial: [Site Debian](https://cdimage.debian.org/cdimage/archive/11.6.0/amd64/iso-cd/)
    - Escolha a versão *64-bit (amd64)* correspondente à arquitetura configurada.
    
    <img width="747" height="512" alt="image" src="https://github.com/user-attachments/assets/e31cad33-a8fe-4068-bc46-d63458c070b9" />


14. **Associando a ISO à VM:**
    - No menu superior, acesse *Devices* > *Optical Drives* > *Choose a disk file...*
    - Localize e selecione o arquivo ISO do Debian 12 baixado.
    - Reinicie a VM através de *Machine* > *Reset* e confirme a reinicialização.
    
    <img width="1120" height="565" alt="image" src="https://github.com/user-attachments/assets/c9f14c2e-d468-45ca-98cf-667afa7eb2d1" />

    <img width="1008" height="713" alt="image" src="https://github.com/user-attachments/assets/1423f387-8ae2-4d5f-b777-7d90762bfebf" />

    <img width="806" height="570" alt="image" src="https://github.com/user-attachments/assets/9fcfa3ad-6dd5-4724-902a-ff1a3121ba68" />

    <img width="757" height="514" alt="image" src="https://github.com/user-attachments/assets/18ee4106-cb3f-4486-bcf6-bc1c659efa68" />


15. **Iniciando a Instalação:**
    - Após o reinício, aparecerá a tela do instalador Debian 11.
    - Use as setas para selecionar *install* e pressione Enter.
    - Observação: O tutorial foi feito com interface grafica para uam melhor visualisação, Porem o certo deve ser sem interface grafica. Fique tranquilo que os passos são exatamente os mesmos.
    
    <img width="647" height="602" alt="image" src="https://github.com/user-attachments/assets/38813d5a-1b7a-423d-bdfb-1861aa1a526a" />

16. **Configurações Regionais:**
    - **Idioma:** Selecione Português (Brasil).
    - **Região:** Escolha Brasil.
    - **Layout do Teclado:** Defina Português (Brasil).
    
    <img width="801" height="709" alt="image" src="https://github.com/user-attachments/assets/30ec5099-e025-4db4-9365-017aa6dbde9d" />
    <img width="822" height="710" alt="image" src="https://github.com/user-attachments/assets/9a004fc3-5b7d-4a72-add5-44fffc1c2e48" />
    <img width="811" height="708" alt="image" src="https://github.com/user-attachments/assets/2b806a32-6259-4b99-9ad2-9ea073911fa2" />


17. **Configuração de Rede:**
    - **Nome da Máquina:** Use o mesmo nome definido na criação da VM.
    - **Domínio:** Insira "acme.com.br".
    
    <img width="801" height="695" alt="image" src="https://github.com/user-attachments/assets/3f280333-c1b5-45b2-aa5f-08350eadba74" />
    <img width="802" height="689" alt="image" src="https://github.com/user-attachments/assets/f69b3053-1062-4413-a0dd-b1c2e67519fe" />


18. **Criação de Usuários:**
    - Crie o usuário "suporte" com senha "aluno".
    - Defina a senha do root como "aluno".
    
    ⚠️ **IMPORTANTE:** Senhas simples são aceitáveis apenas para fins educacionais. Em produção, utilize senhas complexas com combinação de letras, números e caracteres especiais.

19. **Definição de Fuso Horário:**
    - Selecione seu estado (São Paulo é comumente usado como referência para o fuso UTC-3).
    
    <img width="808" height="706" alt="image" src="https://github.com/user-attachments/assets/557a2955-a6c4-49fe-aba5-55ca94f1fee7" />


## Particionamento Personalizado do Disco

20. **Iniciando Particionamento Manual:**
    - Selecione "Manual" para configuração personalizada das partições.
    - Escolha o disco virtual de 20 GB criado anteriormente.
    - Confirme a criação de novas tabelas de partições vazias.
    
    <img width="807" height="701" alt="image" src="https://github.com/user-attachments/assets/91cbc049-c53c-408e-9572-6610425fb21d" />

    <img width="806" height="704" alt="image" src="https://github.com/user-attachments/assets/0beb608d-e981-49fc-873f-f1a0edc6456f" />

    <img width="844" height="722" alt="image" src="https://github.com/user-attachments/assets/9dab6546-5227-4c4d-9cb5-35dc29cda4bb" />


21. **Esquema de Particionamento Recomendado:**

| **Ponto de Montagem** | **Tamanho** | **Opções de Segurança** |
|----------------------|-------------|------------------------|
| / | 7 GB | - |
| swap | 1 GB | - |
| /home | 4 GB | nodev, nosuid, noexec |
| /var/log | 5 GB | - |
| /var/tmp | 2 GB | nodev, nosuid, noexec |
| /tmp | 2 GB | nodev, nosuid, noexec |

22. **Função de Cada Partição:**

    **Partição / (Root):** Sistema operacional base.
    
    **Partição swap:** Memória virtual adicional.
    
    **Partição /home:** Dados pessoais dos usuários.
    - **nodev:** Previne interpretação de dispositivos especiais.
    - **nosuid:** Impede execução de arquivos setuid.
    - **noexec:** Bloqueia execução direta de binários.
    
    **Partição /var/log:** Armazenamento de logs do sistema.
    
    **Partição /var/tmp:** Armazenamento de logs do sistema.
    
    **Partição /tmp:** Arquivos temporários com restrições de segurança.
    

**OBSERVAÇÃO:** As três primeiras partições (/, swap, /home) devem ser primárias, todas criadas no início do espaço disponível.

23. **Processo de Criação das Partições:**
    - Selecione espaço livre > "Criar uma nova partição"
    - Defina o tamanho conforme tabela
    - Escolha tipo conforme especificação
    - Selecione "Início" para posicionamento
    - Configure "Usar como" (swap para partição de troca, sistema de arquivos padrão para as demais)
    - Defina ponto de montagem conforme tabela
    - Adicione opções de segurança quando aplicável
    - Finalize configuração da partição
    - Repita para todas as partições
    
    <img width="853" height="740" alt="image" src="https://github.com/user-attachments/assets/5165253c-d140-4573-a90f-6737711b07ae" />
    <img width="847" height="716" alt="image" src="https://github.com/user-attachments/assets/851cdbb4-2080-4fb9-b32f-063681d2c9e0" />
    <img width="860" height="726" alt="image" src="https://github.com/user-attachments/assets/cc6589ec-dd97-439e-93b9-74f13bdf0860" />
    <img width="850" height="723" alt="image" src="https://github.com/user-attachments/assets/747effa0-5d68-4f9e-b164-523e55358945" />
    <img width="839" height="719" alt="image" src="https://github.com/user-attachments/assets/cb0d21e5-f7d1-40c9-b95b-64ecc2782a3b" />
    <img width="858" height="737" alt="image" src="https://github.com/user-attachments/assets/28a68323-8adf-4d9e-bedc-1fad32e0bf46" />
    <img width="860" height="737" alt="image" src="https://github.com/user-attachments/assets/cdca1d8b-af6e-4b06-98f5-c28258421a22" />
    <img width="841" height="730" alt="image" src="https://github.com/user-attachments/assets/365aace5-3c0c-4196-8cce-4d134639ee3b" />
    <img width="847" height="714" alt="image" src="https://github.com/user-attachments/assets/0ddeb693-be92-4bc6-a8d3-ef5d870bf9e8" />

24. **Confirmação das Alterações:**
    - Revise todas as configurações de particionamento.
    - Confirme as alterações no disco.
    
    <img width="842" height="710" alt="image" src="https://github.com/user-attachments/assets/c39d928a-de63-40bc-abcb-2b4ecad7d57e" />
    <img width="841" height="709" alt="image" src="https://github.com/user-attachments/assets/51ddb86f-187c-41a0-a7c7-13a6e12ee994" />
    <img width="847" height="722" alt="image" src="https://github.com/user-attachments/assets/6dab4240-9582-4a4a-8e31-8da69e8dd60c" />




## Finalização da Instalação

25. **Configuração do Gerenciador de Pacotes:**
    - Selecione "Não" para mídias adicionais.
    - Escolha Brasil como localização.
    - Selecione o espelho *debian.c3sl.ufpr.br* da UFPR.
    - Deixe campo de proxy HTTP vazio.
    
    <img width="840" height="715" alt="image" src="https://github.com/user-attachments/assets/6a3ca6b2-e56a-4b75-9244-a782d79c6337" />


    <img width="841" height="722" alt="image" src="https://github.com/user-attachments/assets/c837dc9f-96a4-4ff0-a59f-3f11444f45e4" />

    <img width="840" height="718" alt="image" src="https://github.com/user-attachments/assets/10eac226-f684-4059-ad96-4d794a0a8441" />

    `<img width="835" height="715" alt="image" src="https://github.com/user-attachments/assets/90cc8dad-19da-49a2-9672-aff12a434e8f" />


26. **Opções Adicionais:**
    - Decline participação no Popularity Contest.
    - Desmarque todos os pacotes extras para manter sistema enxuto.
    
    <img width="840" height="721" alt="image" src="https://github.com/user-attachments/assets/fae5bd44-704e-4aa4-bd43-fc242f56e21a" />

    <img width="842" height="714" alt="image" src="https://github.com/user-attachments/assets/01587252-de73-4df2-8b40-afe771f734d6" />


27. **Instalação do GRUB:**
    - Confirme instalação do GRUB bootloader.
    - Selecione o disco correto para instalação.
    
    <img width="834" height="713" alt="image" src="https://github.com/user-attachments/assets/51f56c59-61ca-47dc-a089-527126f6a422" />

    <img width="842" height="721" alt="image" src="https://github.com/user-attachments/assets/c9a2ba64-d2e8-4a83-a54c-0d5837c1780c" />


28. **Finalização:**
    - Clique em "Continuar" para concluir instalação.
    - Sistema reiniciará automaticamente.
    
    <img width="846" height="722" alt="image" src="https://github.com/user-attachments/assets/e00c90d9-f7fc-487a-8588-7cf5654dfe63" />


## Primeiro Acesso ao Sistema

29. **Login Inicial:**
    - Após reinicialização, selecione Debian no menu de boot.
    - Na tela de login, insira nome de usuário (suporte ou root).
    - Digite a senha correspondente.
    - Sistema estará pronto para configuração do servidor proxy.
    
    <img width="816" height="692" alt="image" src="https://github.com/user-attachments/assets/36bcf7e5-eb91-4f48-90cc-6a0da0ef8e8a" />

    <img width="823" height="693" alt="image" src="https://github.com/user-attachments/assets/2ecee7c3-548a-4b4a-9474-9f23e2743caa" />

    <img width="821" height="691" alt="image" src="https://github.com/user-attachments/assets/51d63b42-5155-413e-a6ba-4907ae8efb39" />


## Configuração da Interface de Rede

30. **Verificando a Configuração de Rede no VirtualBox:**
    - Antes de configurar a interface no sistema, certifique-se de que a VM está configurada para usar NAT.
    - No VirtualBox, com a VM desligada, acesse *Settings* > *Network*.
    - Verifique se o *Adapter 1* está habilitado e configurado como *NAT*.
    
    <img width="986" height="661" alt="image" src="https://github.com/user-attachments/assets/906aa32b-ef62-4d25-ba47-47a0e39b5d9c" />


31. **Acessando o Sistema como Root:**
    - Faça login com o usuário root para ter privilégios administrativos.
    - Digite `root` como usuário e a senha `aluno`.
    
    <img width="819" height="679" alt="image" src="https://github.com/user-attachments/assets/1adbd8b7-c3ca-423f-b709-eda4d82a024a" />


32. **Identificando a Interface de Rede:**
    - Execute o comando para listar as interfaces de rede disponíveis:
    ```bash
    ip addr show
    ```
    - Identifique a interface de rede (geralmente será `enp0s3` em máquinas virtuais VirtualBox).
    
    <img width="865" height="708" alt="image" src="https://github.com/user-attachments/assets/fa8cb04b-2d49-442b-b984-c1a91dccb646" />


33. **Editando o Arquivo de Configuração de Rede:**
    - Abra o arquivo de configuração de interfaces de rede:
    ```bash
    nano /etc/network/interfaces
    ```
    
    <img width="826" height="705" alt="image" src="https://github.com/user-attachments/assets/1fb414db-56bb-4376-945f-83083ce24a8c" />


34. **Configurando a Interface enp0s3:**
    - No editor nano, localize ou adicione as seguintes linhas para configurar a interface enp0s3:
    ```
    # Interface de rede principal
    auto enp0s3
    iface enp0s3 inet dhcp
    ```
    - **Explicação das configurações:**
      - `auto enp0s3`: Faz com que a interface seja ativada automaticamente durante o boot
      - `iface enp0s3 inet dhcp`: Configura a interface para obter IP automaticamente via DHCP
    
    <img width="835" height="701" alt="image" src="https://github.com/user-attachments/assets/2b1ca37d-756c-4dbc-a6b5-b2c993bc638e" />


35. **Salvando as Alterações:**
    - Pressione `Ctrl + X` para sair do nano
    - Digite `Y` para confirmar as alterações
    - Pressione `Enter` para salvar o arquivo
    
    <img width="846" height="690" alt="image" src="https://github.com/user-attachments/assets/d239da67-ae37-49a8-a58c-1bded9354b6b" />


36. **Reiniciando o Serviço de Rede:**
    - Execute os comandos para reiniciar a configuração de rede:
    ```bash
    systemctl restart networking
    ```
    - Ou alternativamente:
    ```bash
    ifdown enp0s3 && ifup enp0s3
    ```
    
    <img width="827" height="701" alt="image" src="https://github.com/user-attachments/assets/010a2f99-bf96-41e3-9fa7-928c65f7a1ac" />


37. **Verificando a Configuração:**
    - Confirme se a interface recebeu um endereço IP:
    ```bash
    ip addr show enp0s3
    ```
    - Teste a conectividade com a internet:
    ```bash
    ping -c 4 8.8.8.8
    ```
    
    <img width="1017" height="789" alt="image" src="https://github.com/user-attachments/assets/fac5df59-36dd-47ee-bcaf-bc28a6703971" />

    <img width="997" height="785" alt="image" src="https://github.com/user-attachments/assets/6062a8be-e663-4c53-a9d3-0552d082fa52" />


38. **Configuração de DNS (Opcional):**
    - Se necessário, configure servidores DNS editando o arquivo:
    ```bash
    nano /etc/resolv.conf
    ```
    - Adicione os servidores DNS:
    ```
    nameserver 8.8.8.8
    nameserver 8.8.4.4
    ```
    
   <img width="995" height="777" alt="image" src="https://github.com/user-attachments/assets/5cba7731-8e68-49e4-90da-3808cd70df4a" />


39. **Teste Final de Conectividade:**
    - Teste a resolução de nomes:
    ```bash
    ping -c 4 google.com
    ```
    - Se o ping for bem-sucedido, a configuração de rede está completa e funcional.
    
    <img width="1006" height="779" alt="image" src="https://github.com/user-attachments/assets/6d4e0c0d-209b-44c9-acf5-e322385aee1a" />


**Observações Importantes:**
- A configuração NAT no VirtualBox permite que a VM acesse a internet através da conexão do host
- O DHCP fornecerá automaticamente IP, gateway e DNS para a interface
- A interface `enp0s3` é o padrão para o primeiro adaptador de rede em VMs VirtualBox
- Esta configuração é ideal para ambientes de desenvolvimento e teste
