**1. dw_orgaos**

**Descrição**: Informações de orgãos do Poder Executivo, incluindo ug, uo, uasg
(Siasg), com tabelas agrupadas pela origem dos dados: Novo Portal, Portal
Diário, Siafi e Siape

**Tabelas**:

>   1.1 novoPortal.historico_orgao  
>   1.2 novoPortal.historico_ug  
>   1.3 novoPortal.historico_uo  
>   1.4 portadiario.historico_orgao  
>   1.5 portadiario.historico_ug  
>   1.6 portadiario.historico_uo  
>   1.7 siafi.historico_orgao  
>   1.8 siafi.historico_ug  
>   1.9 siafi.historico_ug_test  
>   1.10 siape.historico_orgao  
>   1.11 siape.historico_uorg  
>   1.12 siape.historico_upag  
>   1.13 siasg.historico_orgao  
>   1.14 siasg.historico_uasg  

**Diagramas** (constam na própria base de dados na árvore “Diagramas de Banco de
Dados”)

>   dw_orgaos - (novoPortal) historico_orgao  
>   dw_orgaos - (portaldiario) historico_orgao  
>   dw_orgaos - (siafi) historico_orgao  
>   dw_orgaos - (siape) historico_orgao  
>   dw_orgaos - (siasg) historico_orgao

**1.1** novoPortal.historico_orgao

**Descrição**: histórico de nomes de orgãos do Poder Executivo, com dados provenientes do Novo Portal

**Relacionamentos:** novoPortal.historico_orgao, novoPortal.historico_ug e novoPortal.historico_uo (chave: CodOrgaoSIAFI)

**Campos:**

>   **Referencia:** varchar(6) , obrigatório  
>   **CodOrgaoSIAFI:** varchar(5) , obrigatório  
>   **NumCNPJOrgao:** varchar(14) , obrigatório  
>   **SigOrgao:** varchar(50) , opcional  
>   **NomOrgao:** varchar(100) , obrigatório  
>   **CodOrgaoMax:** varchar(5) , obrigatório  
>   **SigOrgaoMax:** varchar(50) , opcional  
>   **NomOrgaoMax:** varchar(100) , opcional  
>   **DescPoder:** varchar(50) , obrigatório  
>   **FlgFederal:** numeric(3, 0) , obrigatório  
>   **FlgUnidadesComVinculoDireto:** numeric(3, 0) , obrigatório

**Exemplo de conteúdo:**

>   **referencia:** 201812  
>   **CodOrgaoSIAFI:** 20114  
>   **NumCNPJOrgao:** 0  
>   **SigOrgao:** AGU  
>   **NomOrgao:** ADVOCACIA-GERAL DA UNIAO - UNIDADES COM VÍNCULO DIRETO  
>   **CodOrgaoMax:** 20114  
>   **SigOrgaoMax:** AGU  
>   **NomOrgaoMax:** ADVOCACIA-GERAL DA UNIAO  
>   **DescPoder:** EXECUTIVO  
>   **FlgFederal:** 0  
>   **FlgUnidadesComVinculoDireto:** 1  
>   **CodUnidadeorcamentaria:** 45101  
>   **NomUnidadeOrcamentaria:** ADVOCACIA-GERAL DA UNIAO

**script de exemplo:**

>   SELECT *  
>   FROM [dw_orgaos].[novoPortal].[historico_orgao] A    
>   WHERE A.[referencia] = '201812'

**1.2** novoPortal.historico_ug

**Descrição**: histórico de nomes de UGs (unidades de gestoras) de orgãos do Poder Executivo, com dados provenientes do Novo Portal

**Relacionamentos:** novoPortal.historico_orgao, novoPortal.historico_ug e novoPortal.historico_uo (chave: CodOrgaoSIAFI)

**Campos:**

>   **Referencia**: varchar(6) , obrigatório  
>   **CodUG**: varchar(6) , obrigatório  
>   **NomUG**: varchar(45) , obrigatório  
>   **CodOrgaoSIAFI**: varchar(5) , opcional  
>   **NumCNPJOrgao**: varchar(14) , opcional  
>   **SigOrgao**: varchar(50) , opcional  
>   **SigOrgaoOriginal**: varchar(19) , opcional  
>   **NomOrgao**: varchar(100) , opcional  
>   **NomOrgaoOriginal**: varchar(100) , opcional  
>   **skNaturezaJuridicaOrgao**: int , opcional  
>   **CodOrgaoSup**: varchar(5) , opcional  
>   **SigOrgaoSup**: varchar(50) , opcional  
>   **SigOrgaoSupOriginal**: varchar(19) , opcional  
>   **NomOrgaoSup**: varchar(100) , opcional  
>   **NomOrgaoSupOriginal**: varchar(100) , opcional  
>   **CodOrgaoMax**: varchar(5) , opcional  
>   **SigOrgaoMax**: varchar(50) , opcional  
>   **SigOrgaoMaxOriginal**: varchar(19) , opcional  
>   **NomOrgaoMax**: varchar(100) , opcional  
>   **NomOrgaoMaxOriginal**: varchar(100) , opcional  
>   **DescPoder**: varchar(50) , opcional  
>   **DescTipoAdm** :varchar(50) , opcional  
>   **FlgExisteFatoDespesa**: numeric(3, 0) , opcional  
>   **FlgExisteFatoReceita** :numeric(3, 0) , opcional  
>   **FlgUnidadesComVinculoDireto**: numeric(3, 0) , opcional

**Exemplo de conteúdo:**

>   **Referencia:** 201812  
>   **CodUG:** 133  
>   **NomUG:** REITORIA/IFCE  
>   **CodOrgaoSIAFI:** 26405  
>   **NumCNPJOrgao:** 1,07441E+13  
>   **SigOrgao:** IF DO CEARA  
>   **SigOrgaoOriginal:** NULL  
>   **NomOrgao:** INST.FED.DE EDUC.,CIENC.E TEC.DO CEARA  
>   **NomOrgaoOriginal:** NULL  
>   **skNaturezaJuridicaOrgao:** NULL  
>   **CodOrgaoSup:** 26000  
>   **SigOrgaoSup:** MIN.EDUCACAO  
>   **SigOrgaoSupOriginal:** NULL  
>   **NomOrgaoSup:** MINISTERIO DA EDUCACAO  
>   **NomOrgaoSupOriginal:** NULL  
>   **CodOrgaoMax:** 26000  
>   **SigOrgaoMax:** MIN.EDUCACAO  
>   **SigOrgaoMaxOriginal:** NULL  
>   **NomOrgaoMax:** MINISTERIO DA EDUCACAO  
>   **NomOrgaoMaxOriginal:** NULL  
>   **DescPoder:** EXECUTIVO  
>   **DescTipoAdm:** AUTARQUIA  
>   **FlgExisteFatoDespesa:** 0  
>   **FlgExisteFatoReceita:** 0  
>   **FlgUnidadesComVinculoDireto:** 0  

**Script de exemplo:**

>   SELECT A.[referencia]  
>   ,A.[CodOrgaoSIAFI]  
>   ,A.[NumCNPJOrgao]  
>   ,A.[SigOrgao]  
>   ,A.[NomOrgao]  
>   ,A.[CodOrgaoMax]  
>   ,A.[SigOrgaoMax]  
>   ,A.[NomOrgaoMax]  
>   ,A.[DescPoder]  
>   ,A.[FlgFederal]  
>   ,A.[FlgUnidadesComVinculoDireto]  
>   ,B.CodUG  
>   ,B.NomUG  
>
>   FROM [dw_orgaos].[novoPortal].[historico_orgao] A  
>   LEFT JOIN [dw_orgaos].[novoPortal].[historico_ug] B ON B.[CodOrgaoSIAFI] =
>   A.[CodOrgaoSIAFI]  
>   WHERE A.[referencia] = '201812'

**1.3** novoPortal.historico_uo

**Descrição**: histórico de nomes de UOs (unidades orçamentárias) de orgãos do Poder Executivo, com dados provenientes do Novo Portal

**Relacionamentos:** novoPortal.historico_orgao, novoPortal.historico_ug e novoPortal.historico_uo (chave: CodOrgaoSIAFI)

**Campos:**

>   **Referencia**: varchar(6) , obrigatório  
>   **CodUnidadeorcamentaria**: varchar(5) , obrigatório  
>   **NomUnidadeOrcamentaria**: varchar(45) , obrigatório  
>   **CodUnidadeGestoraResponsavel**: varchar(6) , obrigatório  
>   **CodOrgaoSIAFI**: varchar(5) , obrigatório

**Exemplo de conteúdo:**

>   **Referencia:** 201902  
>   **CodUnidadeorcamentaria:** 45101  
>   **NomUnidadeOrcamentaria:** ADVOCACIA-GERAL DA UNIAO  
>   **CodUnidadeGestoraResponsavel:** 110596  
>   **CodOrgaoSIAFI:** 20114

**Script de exemplo:**

>   SELECT A.[referencia]  
>   ,A.[CodOrgaoSIAFI]  
>   ,A.[NumCNPJOrgao]  
>   ,A.[SigOrgao]  
>   ,A.[NomOrgao]  
>   ,A.[CodOrgaoMax]  
>   ,A.[SigOrgaoMax]  
>   ,A.[NomOrgaoMax]  
>   ,A.[DescPoder]  
>   ,A.[FlgFederal]  
>   ,A.[FlgUnidadesComVinculoDireto]  
>   ,B.CodUnidadeorcamentaria ,B.NomUnidadeOrcamentaria

>   FROM [dw_orgaos].[novoPortal].[historico_orgao] A  
>   LEFT JOIN [dw_orgaos].[novoPortal].[historico_uo] B ON B.[CodOrgaoSIAFI] =
>   A.[CodOrgaoSIAFI]  
>   WHERE A.[referencia] = '201812'
