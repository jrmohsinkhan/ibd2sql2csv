# ibd2sql2csv
ibd2sql2csv is a dual-purpose toolset with two scripts: one converts InnoDB .ibd files to SQL with DDL generation, and the other transforms SQL INSERT statements into CSV format. It simplifies database extraction and migration, making data handling efficient and structured.

1. **`ibd2sql`** – Parses `.ibd` files to generate SQL and DDL statements.
2. **`sql2csv`** – Converts SQL INSERT statements into CSV format for easy data handling.

This repository simplifies database recovery, migration, and analysis.

---

## Features

* Extract table structure and data from InnoDB `.ibd` files.
* Generate DDL statements with optional history and foreign-key options.
* Support single and multi-value INSERT SQL generation.
* Convert SQL INSERTs to CSV format for further processing.
* Multi-process parsing for large tables.
* Optional web interface to browse `.ibd` content.
* Flexible configuration of output paths, table/schema filtering, and more.

---

## Installation

1. Clone the repository:

```bash
git clone https://github.com/jrmohsinkhan/ibd2sql2csv.git
cd ibd2sql2csv
```

2. Install dependencies (recommended in a virtual environment):

```bash
pip install -r requirements.txt
```

---

## Usage

### Parsing `.ibd` files to SQL/DDL

```bash
python ibd2sql.py /path/to/table.ibd --ddl --sql --output ./output_dir
```

Options include:

* `--ddl [history|disable-keys|keys-after]` – Generate DDL statements.
* `--sql [sql|data]` – Generate SQL INSERT statements.
* `--multi-value` – Combine multiple rows into a single SQL statement.
* `--replace` – Replace `REPLACE INTO` with `INSERT INTO`.
* `--table` – Specify table name.
* `--schema` – Specify schema name.
* `--web` – Run web console to browse `.ibd` data.

---

### Converting SQL to CSV

```bash
python sql2csv.py input.sql output.csv
```

* Converts all INSERT statements in `input.sql` to a CSV file `output.csv`.
* Supports configurable field separators and enclosures.

---

## Examples

1. Extract table structure and data:

```bash
python ibd2sql.py employees.ibd --ddl --sql --output ./output
```

2. Generate CSV from SQL inserts:

```bash
python sql2csv.py ./output/employees.sql employees.csv
```

3. Browse `.ibd` file in web console:

```bash
python ibd2sql.py employees.ibd --web
```

---

## Contributing

Contributions are welcome. Please open an issue or submit a pull request for new features, bug fixes, or enhancements.

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---


Do you want me to do that too?

