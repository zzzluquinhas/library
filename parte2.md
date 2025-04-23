[![tests](https://github.com/andrehora/library/actions/workflows/tests.yml/badge.svg)](https://github.com/andrehora/library/actions/workflows/tests.yml)

# Library refactoring example - Parte 2

Este exercício é a continuação da refatoração iniciada na parte 1.
Você deve realizar os 5 commits descritos abaixo e submeter os 5 links dos commits via Moodle.

# Commit 6: Moving method get_charge from Rental to Book

Mova o método `get_charge` da classe `Rental` para a classe `Book`.

Na classe `Rental`, o método `get_charge` deve apenas delegar a chamada:

```python
def get_charge(self) -> float:                
  return self.book.get_charge(self.days_rented)
```

#### Faça o commit das alterações
Com os testes passando, faça o commit com a seguinte mensagem: *Commit 6: Moving method get_charge from Rental to Book*.

# Commit 7: Moving method get_frequent_renter_points from Rental to Book

Mova o método `get_frequent_renter_points` da classe `Rental` para a classe `Book`.

Lembre-se de delegar a chamada do método `get_frequent_renter_points` na class `Rental`. 

#### Faça o commit das alterações
Com os testes passando, faça o commit com a seguinte mensagem: *Commit 7: Moving method get_frequent_renter_points from Rental to Book*.

# Commit 8: Replacing conditional with polymorphism - part 1

Iremos aplicar uma refatoração para isolar a lógica de negócio presentes nos métodos `get_charge` e `get_frequent_renter_points`.
Neste caso, iremos utilizar herança para que cada cálculo de preço e pontos fique em sua própria classe.

Primeiramente, crie a superclasse `Price` com dois métodos abstratos. Essa classe não de

```python
class Price:

    def get_charge(self, days_rented: int) -> float:
        pass

    def get_frequent_renter_points(self, days_rented: int) -> int:
        pass
```

Em seguida, crie três subclasses vazias `RegulaPrice`, `NewReleasePrice` e `ChildrenPrice`:

```python
class RegulaPrice(Price):
    pass

class NewReleasePrice(Price):
    pass

class ChildrenPrice(Price):
    pass
```

#### Faça o commit das alterações
Com os testes passando, faça o commit com a seguinte mensagem: *Commit 8: Replacing conditional with polymorphism - part 1*.



