
**Nome:** Nathan Nogueira

**Matrícula:** 2017086023

**Teste 1**
**Projeto:**   Link: https://github.com/TheAlgorithms/Python

Este sistema tem como funcionalidade demonstrar implementações matematicas para fins de aprendizagem. Com o intuito de aumentar o conhecimento sobre operações matriciais por exemplo, por meio de codigos escritos em python.

```python
@pytest.mark.mat_ops
    def test_scalar_multiply():
      act = (3.5 * np.array(mat_a)).tolist()
      theo = matop.scalar_multiply(mat_a, 3.5)
      assert theo == act
```
O obejtivo deste deste é verificar se a mutiplicação de uma matriz por um escalar esta correta. Utilizando como referencia para o resulta numpy arry vezes o mesmo escalar que é passado como parametro para a função do sistema.


**Teste 2**
```python
@pytest.mark.mat_ops
@pytest.mark.parametrize("mat", [mat_a, mat_b, mat_c, mat_d, mat_e, mat_f])
def test_transpose(mat):
    if (np.array(mat)).shape < (2, 2):
        with pytest.raises(TypeError):
            logger.info(f"\n\t{test_transpose.__name__} returned integer")
            matop.transpose(mat)
    else:
        act = (np.transpose(mat)).tolist()
        theo = matop.transpose(mat, return_map=False)
        assert theo == act
```
Neste, primeiro é verificado se as dimensões de uma matriz é superior a uma matriz de 2x2, ja que uma matriz 1x1 não tem como ter transposta. Com isso, é verificado com o numpy transpose se a matriz transposta passada como parametro para o sistema é igual.

**Teste 3**
```python
@pytest.mark.mat_ops
def test_identity():
    act = (np.identity(5)).tolist()
    theo = matop.identity(5)
    assert theo == act
```

Para fazer a validação do teste, é utilizado como comparação do valor de retorno da função ***matop.identity*** a criação de uma matriz identitade, de tamanho 5x5, pelo numpy.
