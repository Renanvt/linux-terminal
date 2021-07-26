# Bibliotecas (Libraries)
Uma biblioteca compartilhada é um arquivo que tem inúmeras funções, métodos e procedimentos que podem ser compartilhados ou utilizados pelos outros aplicativos instalados no sistema
Uma biblioteca faltante ou corrompida faz com que os aplicativos não funcionem corretamente
No windows as bibliotecas compartilhas se assemelham com arquivos .dll

# Comando ldd
Exibe as **bibliotecas compartilhadas** requeridas por cada um dos programas listados na sua linha de comando, trazendo o nome da biblioteca e o local onde se espera encontrá-la
	
`ldd [programas] <enter>` Imprime as dependências de bibliotecas compartilhadas
	
`ldd --version <enter>` -Mosra a versão do ldd
	
`ldd -v [programa] <enter>` - Modo verbose para o programa especificado
 `ldd -v /bin/ls <enter>`
		
- Vinculando as bibliotecas compartilhadas - **ld.so**:
- Os programas executáveis dinamicamente vinculados são examinados, no momento da execução, pelo vinculador dinâmico de objetos compartilhados **ld.so**
- Ele procura por dependências no executável que está sendo carregado e tenta satisfazer vínculos a bibliotecas compartilhadas de sistema que não estejam resolvidos. Se ele não encontrar uma biblioteca, o programa não poderá rodar
- **ld.so** pode procurar pelos diretórios que contém bibliotecas na variável **LD_LIBRARY_PATH** ou as bibliotecas são procuradas em diretórios específicos como **/lib** e **/user/lib** ou em um índice de nomes e localizações de bibliotecas (binário) chamado **/etc/ld.so.cache** .
- Adicionar novas entradas ao cache: adicione o diretório que contém as bibliotecas ao arquivo **/etc/ld.so.conf** e atualize o cache com o comando **ldconfig**.

# ldconfig

```
sudo ldconfig
```

- **ldconfig** - Configura ligações em tempo de execução do ligador dinâmico (ld.so).
- Cria os links e cache necessários para as bibliotecas compartilhadas mais recentes encontradas nos diretórios especificados na CLI, no arquivo **/etc/ld.so.conf** e nos diretórios **/lib** e **/user/lib**.
- **Deve ser executado após a instalação de uma nova biblioteca compartilhada**

```
sudo ldconfig -p
```
Examina o conteúdo do cache de bibliotecas ld.so.cache

```
sudo ldconfig
```
Reconstrói o cache incluindo as atualizações realizadas em /etc/ld.so.conf.

# Variável LD_LIBRARY_PATH
Quando um programa precisa de uma biblioteca o sistema ou o ld.so procura nos diretórios que estão listados em LD_LIBRARY_PATH
- Variável de ambiente **LD_LIBRARY_PATH**
- Contém uma lista de diretórios separados por : onde o sistema irá procurar por determinada biblioteca dinâmica (*.so).
- Quando um programa precisa de uma biblioteca, o sistema procura nos diretórios listados em **LD_LIBRARY_PATH**, depois no arquivo de cache **/etc/ld.so.cache** e então nos diretórios **/lib** e **/usr/lib** nessa ordem.
- Para visualizar o conteúdo da variável de ambiente **LD_LIBRARY_PATH**, use o seguinte comando:
```
echo $LD_LIBRARY_PATH
```

- **/etc/ld.so.conf** - Arquivo que contém uma lista de diretórios nos quais pode-se procurar por bibliotecas; configurável pelo usuário.
- **/etc/ld.so.cache** - Arquivo que contém uma lista ordenada de todas as bibliotecas do sistema encontradas nos diretórios encontrados em /etc/ld.so.conf. Não é legível por humanos e não deve ser editado, pois é binário.

# Resumo: Bibliotecas compartilhadas

1. O usuário executa um programa qualquer;
2. O programa **ld.so** é invocado para descobrir as dependências do programa do usuário e vinculas as bibliotecas necessárias.
3. Para isso o **ld.so** consulta diversos diretórios que contém bibliotecas  **(ex.:/lib)** e a variável de ambiente **LD_LIBRARY_PATH**
4. Ao encontrar as dependências requeridas, efetua a vinculação e assim as funções da biblioteca ficam disponíveis para o programa chamador, e ele é então executado.
5. O **ld.so** também pode consultar um cache de nomes de bibliotecas e caminhos chamado **/etc/ld.so.cache** (não é legível por humanos).
6. È possível acrescentar mais caminhos de diretórios ao **ld.so.cache** editando-se o arquivo de configuração **/etc/ld.so.conf**
7. Caso o **/etc/ld.so.conf** seja editado, rode o programa **ldconfig** logo após para atualizar o cache **(/etc/ld.so.cache)** com as novas configurações
