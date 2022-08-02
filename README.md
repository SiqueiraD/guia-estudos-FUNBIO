# guia-estudos-FUNBIO

## 1 - Dê permissão para seu usuário 
Dê permissão para seu usuário  no subprojeto **AMA PEA Foco – AMA óleo de pescado**, ele faz parte do projeto *Educação Ambiental - Fase 1* (id: 85)  
Não se esqueça da view **vw_ppps**, ela pode te ajudar.

## 2 - Altere o donatário do protocolo **2021.0831.00024-3**
Altere o donatário do protocolo 2021.0831.00024-3 para o Donatario: **Instituto do Meio Ambiente e Recursos Hídricos - INEMA-BA**  
Dica: A relação da tabela donatário com solicitação pode ser encontrada com o script de [busca de tabelas a partir de consulta](#scripts-de-ajuda)

## 3 - Crie uma solicitação qualquer no cérebro
Crie uma solicitação qualquer no cérebro e apenas salve! Após salvar, busque ela pelo protocolo na tabela `Solicitacao`. Atente-se pelo `IdSolicitacaoStatus`, pode verificar as opções de status na tabela `SolicitacaoStatus`.   
            
>Envie para aprovação!

Agora, faça a consulta na tabela `Solicitacao` novamente e pesquise também pelo `IdSolicitacao` na tabela `FluxoAprovacaoHistorico`.

## 4 - Retorne a solicitação para *Em elaboração*
Retorne a solicitação para o status *Em elaboração* modificando o `IdSolicitacaoStatus` e excluindo da tabela `FluxoAprovacaoHistorico` o item relacionado à solicitação criada na tarefa anterior.  

    Esse não é o procedimento padrão, normalmente mantemos os históricos de alterações e inserimos mais um para identificar que o fluxo foi alterado.

## 5 -

## Scripts de Ajuda:
```sql
-- BUSCAR POR COLUNAS EM TABELAS
SELECT
    tab.name AS 'TableName',
    col.*
FROM
    sys.columns col
JOIN
    sys.tables  tab  ON col.object_id = tab.object_id
WHERE
    col.name LIKE '%Prog_IdPrograma%'
ORDER BY
    TableName
```