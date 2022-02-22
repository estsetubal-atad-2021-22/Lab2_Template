# Algoritmos e Tipos Abstratos de Dados | Enunciado

## Lab 2 + Template | **Avaliado**

Este repositório foi criado a partir de:

- [https://github.com/estsetubal-atad/CProgram_Template](https://github.com/estsetubal-atad/CProgram_Template) 

Consulte o seu README se tiver dúvidas sobre a sua utilização.

----

**Objetivos**:

- Implementação de pesquisa, seleção e ordenação;
- Documentação Doxygen.
- Debugging;

**Referências**:

- Organização ATAD, documentação do software utilizado: [https://github.com/estsetubal-atad/Docs](https://github.com/estsetubal-atad/Docs)

- Slides TP, disponíveis no Moodle.

---

:computer: Faça o clone **deste** repositório para elaborar o enunciado.

### Nível 1 (Duração estimada: < 10min)

:exclamation: As seguintes funções devem pertencer a um novo módulo "arrays".

1. Defina e implemente a função `arrayPrint`, que imprime na consola um array no formato `[a, b, c, d, <...>]`:

```cpp
void printArray(int arr[], int arrLength) {
    printf("[ ");
    for(int i=0; i<arrLength; i++) {
        printf("%d%s", arr[i], (i < arrLength - 1 ? ", " : ""));
    }
    printf("]\n");
}
```

2. Exemplifique a utilização desta função no `main`, imprimindo o array `seq`; edite o *makefile*, compile e execute o programa.

### Nível 2 (Duração estimada: ~ 25min)

3. No módulo "arrays" defina e implemente a função `arrayFirstIndexOf`:
	- **Parâmetros formais**: (i) valor `val` a procurar; (ii) um *const* array `arr` de inteiros; (iii) a sua dimensão, e;
	- **Retorno**: inteiro - índice em `arr` da primeira ocorrência de `val`; `-1` caso não exista.

4. ... defina e implemente a função `arrayLastIndexOf` - análoga à função anterior, mas devolve o índice da *última ocorrência* de `val` no array `arr`.

5. Teste o resultado destas funções sobre o array `seq` instanciado no `main`.

	- Imprima a sequência `seq`;

	- Solicite ao utilizador - com a função `readInteger` - o valor a pesquisar;

	- Invoque as funções;

	- Se o valor não existir deve ser apresentar ao utilizador a mensagem `"Valor <val> não existe na sequência."`

	- Se existir, deve apresentar os índices (primeiro e último) onde o valor ocorre.

### Nível 3 (Duração estimada: ~ 20min)

6. No módulo "arrays" defina e implemente a função `void arraySort(int arr[], int arrLenght, bool ascending)` que tem como objetivo ordenar o array `arr`. De notar que:

	- Se `ascending` for `true`, deve fazer uma ordenação crescente; se `false`, deve fazer uma ordenação decrescente.

	:bulb: É livre de utilizar o algoritmo que desejar (*bubble* or *selection sort*)

7. Teste a função no `main` e ordene o array `seq` das duas formas e apresente-o.

### Nível 4 (Duração estimada: ~ 20min)

:exclamation: Neste nível pretende-se aplicar/adaptar o algoritmo de *seleção* lecionado na TP a arrays bi-dimensionais (matrizes).

:bulb: Na linguagem C, os parâmetros que representam matrizes têm de ser representados na forma e ordem indicadas abaixo.

8. No módulo "arrays" defina e implemente a função `int matrixMaximumIndex(int n, int m, int mat[][m])` onde:

	- `m` é o número de linhas da matriz;
	- `n` é o número de colunas da matriz;
	- `mat` é o array bi-dimensional. 
	- Retorna o "índice" onde o maior valor foi encontrado, de acordo com o especificado de seguida; `-1`, caso `m` e `n` representem uma matriz vazia ou de dimensões inválidas (e.g., negativas).	

	Assumindo que utiliza uma variável `i` para percorrer as linhas e `j` para as colunas, e.g.,:
	
	```cpp
	for (int i = 0; i < n; i++) {
        for (int j = 0; j < m; j++) {
			...
	```
	
	o índice a devolver é calculado da seguinte forma:

	`computedIndex = (i * m + j)`; atualize-o apenas quando em `mat[i][j]` encontrar um "novo máximo")

:question: Qual a complexidade algorítmica da função `matrixMaximumIndex` que implementou?

9. Teste a função no `main`. O resultado esperado para a matriz `matrix` é `13` (treze).

### Nível 5 (Duração estimada: ~ 15min)

10. Forneça a documentação *doxygen* da função `matrixMaximumIndex`. 

	* Gere a documentação *doxygen* - deverá obter a pasta `html`. Abra o ficheiro `index.html` e verifique a documentação gerada.

11. Coloque um *breakpoint* na função `matrixMaximumIndex` por forma a conseguir fazer *debug* à mesma. 

	- Durante o *debugging* aponte a sequência de valores que `computedIndex` assume durante a execução da função.

