[Fase_1.pdf](https://github.com/user-attachments/files/18466635/Fase_1.pdf)
Projeto prático - parte 1
Nesse módulo vamos explorar o Streamlit, uma biblioteca que facilita a criação de aplicações web interativas e visualmente agradáveis.
Com ela, conseguimos transformar scripts Python em aplicativos web de maneira simples e rápida, sem a necessidade de conhecimentos aprofundados em desenvolvimento web.

Escolher a pasta onde o projeto será salvo ->abrir novo arquivo no Welcome -> Python File
 
Chamar o “poetry init” na aba terminal
 
Acionar enter até o final da instalação:

 
Clear para limpar o terminal.
Digitar poetry shell para criar o ambiente virtual. (.venv)
Criar novo arquivo (New File) para servir como arquivo principal. “Cadastro.py”
 
Acionar o ambiente virtual na aba inferior direita e escolhe a opção no menu superior (.venv)
 
Se o ambiente não estiver criado execute a opção “Create Virtual Environment” e dê o nome (.venv).
NO terminal, digite poetry add streamlit e aguarde a instalação
No terminal ainda, digite poetry add pandas e aguarde a instalação

Clear para limpar o terminal
Digite streamlit run Cadastro.py para iniciar a aplicação:

$ streamlit run Cadastro.py
  You can now view your Streamlit app in your browser.
  Local URL: http://localhost:8501
  Network URL: http://192.168.15.49:8501
Inicie a importação dos pacotes dentro do arquvo principal chamada de Cadastro.py
Criando uma nova página;
Crie um novo “folder” chamado “pages” e uma subfolder “Consulta.py”. Esse comando vai criar uma seção lateral á página principal.

 
 

Gravando dados de entrada

Validação de dados: Criar a função def antes do bloco principal.
def gravar_dados(nome, data_nasc, tipo): 

e então criar o botão on_click
btn_cadastrar = st.button("Cadastrar", 
                          on_click=gravar_dados,
                          args=[nome, dt_nasc, tipo])

Validação de dados com limites:
    if nome and data_nasc <= date.today():
        st.session_state["sucesso"] = True
    else:
        st.session_state["sucesso"] = False

Testar o funcionamento do botão:
if btn_cadastrar:
    if st.session_state["sucesso"]:
        st.success("Cliente cadastrado com sucesso",
                   icon="👍")
    else:
        st.error("Houve algum problema no cadastro")

