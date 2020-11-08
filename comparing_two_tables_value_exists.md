
SELECT column1 as "col1 of tbl1 not in tbl2", col2 as "col2 of tbl 1 not in tbl2" FROM schema_namee.table
  WHERE NOT EXISTS (SELECT col1, col2 FROM schema.table
                    WHERE schema.table1.id = shcema.table2.id);


