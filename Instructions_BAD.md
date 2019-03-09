__2. Design a normalized relational database that can contain all CSV data in your `SourceData` repository. Document the design with an ERD and a data dictionary.__

- The database should not leave off any files or columns.
- Normalize to at least BCNF.
- The ERD should be a PDF file named "CourseDataERD.PDF" to be dropped in the `docs` folder.
- Also in the `docs` folder, add a Markdown-formatted `CourseDataDictionary.md` file that defines every column on every table. Use the table names as second level headings (`##`) and bullet lists for the column definitions. If you are feeling frisky, then perhaps use Markdown tables instead of bullet lists.  

__3. Create a SQLite database called `CourseData.db` in this folder. The database should exactly match your ERD. Populate the database with data from the CSV files.__

- CSV files are best imported using the SQLite3 tool we discussed in class. Experiment with it to get the imports right before writing any SQL.
- You will likely have to import the CSV file data into tables that you will ultimately drop when the database is completed. To keep track of them all, please the prefix the table name with `import_` to indicate that the table contains raw source data.
- Use SQL to create and populate the tables in your ERD. The code will likely look a lot like what we did in class, with lots of JOINs. You should implement FOREIGN KEY constraints (With cascading updates/deletes) as well.
- Capture all of your SQL DDL and DML code in a new notebook called `CourseDataETL.ipynb` in this project folder. Use Markdown to annotate your work as you go along. Also, make sure you can re-run your code from scratch to rebuild the database when needed.

__4. Test the integrity of your new `CourseData.db` database.__

- Create a new notebook called `CourseDataTests.ipynb`.
- Write queries to ensure that  ...
    - Each column has a sensible data type (Domain integrity); are there truncation or translation errors?   
    - Each row describes a unique entity (Entity integrity); just having a PK is not enough: you will need to look for duplicate a data records
    - Each relationship is implemented correctly (Relational integrity); are the FKs JOIN-compatible with the PKs? does each mandatory relationship have a corresponding NOT NULL constraint?
- Annotate your queries in Markdown so we know what you are testing and why.

__5. Design and build data warehouse called `CourseDataWarehouse.db`.__

- Use a star schema design. The idea is to make writing 'rollup' queries with SELECT ... FROM ... WHERE ... GROUP BY as easy as possible. The dimension FKs are likely redundant -- they can be usually be inferred from other table relationships -- but often eliminate the need for complex JOINs.
- Document each fact table (and associated dimensions) as a separate ERD. Each ERD should be named using the pattern <fact table>.pdf (without the brackets, which are there to indicate a placeholder) and contain no spaces or other unnecessary punctuation. Store the PDF files in the `docs` folder.
- You will need to figure out how to extract data from `CourseData.db` in order to insert it into `CourseDataWarehouse.db`.

__6. Test your `CourseDataWarehouse.db` for data integrity.__

- This is pretty much the same process as you used for the first database.
- Call your new notebook `CourseDataWarehouseTest.ipynb`.

__7. Demo your results with useful queries.__

- Create yet another new notebook called `CourseDataWarehouseDemo.ipynb` that illustrates the usefulness of the data warehouse with a few informative queries.
- Number the queries so we can refer to them by number later. (In other words, make sure your queries have entity integrity.)
- In your Markdown include remarks about why, when, and how the query might be used in practice. If your query results suggest anything insightful, then include a cell below the query results with Markdown-formatted remarks.

__8. Deliver a walkthrough presentation of your work.__

- Add a Markdown-formatted `Readme.md` file with a step-by-step tour of your work, including links to files as needed.
- You will have exactly 10 minutes to present your work in class. There will be no Q&A, but each team is expected to peer review every other team's work with the an online form provided just prior to the final class session.  
- There are no slides for presentation itself. Just walk us through your work using your `Readme.md` file. What ever you do, please do not try to _sell_ your work. The purpose of the walkthrough is to review the work for completeness, relevance, and professionalism. If you have met the course objectives, then your work should stand on its own.
