# Pipeline CI/CD com Python e GitHub Actions
Evidências e respostas
1. O que representa a etapa de CI neste projeto?

A etapa de Continuous Integration (CI) representa a integração e validação automática do código. Neste projeto, o GitHub Actions executa os testes automatizados desenvolvidos com Pytest sempre que uma alteração é enviada ao repositório.

O objetivo é verificar se as funções da calculadora continuam funcionando corretamente e identificar rapidamente possíveis erros ou regressões no código.

Quando todos os testes são aprovados, o pipeline apresenta a execução do job de Continuous Integration com sucesso. ✅

2. O que impede a execução do Continuous Delivery quando existe um defeito?

A execução do Continuous Delivery é impedida porque o pipeline depende da aprovação da etapa de Continuous Integration.

Quando um teste falha, como o test_somar, o job de CI apresenta falha:

test_somar FAILED

Continuous Integration ❌

Como a etapa anterior não foi concluída com sucesso, o pipeline não deve prosseguir para a etapa de Continuous Delivery.

Isso funciona como uma barreira de segurança, evitando que uma versão que contém defeitos seja disponibilizada para entrega.

3. Qual seria a próxima etapa necessária para transformar este pipeline em Continuous Deployment?

Para transformar o pipeline em Continuous Deployment, seria necessário adicionar uma etapa de implantação automática (Deploy) após a aprovação dos testes.

O fluxo poderia ficar:

Código
   ↓
Continuous Integration
   ↓
Testes automatizados
   ↓
Continuous Delivery
   ↓
Deploy automático
   ↓
Aplicação em produção

No Continuous Deployment, após o código passar pelos testes e pelas demais validações, o GitHub Actions poderia realizar automaticamente o deploy da aplicação em um ambiente de produção, sem necessidade de uma aprovação manual.

Assim, o pipeline completo poderia ser representado como:

Code → Build/Test → CI → Delivery → Deploy → Produção


