# Tabela Própria do Convênio para o Sistema Soul MV

<h2>Apresentação</h2>

Foi elaborado um excel para ajudar os faturistas que utilizam o sistema Hospitalar MV a importarem tabelas próprias de convênio, já que muitos documentos disponibilizados pelos convênios são encaminhados em pdf ou excel. Com este intuito, foi elaborado este arquivo em excel para que permita colocar as colunas desejadas na transformação para o layout exigido pela MV.

<h2>Considerações</h2>
O arquivo é para as tabelas com o valor do filme junto. Alguns convênios enviam desta forma o que necessitou deste parâmetro.

<h2>Requisitos</h2>
<ul>
    <li>Possuir o programa Excel da Microsoft</li>
    <li>Ter acesso a tela O_IMPVAL_PROC do MV</li>
    <li>Utilizar o sistema Soul MV</li>
</ul>

<h2>Utilização do arquivo</h2>
A tela do MV, (<b>O_IMPVAL_PROC</b>), exige que o arquivo em txt siga um padrão de posição, na tabela abaixo segue seus requisitos:

<table>
    <tr>
        <th>Posição</th>
        <th>Coluna</th>
    </tr>
    <tr>
        <td>01-08</td>
        <td>Código do Procedimento</td>
    </tr>
    <tr>
        <td>09-68</td>
        <td>Descrição do Procedimento</td>
    </tr>
    <tr>
        <td>69-71</td>
        <td>Nº de Auxiliares</td>
    </tr>
    <tr>
        <td>72-74</td>
        <td>Nº do Porte</td>
    </tr>
    <tr>
        <td>75-85</td>
        <td>Valor 1* (formato 999999,9999)</td>
    </tr>
    <tr>
        <td>86-96</td>
        <td>Valor 2* (formato 999999,9999)</td>
    </tr>
</table>
*Valores que no momento na tela de importação <b>(O_IMPVAL_PROC)</b> decidirá importar

<h2>Regra das Colunas do Arquivo</h2>

<ul>
    <li><b>Código</b> - Transforma em string com apenas 8 caracteres</li>
    <li><b>Procedimento</b> - Transforma todo o texto em letras maiúsculas com tamanho de 60 caracteres. Os textos menores que 60 caracteres são preenchidos com espaços em brancos até cumprir este tamanho.</li>
    <li><b>Nº PA</b> - Número do porte, caso o campo esteja vazio, será preenchido com 0 e com tamanho de 3 caracteres</li>
    <li><b>AUX</b> - Número de auxiliares, caso esteja vazio, será preenchido com 0 e com tamanho de 3 caracteres.</li>
    <li><b>R$ TOTAL</b> - Adiciona o Valor 1 e Valor dois seguindo a máscara de (999999,9999).</li>
    <li><b>TEXTO DE IMPORTAÇÃO</b> - Coluna utilizada para copiar para um arquivo de texto</li>
    <li><b>TAM</b> - Verifica se o tamanho da coluna TEXTO DE IMPORTAÇÃO contém 96 caractéres.</li>
</ul>

Obs: As demais colunas não têm propósito de utilização, estavam existentes para versão anterior.

<h2>Descrição das Atividades</h2>

<ol>
    <li>Copie a coluna do arquivo do convênio para o excel IMPORTA HONORARIO TAB PROPRIA. Recomendado fazer coluna por coluna.</li>
    <li>Abra o bloco de notas</li>
    <li>Copie o conteúdo na coluna TEXTO DE IMPORTAÇÃO</li>
    <li>Abra o MV e vá: <u>Faturamento -> Faturamento de Convênios e Particulares -> Importações -> Importação de Procedimentos/Valores</u></li>
        <ul>
            <li>Selecione o arquivo .txt</li>
            <li>Escolha da vigência e a tabela que vai ser importada</li>
            <li>“Valor a Importar” selecione o Valor 1</li>
            <li>Clique em Importar</li>
        </ul>
</ol>
