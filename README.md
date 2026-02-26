# 🎮 Pokemon Lista

Script Python que consome a [PokeAPI](https://pokeapi.co) e exporta os dados dos primeiros 20 Pokémons em uma planilha Excel formatada.

---

## 📋 Sobre o Projeto

Este projeto foi desenvolvido como teste técnico para demonstrar:

- Consumo de APIs REST com Python
- Manipulação e organização de dados
- Exportação para Excel com formatação profissional
- Tratamento de erros e código modular

---

## ✨ Funcionalidades

- Busca os **primeiros 20 Pokémons** da PokeAPI
- Coleta: **ID, Nome, Altura, Peso, Tipos e Base Experience**
- Gera o arquivo `pokemon.xlsx` com formatação visual profissional
- Trata erros de rede sem interromper a execução completa

---

## 🛠️ Tecnologias

- **Python 3.10+**
- [requests](https://pypi.org/project/requests/) — requisições HTTP
- [openpyxl](https://pypi.org/project/openpyxl/) — geração do arquivo Excel
- [PokeAPI v2](https://pokeapi.co/docs/v2) — API pública de dados Pokémon

---

## 🚀 Como usar

### 1. Clone o repositório

```bash
git clone https://github.com/Casali-Thiago/API_Pokemon.git
cd Poketeste
```

### 2. Instale as dependências

```bash
pip install requests openpyxl
```

### 3. Execute o script

```bash
python poketeste.py
```

### 4. Saída esperada

```
Buscando lista de Pokémons...
[1/20] Bulbasaur encontrado
[2/20] Ivysaur encontrado
...
Arquivo 'pokemon.xlsx' gerado com sucesso!
```

O arquivo `pokemon.xlsx` será gerado na mesma pasta do script.

---

## 📁 Estrutura do Projeto

```
pokemon-data-fetcher/
│
├── poketeste.py   # Script principal
├── pokemon.xlsx         # Arquivo gerado (após execução)
└── README.md
```

---

## 📊 Exemplo de Saída

| ID | Nome       | Altura (dm) | Peso (hg) | Tipos          | Base Experience |
|----|------------|-------------|-----------|----------------|-----------------|
| 1  | Bulbasaur  | 7           | 69        | grass, poison  | 64              |
| 2  | Ivysaur    | 10          | 130       | grass, poison  | 142             |
| 3  | Venusaur   | 20          | 1000      | grass, poison  | 263             |
| 4  | Charmander | 6           | 85        | fire           | 62              |
| 5  | Charmeleon | 11          | 190       | fire           | 142             |

> Altura em decímetros (dm) e Peso em hectogramas (hg), conforme retornado pela API.

---

## ⚙️ Como funciona

O script é organizado em três funções principais:

**`lista_de_pokemon(limit)`**
Busca a lista dos primeiros N Pokémons disponíveis na API.

**`acharPokemon(url)`**
Busca os dados detalhados de cada Pokémon individualmente pelo URL retornado na listagem.

**`create_excel(pokemons, filename)`**
Gera o arquivo `.xlsx` com os dados coletados, aplicando cabeçalho estilizado, bordas e linhas alternadas.

---

## 🛡️ Tratamento de Erros

- `response.raise_for_status()` — lança exceção para respostas HTTP com erro (4xx, 5xx)
- `try/except` por Pokémon — falhas individuais são registradas no terminal sem interromper o script
- Campo `base_experience` tratado com `.get(..., 'N/A')` pois pode ser nulo na API

---

## 📄 Licença

Este projeto é de uso livre para fins educacionais e de avaliação técnica.
