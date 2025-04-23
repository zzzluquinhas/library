[![tests](https://github.com/andrehora/library/actions/workflows/tests.yml/badge.svg)](https://github.com/andrehora/library/actions/workflows/tests.yml)

# Library refactoring example - Parte 2

Este exercício é a continuação da refatoração iniciada na parte 1.
Você deve realizar os 5 commits descritos abaixo e submeter os 5 links dos commits via Moodle.

# Commit 6: Moving method get_charge from Rental to Book

Mova o método `get_charge` da classe `Rental` para a classe `Book`.

#### Faça o commit das alterações
Com os testes passando, faça o commit com a seguinte mensagem: *Commit 4: Moving method get_charge from Client to Rental*.

# Commit 5: Extracting get_frequent_renter_points from Client.statement to Rental

Vamos decompor mais uma vez `statement` para diminuir seu tamanho e complexidade. 

O método extraído deve conter o código relativo ao comentário *add frequent renter points*.
Extraia o seguinte método chamado `get_frequent_renter_points` e para classe `Rental`:

```python
def get_frequent_renter_points(self):
    points = 1
    if self.book.price_code == Book.NEW_RELEASE and self.days_rented > 1:
        points += 1
    return points
````

Atualize a chamada do método `get_frequent_renter_points` em `statement`:

```python
frequent_renter_points = rental.get_frequent_renter_points()
```

Rode os testes, e observe que vários testes falham.
Ou seja, inserimos uma regressão (BUG!) no sistema.
Testes funcionam como uma rede de proteção contra a inserção de bugs.

Encontre e corrija o bug!
Dica: o bug está no código acima.

#### Faça o commit das alterações
Com os testes passando, faça o commit com a seguinte mensagem: *Commit 5: Extracting get_frequent_renter_points from Client.statement to Rental*.
