# Расчеты в попластовом режиме

Использование расчетов в Python в попластовом режиме ничем не отличается от других расчетов. Пользователю нужно подать на вход вместо обычной кривой, например GR, ее осредненные значения GR#.

Пример для расчета проницаемости в попластовом режиме:

```python
from components.domain.Log import BasicLog
from components.domain.Well import Well
from components.domain.WellDataset import WellDataset

# входные кривые
well = Well('100')
datasets = WellDataset(well, 'LQC')
por = BasicLog(datasets.id, 'PHIT_VMPP#')

# выходные кривые
perm = BasicLog(datasets.id, 'PERM#', True)

# параметры
a = 2
b = 5

# расчет
perm_val = 10**(a + b * por.values)

# назначаем свойства для кривых
perm.meta.family = "Permeability"
perm.meta.units = "mD"

#добавляем свойство, чтобы результирующая кривая отображалась как блоковая
perm.meta.display = {'data_form' : 'blocked'}

# save rusults with selected reference (сохраняем результаты)
perm.set_rvalues(por.reference, perm_val)
perm.save()
```

Важно, что в конце этого алгоритма добавлена строка, которая делает из обычной кривой попластовую при отображении:

```python
#добавляем свойство, чтобы результирующая кривая отображалась как блоковая
perm.meta.display = {'data_form' : 'blocked'}
```

Это же свойство можно увидеть в любой другой попластовой кривой в виджете свойств:

![](files/Pasted%20image%2020240120124332.png)
