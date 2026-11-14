# Raízes da Família

Árvore genealógica pessoal, inspirada no FamilySearch, mas simples: só eu edito e só eu vejo.

A página (`index.html`) é publicada como um Artifact privado no claude.ai. Os dados ficam guardados junto com ela
(banco de dados do artifact e fotos), então não é preciso instalar nada nem manter servidor.
Aberta direto no navegador, fora do claude.ai, a página funciona em "modo local" e guarda os dados no próprio navegador.

## O que já faz (Fase 1)

- Cadastro de pessoas: nome, sobrenome, sexo, nascimento e falecimento (data e local), ocupação, notas e foto.
- Datas flexíveis: `12/03/1931`, `1931`, `c. 1890`, `antes de 1900`.
- Ligações: pai/mãe, cônjuge (com data e local da união), filhos e irmãos, criando pessoa nova ou ligando a alguém já cadastrado.
- Árvore desenhada automaticamente (biblioteca dagre), com zoom, arrastar e destaque da linha direta de quem está selecionado.
- Parentesco com você, em português: avó, tia, primo de 2º grau, sogra, cunhado, nora etc.
- Busca por nome ou local.
- Exportação para o Excalidraw (copiar e colar, ou baixar arquivo) para enfeitar e imprimir.
- Cópia de segurança em `.json` (baixar e restaurar).

## Modelo de dados

- `people/<id>`: `{ given, surname, sex: "M"|"F"|"U", living, birthDate, birthPlace, deathDate, deathPlace, occupation, notes, photo }`
- `families/<id>`: `{ partners: [ids], children: [ids], marriageDate, marriagePlace }`, no mesmo formato da "família" do GEDCOM
- `meta/settings`: `{ rootId }`, a pessoa marcada como "eu"

## Próximas fases

2. Linha do tempo por pessoa, várias fotos e documentos, fontes (certidões, registros paroquiais).
3. Importar e exportar GEDCOM (para trocar dados com o FamilySearch e outros programas), gráfico em leque, mapa de lugares.
