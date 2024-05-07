# Código de automação de tarefa

 Esse código tem por finalidade automatizar o processo de lançamento de DANFES (Documento Auxiliar De Nota Fiscal Eletrônica). Por meio do XML que cada nota fiscal gera, o código extrai suas informações e as insere no sistema ERP da empresa em que trabalho. O código possui em si as travas necessárias que o processo exige, como não lançar NF sem boleto anexado ao portal, nem lançar NF com a filial de entrega errada cadastrada no pedido interno, ou não lançar NF com valor do item no pedido interno icorrígivel em relação ao valor do item no XML da DANFE. Esse código ultiliza da biblioteca SELENIUM para acessar um portal criado especificamente para atender as necessidades internas da empresa; esse portal é vinculado ao sistema ERP TOTVS MICROSIGA, e tem por finalidade unir todos os documentos relacionados a uma operação de compra, nele temos os boletos referentes ao pagamento, o comprovante do pagamento, o PDF da NF, sua chave de acesso, prazo para pagamento, entre outras informações. O código é um script do processo de lançamento, ele abre o processo no portal, coleta dados como a chave de acesso da DANFE, e se o boleto está ou não anexado, e então inicia o processo de lançamento; através da chave de acesso, ele busca o XML da NF em uma pasta, essa pasta tem o propósito de ser um banco de XMLs, o código busca o XML do processo que está lançando, extrai seus dados, abre o processo no sistema ERP, e por meio das bibliotecas PYAUTOGI e PYPERCLIP verifica as informações e as corrige se necessário, além de inserir dados pertinentes ao processo; finaliza o lançamento e inicia outro.
