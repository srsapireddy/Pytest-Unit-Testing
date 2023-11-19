# Pytest-Unit-Testing

#### File: my_module.py
```
def square(x):
    return x ** 2
```
#### test_my_module.py
```
from my_module import square
import pytest

@pytest.fixture
def input_value():
    return 4

  def test_square_gives_correct_value(input_value):
    # When
    subject = square(input_value)

    # Then
    assert subject == 16
```
#### Running test
```
pytest
```

#### Output
![image](https://github.com/srsapireddy/Machine-Learning-Model-Testing-and-Monitoring/assets/32967087/9fce720e-30f9-49a4-9e76-b1544632eaea)


#### Create new Test File: test_my_module_again.py
```
from my_module import square

def test_square_return_value_type_is_int():
    # When
    subject = square(2)

    # Then
    assert isinstance(subject, int)
```
#### Running
```
py_test
```
Here, we can see that two tests are passed using the pytest.
#### Output
![image](https://github.com/srsapireddy/Machine-Learning-Model-Testing-and-Monitoring/assets/32967087/cab62443-4ed5-40e4-b6ba-8e30f077a671)


#### Create a new file: conftest.py
```
import pytest

@pytest.fixture
def input_value():
    return 4
```
#### Create a new file: test_my_module_again.py
#### test_my_module.py

```
from my_module import square

def test_square_return_value_type_is_int(input_value):
    # When
subject = square(input_value)

# Then
assert isinstance(subject, int)
```
#### Rerun the tests
```
pytest
```
We can see that both are passed.
By context, the fixtures in conftest will be made available to your test modules.
#### Output
![image](https://github.com/srsapireddy/Machine-Learning-Model-Testing-and-Monitoring/assets/32967087/9afdbd1b-fe62-4df7-9830-5b86b03c0110)

#### Parameterization Option in pytest
#### File: test_my_module_again.py
```
from my_module import square
import pytest

@pytest.mark.parameterize(
    'inputs',[
    2,3,4]
)
def test_square_return_value_type_is_int(inputs):
    # When
subject = square(inputs)

# Then
assert isinstance(subject, int)
```
### After running this, we can see that four tests are passed. The reason is that each of these values is turned into a test.
#### Output
![image](https://github.com/srsapireddy/Machine-Learning-Model-Testing-and-Monitoring/assets/32967087/a450c20b-97d9-4300-9efb-2ef2908e1783)
