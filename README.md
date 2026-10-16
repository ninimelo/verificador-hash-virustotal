
# SOC - Verificador Automático de Malware

Projeto educacional desenvolvido em Python para realizar a
triagem inicial de arquivos por meio do cálculo de hash SHA-256
e da consulta à API v3 do VirusTotal.

## Funcionalidades

- Cálculo do hash SHA-256 de arquivos locais.
- Consulta de hashes na API do VirusTotal.
- Exibição de estatísticas de detecção.
- Tratamento de erros comuns de conexão e consulta.
- Proteção da chave de API por meio de variável de ambiente.

## Tecnologias utilizadas

- Python 3
- hashlib
- os
- requests
- API v3 do VirusTotal

## Requisitos

- Python instalado.
- Conexão com a internet.
- Chave de API do VirusTotal com permissão para realizar consultas.

## Instalação

Clone o repositório:

```bash
git clone https://github.com/SEU-USUARIO/soc-verificador-malware.git
cd soc-verificador-malware
```

Instale a dependência:

```bash
python -m pip install -r requirements.txt
```

## Configuração da API

A chave da API não deve ser armazenada no código-fonte.

No Windows PowerShell, configure a variável de ambiente:

```powershell
$env:VT_API_KEY="SUA_CHAVE_DO_VIRUSTOTAL"
```

Substitua o texto pela sua própria chave.

Essa configuração vale para a janela atual do PowerShell.

## Como executar

```powershell
python triagem_malware.py
```

Informe o caminho do arquivo quando solicitado.

Exemplo no Windows:

```text
C:\Users\SeuUsuario\Desktop\arquivo.txt
```

## Como interpretar os resultados

- Detecções maliciosas: existem classificações maliciosas no relatório.
- Detecções suspeitas: existem classificações que merecem investigação.
- Hash não encontrado: não há relatório disponível para o hash consultado.
- Nenhuma detecção maliciosa: não significa que o arquivo seja comprovadamente seguro.

A ferramenta consulta um relatório por hash. Ela não executa o arquivo,
não realiza análise dinâmica e não garante a identificação de todas
as ameaças.

## Segurança

- Nunca publique sua chave de API.
- Se uma chave for exposta, revogue-a ou substitua-a assim que possível.
- Consulte apenas arquivos que você tem autorização para analisar.
- Considere as políticas de privacidade do serviço utilizado.

## Objetivo educacional

O projeto tem como objetivo praticar Python, funções, tratamento de
exceções, hashing, requisições HTTP, consumo de API REST e conceitos
de triagem inicial utilizados em segurança da informação e SOC.

## Melhorias futuras

- Exportação de resultados para JSON ou CSV.
- Testes automatizados.
- Registro de data e hora das consultas.
- Interface gráfica.
- Integração com outras fontes de inteligência de ameaças.
