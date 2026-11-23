# Medical Data Validator

A small Python script that checks whether a list of patient records is correctly formatted. It reports which records are invalid and which fields are wrong.

> This project was built while following freeCodeCamp's Python workshop: [Medical Data Validator](https://www.freecodecamp.org/learn/python-v9/workshop-medical-data-validator).

## What it does

The `validate()` function takes a list (or tuple) of patient records and checks:

1. The data is a list or tuple.
2. Every item is a dictionary.
3. Every dictionary has exactly these keys: `patient_id`, `age`, `gender`, `diagnosis`, `medications`, `last_visit_id`.
4. Every field follows its rule (see below).

If something is wrong, it prints a message with the record position and the problem. If everything is fine, it prints `Valid format.`

## Validation rules

| Field | Rule |
|---|---|
| `patient_id` | String: the letter `p` followed by digits (e.g. `P1001`, `p1002`), case-insensitive |
| `age` | Integer, 18 or older |
| `gender` | String: `male` or `female`, case-insensitive |
| `diagnosis` | String or `None` |
| `medications` | List of strings |
| `last_visit_id` | String: the letter `v` followed by digits (e.g. `V2301`, `v2302`), case-insensitive |

## Requirements

- Python 3.8 or newer
- No external libraries (only the built-in `re` module)

## How to run

```bash
git clone https://github.com/YOUR_USERNAME/medical-data-validator.git
cd medical-data-validator
python main.py
```

## Example

Valid data:

```python
validate(medical_records)
# Valid format.
```

Invalid data (for example, age below 18 and a wrong patient ID):

```python
bad_records = [
    {
        'patient_id': 'X1001',
        'age': 15,
        'gender': 'female',
        'diagnosis': 'Asthma',
        'medications': ['Albuterol'],
        'last_visit_id': 'V2301',
    }
]

validate(bad_records)
# Unexpected format for patient_id, age at position 0.
```

## Project structure

```
medical-data-validator/
├── main.py      # validation code and sample data
└── README.md
```

## Note

All patient data in this project is **fake sample data** used only for practice. Never upload real patient information to a public repository.

## What I practiced

- Working with lists and dictionaries
- Regular expressions with `re.fullmatch` and `re.IGNORECASE`
- Type checking with `isinstance`
- Writing reusable validation functions
- Comparing sets to check for missing or extra keys

## Credits

Based on the [freeCodeCamp](https://www.freecodecamp.org/learn/python-v9/) Python curriculum.

Part of my learning journey: [My freeCodeCamp Profile](https://www.freecodecamp.org/adin-ahmed).
