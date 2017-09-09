# wcpan.model

Declarative dictionary-based model classes for Python.

Forked from [j4mie/micromodels](https://github.com/j4mie/micromodels).

## Example

```python
import wcpan.model as wm

class Author(wm.Model):
    first_name = wm.StringField()
    last_name = wm.StringField()
    date_of_birth = wm.DateField(format="%Y-%m-%d")

    @property
    def full_name(self):
        return "%s %s" % (self.first_name, self.last_name)


douglas_data = {
    "first_name": "Douglas",
    "last_name": "Adams",
    "date_of_birth": "1952-03-11",
}

douglas = Author.from_dict(douglas_data)
print "%s was born in %s" % (douglas.full_name, douglas.date_of_birth.strftime("%Y"))
```
