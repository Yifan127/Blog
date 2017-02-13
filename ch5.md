* sqlalchemy.exc.NoReferencedTableError: Foreign key associated with column 'weather_detail.basic_id' could not find table 'weatherbasic' with which to generate a foreign key to target column 'id'

the table name is automatically set for you unless overridden. It’s derived from the class name converted to lowercase and with “CamelCase” converted to “camel_case”.

* foreign key, relationship, weather_basic.detail.append(weather_detail)

* mode, view, control

* ','.join(map(str,e))

* PickleType

```
class SomeEntity(Base):
    __tablename__ = 'some_entity'
    id = Column(Integer, primary_key=True)
    attributes = Column(PickleType)

# Just set the attribute to save it
s = SomeEntity(attributes={'baked': 'beans', 'spam': 'ham'})
session.add(s)
session.commit()

# If mutable=True on PickleType (the default) SQLAlchemy automatically
# notices modifications.
s.attributes['parrot'] = 'dead'
session.commit()
```