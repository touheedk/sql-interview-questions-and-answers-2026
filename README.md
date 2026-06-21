# SQL Interview Questions

SQL interview questions on joins, window functions, indexing, query optimization, and schema design.

416 questions · 25 subtopics

Full answers and code examples: [interview-prep.coderboi.com/sql](https://interview-prep.coderboi.com/sql)  
Structured study roadmap: [interview-prep.coderboi.com/roadmap/sql](https://interview-prep.coderboi.com/roadmap/sql)

---

SQL shows up in almost every data engineering, backend, and analytics interview. These questions cover what actually gets asked — not textbook theory, but the practical SQL skills interviewers test.

Window functions and query optimization are the areas where most candidates struggle. If you're comfortable with GROUP BY but haven't touched OVER() yet, start there.

---

## Index

**[Basics](#basics)** — 98 questions  
[Joins](#joins) · [SELECT & WHERE](#select--where) · [Sorting & Limiting](#sorting--limiting) · [Aggregation & GROUP BY](#aggregation--group-by) · [Set Operations](#set-operations)

**[Subqueries](#subqueries)** — 38 questions  
[Subqueries](#subqueries-1) · [Common Table Expressions (CTEs)](#common-table-expressions-ctes)

**[Window Functions](#window-functions)** — 54 questions  
[Window Function Basics](#window-function-basics) · [Ranking Functions](#ranking-functions) · [Frames & Offset Functions](#frames--offset-functions)

**[DML](#dml)** — 30 questions  
[INSERT, UPDATE & DELETE](#insert-update--delete) · [Views](#views)

**[Schema](#schema)** — 61 questions  
[Data Types](#data-types) · [DDL — Creating & Altering Tables](#ddl--creating--altering-tables) · [Constraints & Integrity](#constraints--integrity) · [Normalization](#normalization)

**[Functions](#functions)** — 45 questions  
[String & Numeric Functions](#string--numeric-functions) · [Date & Time Functions](#date--time-functions) · [Conditional & NULL Functions](#conditional--null-functions)

**[Transactions](#transactions)** — 30 questions  
[Transactions & ACID](#transactions--acid) · [Isolation Levels & Concurrency](#isolation-levels--concurrency)

**[Performance](#performance)** — 30 questions  
[Indexes](#indexes) · [Query Optimization](#query-optimization)

**[Security](#security)** — 30 questions  
[Permissions & Roles](#permissions--roles) · [SQL Injection](#sql-injection)

---

## Difficulty Key

🟢 Easy — should know cold  ·  🟡 Medium — needs practice  ·  🔴 Hard — senior-level

---

## Basics

JOIN types and aggregation are the foundation. Be able to write and explain the execution order of a query (WHERE before GROUP BY before HAVING).

### Joins

- 🟢 [What is a JOIN?](https://interview-prep.coderboi.com/sql/basics/joins#q-what-is-join)
- 🟡 [What is the difference between INNER JOIN and OUTER JOIN?](https://interview-prep.coderboi.com/sql/basics/joins#q-inner-vs-outer)
- 🟡 [What is the difference between LEFT and RIGHT JOIN?](https://interview-prep.coderboi.com/sql/basics/joins#q-left-vs-right)
- 🔴 [What is a self join?](https://interview-prep.coderboi.com/sql/basics/joins#q-self-join)
- 🟡 [What does a CROSS JOIN produce?](https://interview-prep.coderboi.com/sql/basics/joins#q-cross-join)
- 🔴 [How do you find rows with no match using a join?](https://interview-prep.coderboi.com/sql/basics/joins#q-join-nulls)
- 🔴 [What is the difference between the ON and WHERE clauses in a join?](https://interview-prep.coderboi.com/sql/basics/joins#q-on-vs-where)
- 🔴 [Why does filtering the right table in WHERE turn a LEFT JOIN into an INNER JOIN?](https://interview-prep.coderboi.com/sql/basics/joins#q-left-join-where-trap)
- 🟡 [How do you join three or more tables?](https://interview-prep.coderboi.com/sql/basics/joins#q-multiple-joins)
- 🟡 [What does the USING clause do?](https://interview-prep.coderboi.com/sql/basics/joins#q-using-clause)
- 🔴 [What is a NATURAL JOIN and why is it risky?](https://interview-prep.coderboi.com/sql/basics/joins#q-natural-join)
- 🟡 [How do you combine a join with aggregation?](https://interview-prep.coderboi.com/sql/basics/joins#q-join-groupby)
- 🟡 [Why do joins sometimes produce duplicate rows?](https://interview-prep.coderboi.com/sql/basics/joins#q-duplicate-rows)
- 🔴 [What is the COUNT trap with LEFT JOIN?](https://interview-prep.coderboi.com/sql/basics/joins#q-left-join-count-trap)
- 🟡 [When should you use a join vs a subquery?](https://interview-prep.coderboi.com/sql/basics/joins#q-join-vs-subquery)
- 🔴 [What is the difference between EXISTS and IN?](https://interview-prep.coderboi.com/sql/basics/joins#q-exists-vs-in)
- 🟡 [How do you write an anti-join?](https://interview-prep.coderboi.com/sql/basics/joins#q-not-exists-antijoin)
- 🔴 [What is a semi-join?](https://interview-prep.coderboi.com/sql/basics/joins#q-semi-join)
- 🟡 [What does a FULL OUTER JOIN do?](https://interview-prep.coderboi.com/sql/basics/joins#q-full-outer-join)
- 🔴 [How do you emulate a FULL OUTER JOIN in MySQL?](https://interview-prep.coderboi.com/sql/basics/joins#q-emulate-full-outer)
- 🟡 [What is the difference between an equi-join and a non-equi join?](https://interview-prep.coderboi.com/sql/basics/joins#q-equi-non-equi)
- 🟢 [How do you join on multiple columns?](https://interview-prep.coderboi.com/sql/basics/joins#q-join-multiple-columns)
- 🔴 [How do you use a self join to compare consecutive rows?](https://interview-prep.coderboi.com/sql/basics/joins#q-self-join-consecutive)
- 🔴 [What is the fan trap (row multiplication) in joins?](https://interview-prep.coderboi.com/sql/basics/joins#q-fan-trap)
- 🔴 [Why and how do you pre-aggregate before joining?](https://interview-prep.coderboi.com/sql/basics/joins#q-pre-aggregate)
- 🔴 [How do indexes affect join performance?](https://interview-prep.coderboi.com/sql/basics/joins#q-join-indexes)
- 🔴 [What join algorithms do databases use?](https://interview-prep.coderboi.com/sql/basics/joins#q-join-algorithms)
- 🟡 [How do you handle NULLs from outer joins in the output?](https://interview-prep.coderboi.com/sql/basics/joins#q-coalesce-join)
- 🟡 [How do you remove duplicate rows from a join result?](https://interview-prep.coderboi.com/sql/basics/joins#q-distinct-dedupe)
- 🔴 [What is a LATERAL join (or CROSS APPLY)?](https://interview-prep.coderboi.com/sql/basics/joins#q-lateral-join)
- 🔴 [What happens when you chain outer joins across three tables?](https://interview-prep.coderboi.com/sql/basics/joins#q-outer-join-chain)
- 🟢 [What is the difference between a JOIN and a UNION?](https://interview-prep.coderboi.com/sql/basics/joins#q-join-vs-union)
- 🔴 [How do you join rows within a date or value range?](https://interview-prep.coderboi.com/sql/basics/joins#q-range-join)

[Full answers with code examples →](https://interview-prep.coderboi.com/sql/basics/joins)

### SELECT & WHERE

- 🟢 [What does a SELECT statement do?](https://interview-prep.coderboi.com/sql/basics/select-where#q-what-is-select)
- 🟢 [What does the WHERE clause do?](https://interview-prep.coderboi.com/sql/basics/select-where#q-where-clause)
- 🟢 [What comparison operators can you use in WHERE?](https://interview-prep.coderboi.com/sql/basics/select-where#q-comparison-operators)
- 🟡 [How do AND and OR precedence interact?](https://interview-prep.coderboi.com/sql/basics/select-where#q-and-or-precedence)
- 🟢 [What does SELECT DISTINCT do?](https://interview-prep.coderboi.com/sql/basics/select-where#q-distinct)
- 🟢 [How does the LIKE operator work?](https://interview-prep.coderboi.com/sql/basics/select-where#q-like-operator)
- 🟢 [What does the IN operator do?](https://interview-prep.coderboi.com/sql/basics/select-where#q-in-operator)
- 🟢 [How does BETWEEN work, and is it inclusive?](https://interview-prep.coderboi.com/sql/basics/select-where#q-between-operator)
- 🟡 [How do you test for NULL values?](https://interview-prep.coderboi.com/sql/basics/select-where#q-is-null)
- 🟢 [What are column and table aliases?](https://interview-prep.coderboi.com/sql/basics/select-where#q-column-aliases)
- 🔴 [In what logical order are the clauses of a SELECT evaluated?](https://interview-prep.coderboi.com/sql/basics/select-where#q-order-of-execution)
- 🟢 [Can you compute expressions in a SELECT list?](https://interview-prep.coderboi.com/sql/basics/select-where#q-arithmetic-expressions)
- 🟡 [How does the NOT operator behave with NULLs?](https://interview-prep.coderboi.com/sql/basics/select-where#q-not-operator)
- 🟡 [How do you return a conditional value in SELECT?](https://interview-prep.coderboi.com/sql/basics/select-where#q-case-in-select)
- 🟡 [How do you do case-insensitive string filtering?](https://interview-prep.coderboi.com/sql/basics/select-where#q-filtering-strings-case)
- 🟢 [How do you return just a few rows to preview a table?](https://interview-prep.coderboi.com/sql/basics/select-where#q-limit-preview)
- 🟡 [What is the difference between WHERE and HAVING?](https://interview-prep.coderboi.com/sql/basics/select-where#q-where-vs-having)

[Full answers with code examples →](https://interview-prep.coderboi.com/sql/basics/select-where)

### Sorting & Limiting

- 🟢 [What does ORDER BY do?](https://interview-prep.coderboi.com/sql/basics/sorting-limiting#q-order-by-basics)
- 🟢 [How do you control sort direction?](https://interview-prep.coderboi.com/sql/basics/sorting-limiting#q-asc-desc)
- 🟢 [How do you sort by multiple columns?](https://interview-prep.coderboi.com/sql/basics/sorting-limiting#q-order-by-multiple)
- 🟡 [Can you sort by an expression or alias?](https://interview-prep.coderboi.com/sql/basics/sorting-limiting#q-order-by-expression)
- 🟡 [Where do NULLs sort in ORDER BY?](https://interview-prep.coderboi.com/sql/basics/sorting-limiting#q-null-ordering)
- 🟢 [How do you limit the number of rows returned?](https://interview-prep.coderboi.com/sql/basics/sorting-limiting#q-limit-clause)
- 🟡 [How do you paginate results with OFFSET?](https://interview-prep.coderboi.com/sql/basics/sorting-limiting#q-offset-pagination)
- 🔴 [What is keyset (cursor) pagination and why is it faster?](https://interview-prep.coderboi.com/sql/basics/sorting-limiting#q-keyset-pagination)
- 🔴 [Why does OFFSET get slow for deep pages?](https://interview-prep.coderboi.com/sql/basics/sorting-limiting#q-offset-performance)
- 🔴 [How do you get the top N rows per group?](https://interview-prep.coderboi.com/sql/basics/sorting-limiting#q-top-n-per-group)
- 🟡 [How do you sort by a custom order?](https://interview-prep.coderboi.com/sql/basics/sorting-limiting#q-order-by-case)
- 🟡 [Why should you add a unique tie-breaker to ORDER BY?](https://interview-prep.coderboi.com/sql/basics/sorting-limiting#q-stable-sort)
- 🔴 [How do you include rows tied with the Nth row?](https://interview-prep.coderboi.com/sql/basics/sorting-limiting#q-limit-with-ties)
- 🔴 [How do you get one row per group (Postgres DISTINCT ON)?](https://interview-prep.coderboi.com/sql/basics/sorting-limiting#q-distinct-on)
- 🔴 [What is collation and how does it affect sorting?](https://interview-prep.coderboi.com/sql/basics/sorting-limiting#q-collation)
- 🟡 [How do you return rows in random order?](https://interview-prep.coderboi.com/sql/basics/sorting-limiting#q-random-order)

[Full answers with code examples →](https://interview-prep.coderboi.com/sql/basics/sorting-limiting)

### Aggregation & GROUP BY

- 🟢 [What is an aggregate function?](https://interview-prep.coderboi.com/sql/basics/aggregation#q-what-is-aggregation)
- 🟢 [What does GROUP BY do?](https://interview-prep.coderboi.com/sql/basics/aggregation#q-group-by)
- 🟡 [Why must non-aggregated SELECT columns appear in GROUP BY?](https://interview-prep.coderboi.com/sql/basics/aggregation#q-group-by-rule)
- 🟡 [What is the difference between COUNT(*) and COUNT(column)?](https://interview-prep.coderboi.com/sql/basics/aggregation#q-count-star-vs-col)
- 🟡 [How do aggregate functions handle NULLs?](https://interview-prep.coderboi.com/sql/basics/aggregation#q-aggregates-ignore-null)
- 🟡 [What does the HAVING clause do?](https://interview-prep.coderboi.com/sql/basics/aggregation#q-having-clause)
- 🟡 [Why can't you use an aggregate in WHERE?](https://interview-prep.coderboi.com/sql/basics/aggregation#q-where-vs-having-agg)
- 🔴 [How do you aggregate conditionally (pivot)?](https://interview-prep.coderboi.com/sql/basics/aggregation#q-conditional-aggregation)
- 🟡 [Why might AVG return a truncated value?](https://interview-prep.coderboi.com/sql/basics/aggregation#q-avg-integer-trap)
- 🟢 [How do you group by more than one column?](https://interview-prep.coderboi.com/sql/basics/aggregation#q-grouping-multiple-columns)
- 🟡 [How do you count distinct values?](https://interview-prep.coderboi.com/sql/basics/aggregation#q-count-distinct)
- 🟢 [What do MIN and MAX return on different types?](https://interview-prep.coderboi.com/sql/basics/aggregation#q-min-max)
- 🟡 [Why does SUM sometimes return NULL instead of 0?](https://interview-prep.coderboi.com/sql/basics/aggregation#q-sum-null-result)
- 🟡 [Can you group by a computed expression?](https://interview-prep.coderboi.com/sql/basics/aggregation#q-group-by-expression)
- 🔴 [What do GROUPING SETS, ROLLUP and CUBE do?](https://interview-prep.coderboi.com/sql/basics/aggregation#q-rollup-cube)
- 🟡 [What is the FILTER clause on an aggregate?](https://interview-prep.coderboi.com/sql/basics/aggregation#q-filter-clause)
- 🔴 [How do you avoid double-counting when aggregating over joins?](https://interview-prep.coderboi.com/sql/basics/aggregation#q-aggregate-over-join)

[Full answers with code examples →](https://interview-prep.coderboi.com/sql/basics/aggregation)

### Set Operations

- 🟢 [What are SQL set operations?](https://interview-prep.coderboi.com/sql/basics/set-operations#q-what-are-set-operations)
- 🟢 [What is the difference between UNION and UNION ALL?](https://interview-prep.coderboi.com/sql/basics/set-operations#q-union-vs-union-all)
- 🟡 [What rules must the queries in a UNION satisfy?](https://interview-prep.coderboi.com/sql/basics/set-operations#q-column-compatibility)
- 🟡 [What does INTERSECT do?](https://interview-prep.coderboi.com/sql/basics/set-operations#q-intersect)
- 🟡 [What do EXCEPT and MINUS do?](https://interview-prep.coderboi.com/sql/basics/set-operations#q-except-minus)
- 🟡 [How do set operations treat NULLs in deduplication?](https://interview-prep.coderboi.com/sql/basics/set-operations#q-union-null-handling)
- 🟡 [How do you sort or limit the result of a UNION?](https://interview-prep.coderboi.com/sql/basics/set-operations#q-order-by-with-union)
- 🟢 [When do you use UNION instead of a JOIN?](https://interview-prep.coderboi.com/sql/basics/set-operations#q-union-vs-join)
- 🟡 [Why is UNION ALL faster than UNION?](https://interview-prep.coderboi.com/sql/basics/set-operations#q-union-performance)
- 🔴 [How do you emulate INTERSECT or EXCEPT without native support?](https://interview-prep.coderboi.com/sql/basics/set-operations#q-emulate-intersect-mysql)
- 🔴 [What is the precedence of set operators when you chain them?](https://interview-prep.coderboi.com/sql/basics/set-operations#q-precedence-set-ops)
- 🟢 [Is there a difference between UNION and UNION DISTINCT?](https://interview-prep.coderboi.com/sql/basics/set-operations#q-union-distinct-keyword)
- 🟡 [How do you tag which source each UNION row came from?](https://interview-prep.coderboi.com/sql/basics/set-operations#q-combining-different-tables)
- 🟡 [Is SELECT DISTINCT the same as UNION for one query?](https://interview-prep.coderboi.com/sql/basics/set-operations#q-distinct-vs-union)
- 🔴 [What happens when column types differ across a UNION?](https://interview-prep.coderboi.com/sql/basics/set-operations#q-type-coercion-union)

[Full answers with code examples →](https://interview-prep.coderboi.com/sql/basics/set-operations)

---

## Subqueries

CTEs vs subqueries vs temp tables — know when each is appropriate and how they differ in readability and performance.

### Subqueries

- 🟢 [What is a subquery in SQL?](https://interview-prep.coderboi.com/sql/subqueries/subqueries#q-what-is-a-subquery)
- 🟢 [What are the main types of subqueries?](https://interview-prep.coderboi.com/sql/subqueries/subqueries#q-types-of-subqueries)
- 🟢 [What is a scalar subquery and where can you use it?](https://interview-prep.coderboi.com/sql/subqueries/subqueries#q-scalar-subquery)
- 🟡 [What is a correlated subquery?](https://interview-prep.coderboi.com/sql/subqueries/subqueries#q-correlated-subquery)
- 🟡 [What is the difference between a correlated and a non-correlated subquery?](https://interview-prep.coderboi.com/sql/subqueries/subqueries#q-correlated-vs-non-correlated)
- 🟡 [What is the difference between IN and EXISTS?](https://interview-prep.coderboi.com/sql/subqueries/subqueries#q-in-vs-exists)
- 🔴 [Why can NOT IN behave unexpectedly with NULL values?](https://interview-prep.coderboi.com/sql/subqueries/subqueries#q-not-in-null-trap)
- 🟡 [What do the ANY and ALL operators do with subqueries?](https://interview-prep.coderboi.com/sql/subqueries/subqueries#q-any-all-operators)
- 🟢 [How are subqueries used in the WHERE clause?](https://interview-prep.coderboi.com/sql/subqueries/subqueries#q-subquery-in-where)
- 🟡 [How do you use a subquery in the SELECT list?](https://interview-prep.coderboi.com/sql/subqueries/subqueries#q-subquery-in-select)
- 🟡 [What is a derived table (subquery in the FROM clause)?](https://interview-prep.coderboi.com/sql/subqueries/subqueries#q-derived-table)
- 🟡 [When should you use a subquery versus a join?](https://interview-prep.coderboi.com/sql/subqueries/subqueries#q-subquery-vs-join)
- 🟡 [What are nested subqueries?](https://interview-prep.coderboi.com/sql/subqueries/subqueries#q-nested-subqueries)
- 🟢 [Why does "subquery returns more than one row" error occur?](https://interview-prep.coderboi.com/sql/subqueries/subqueries#q-subquery-returns-multiple-rows-error)
- 🟡 [In what order are subqueries executed?](https://interview-prep.coderboi.com/sql/subqueries/subqueries#q-subquery-execution-order)
- 🔴 [How can you improve the performance of a correlated subquery?](https://interview-prep.coderboi.com/sql/subqueries/subqueries#q-correlated-subquery-performance)
- 🟡 [Can you use a subquery in the HAVING clause?](https://interview-prep.coderboi.com/sql/subqueries/subqueries#q-subquery-in-having)
- 🟡 [Can subqueries be used in INSERT, UPDATE, and DELETE statements?](https://interview-prep.coderboi.com/sql/subqueries/subqueries#q-subquery-with-insert-update-delete)
- 🟡 [What is the difference between a subquery and a CTE?](https://interview-prep.coderboi.com/sql/subqueries/subqueries#q-subquery-vs-cte)

[Full answers with code examples →](https://interview-prep.coderboi.com/sql/subqueries/subqueries)

### Common Table Expressions (CTEs)

- 🟢 [What is a Common Table Expression (CTE)?](https://interview-prep.coderboi.com/sql/subqueries/ctes#q-what-is-a-cte)
- 🟢 [What is the syntax of a CTE?](https://interview-prep.coderboi.com/sql/subqueries/ctes#q-cte-syntax)
- 🟡 [What is the difference between a CTE and a subquery?](https://interview-prep.coderboi.com/sql/subqueries/ctes#q-cte-vs-subquery)
- 🟡 [What is the difference between a CTE and a view?](https://interview-prep.coderboi.com/sql/subqueries/ctes#q-cte-vs-view)
- 🟡 [Can you define multiple CTEs in one query?](https://interview-prep.coderboi.com/sql/subqueries/ctes#q-multiple-ctes)
- 🟡 [How do you chain CTEs to build a multi-step pipeline?](https://interview-prep.coderboi.com/sql/subqueries/ctes#q-cte-chaining)
- 🔴 [What is a recursive CTE?](https://interview-prep.coderboi.com/sql/subqueries/ctes#q-recursive-cte)
- 🔴 [What are the two parts of a recursive CTE?](https://interview-prep.coderboi.com/sql/subqueries/ctes#q-recursive-cte-parts)
- 🔴 [How do you prevent an infinite loop in a recursive CTE?](https://interview-prep.coderboi.com/sql/subqueries/ctes#q-recursive-cte-infinite-loop)
- 🟡 [Can a CTE be referenced multiple times in the same query?](https://interview-prep.coderboi.com/sql/subqueries/ctes#q-cte-multiple-references)
- 🔴 [Are CTEs materialized or inlined?](https://interview-prep.coderboi.com/sql/subqueries/ctes#q-cte-materialization)
- 🔴 [Do CTEs improve query performance?](https://interview-prep.coderboi.com/sql/subqueries/ctes#q-cte-performance)
- 🟡 [Can CTEs be used with INSERT, UPDATE, and DELETE?](https://interview-prep.coderboi.com/sql/subqueries/ctes#q-cte-in-update-delete)
- 🟡 [Why are CTEs often paired with window functions?](https://interview-prep.coderboi.com/sql/subqueries/ctes#q-cte-window-functions)
- 🟢 [What is the scope of a CTE?](https://interview-prep.coderboi.com/sql/subqueries/ctes#q-cte-scope)
- 🟢 [How do you rename a CTE's output columns?](https://interview-prep.coderboi.com/sql/subqueries/ctes#q-cte-column-aliasing)
- 🟡 [What is the difference between a CTE and a temporary table?](https://interview-prep.coderboi.com/sql/subqueries/ctes#q-cte-vs-temp-table)
- 🟡 [What are common use cases for recursive CTEs?](https://interview-prep.coderboi.com/sql/subqueries/ctes#q-cte-recursive-use-cases)
- 🟡 [When should you avoid using a CTE?](https://interview-prep.coderboi.com/sql/subqueries/ctes#q-when-not-to-use-cte)

[Full answers with code examples →](https://interview-prep.coderboi.com/sql/subqueries/ctes)

---

## Window Functions

Window functions are the gap between intermediate and advanced SQL. PARTITION BY, ORDER BY within OVER, and frame clauses (ROWS vs RANGE) are worth mastering completely.

### Window Function Basics

- 🟢 [What is a window function in SQL?](https://interview-prep.coderboi.com/sql/window-functions/window-basics#q-what-is-a-window-function)
- 🟢 [What does the OVER clause do?](https://interview-prep.coderboi.com/sql/window-functions/window-basics#q-over-clause)
- 🟡 [What is the difference between a window function and GROUP BY?](https://interview-prep.coderboi.com/sql/window-functions/window-basics#q-window-vs-group-by)
- 🟢 [What does PARTITION BY do in a window function?](https://interview-prep.coderboi.com/sql/window-functions/window-basics#q-partition-by)
- 🟡 [How does PARTITION BY differ from GROUP BY?](https://interview-prep.coderboi.com/sql/window-functions/window-basics#q-partition-by-vs-group-by)
- 🟡 [What is the role of ORDER BY inside the OVER clause?](https://interview-prep.coderboi.com/sql/window-functions/window-basics#q-order-by-in-over)
- 🟡 [How do you compute a running total with a window function?](https://interview-prep.coderboi.com/sql/window-functions/window-basics#q-running-total)
- 🟢 [Can regular aggregate functions be used as window functions?](https://interview-prep.coderboi.com/sql/window-functions/window-basics#q-window-aggregate-functions)
- 🟡 [What are the main categories of window functions?](https://interview-prep.coderboi.com/sql/window-functions/window-basics#q-ranking-vs-aggregate-windows)
- 🔴 [In which clauses can window functions be used?](https://interview-prep.coderboi.com/sql/window-functions/window-basics#q-where-window-functions-allowed)
- 🔴 [At what point are window functions evaluated in query processing?](https://interview-prep.coderboi.com/sql/window-functions/window-basics#q-logical-processing-order)
- 🟡 [What is a named window (the WINDOW clause)?](https://interview-prep.coderboi.com/sql/window-functions/window-basics#q-named-window)
- 🟡 [Can you use DISTINCT inside a window function?](https://interview-prep.coderboi.com/sql/window-functions/window-basics#q-distinct-with-window)
- 🔴 [What are the performance considerations of window functions?](https://interview-prep.coderboi.com/sql/window-functions/window-basics#q-window-function-performance)
- 🟡 [Why are window functions preferred over self-joins for analytics?](https://interview-prep.coderboi.com/sql/window-functions/window-basics#q-window-vs-self-join)
- 🔴 [How can you conditionally aggregate within a window?](https://interview-prep.coderboi.com/sql/window-functions/window-basics#q-filter-clause-window)
- 🟢 [What does an empty OVER() clause mean?](https://interview-prep.coderboi.com/sql/window-functions/window-basics#q-empty-over-clause)
- 🟡 [How do you filter rows based on a window function's result?](https://interview-prep.coderboi.com/sql/window-functions/window-basics#q-combining-window-with-where)

[Full answers with code examples →](https://interview-prep.coderboi.com/sql/window-functions/window-basics)

### Ranking Functions

- 🟢 [What are ranking window functions?](https://interview-prep.coderboi.com/sql/window-functions/ranking-functions#q-what-are-ranking-functions)
- 🟢 [What does ROW_NUMBER() do?](https://interview-prep.coderboi.com/sql/window-functions/ranking-functions#q-row-number)
- 🟡 [What is the difference between RANK() and DENSE_RANK()?](https://interview-prep.coderboi.com/sql/window-functions/ranking-functions#q-rank-vs-dense-rank)
- 🟡 [How does ROW_NUMBER() differ from RANK() and DENSE_RANK()?](https://interview-prep.coderboi.com/sql/window-functions/ranking-functions#q-row-number-vs-rank)
- 🟡 [What does NTILE() do?](https://interview-prep.coderboi.com/sql/window-functions/ranking-functions#q-ntile)
- 🔴 [What does PERCENT_RANK() compute?](https://interview-prep.coderboi.com/sql/window-functions/ranking-functions#q-percent-rank)
- 🔴 [What does CUME_DIST() compute and how does it differ from PERCENT_RANK()?](https://interview-prep.coderboi.com/sql/window-functions/ranking-functions#q-cume-dist)
- 🟢 [Why do ranking functions require an ORDER BY in the OVER clause?](https://interview-prep.coderboi.com/sql/window-functions/ranking-functions#q-ranking-requires-order-by)
- 🟡 [How do you select the top N rows per group?](https://interview-prep.coderboi.com/sql/window-functions/ranking-functions#q-top-n-per-group)
- 🟡 [How do you find the Nth highest value using ranking functions?](https://interview-prep.coderboi.com/sql/window-functions/ranking-functions#q-nth-highest-value)
- 🟡 [How do you remove duplicate rows using ROW_NUMBER()?](https://interview-prep.coderboi.com/sql/window-functions/ranking-functions#q-deduplication-with-row-number)
- 🟡 [How can ROW_NUMBER() be used for pagination?](https://interview-prep.coderboi.com/sql/window-functions/ranking-functions#q-pagination-with-row-number)
- 🟡 [How do you make ROW_NUMBER() deterministic when ordering values tie?](https://interview-prep.coderboi.com/sql/window-functions/ranking-functions#q-ranking-tie-breaking)
- 🟢 [How does PARTITION BY affect ranking functions?](https://interview-prep.coderboi.com/sql/window-functions/ranking-functions#q-rank-with-partition)
- 🟡 [Why can't you filter directly on a ranking function in WHERE?](https://interview-prep.coderboi.com/sql/window-functions/ranking-functions#q-filtering-on-rank)
- 🔴 [What happens with NTILE() when rows don't divide evenly?](https://interview-prep.coderboi.com/sql/window-functions/ranking-functions#q-ntile-uneven-buckets)
- 🟡 [How do you choose between ROW_NUMBER, RANK, and DENSE_RANK?](https://interview-prep.coderboi.com/sql/window-functions/ranking-functions#q-choosing-ranking-function)
- 🔴 [How can ranking/distribution functions help compute a median?](https://interview-prep.coderboi.com/sql/window-functions/ranking-functions#q-median-with-percentile)

[Full answers with code examples →](https://interview-prep.coderboi.com/sql/window-functions/ranking-functions)

### Frames & Offset Functions

- 🟡 [What is a window frame?](https://interview-prep.coderboi.com/sql/window-functions/frames-and-offsets#q-what-is-a-window-frame)
- 🔴 [What is the difference between ROWS and RANGE in a frame?](https://interview-prep.coderboi.com/sql/window-functions/frames-and-offsets#q-rows-vs-range)
- 🔴 [What is the default window frame when you specify ORDER BY but no frame?](https://interview-prep.coderboi.com/sql/window-functions/frames-and-offsets#q-default-frame)
- 🟡 [What is the window frame when there is no ORDER BY?](https://interview-prep.coderboi.com/sql/window-functions/frames-and-offsets#q-no-order-by-frame)
- 🔴 [What are the possible frame boundary keywords?](https://interview-prep.coderboi.com/sql/window-functions/frames-and-offsets#q-frame-boundaries)
- 🟡 [How do you compute a moving average?](https://interview-prep.coderboi.com/sql/window-functions/frames-and-offsets#q-moving-average)
- 🟢 [What does the LAG() function do?](https://interview-prep.coderboi.com/sql/window-functions/frames-and-offsets#q-lag-function)
- 🟢 [What does the LEAD() function do?](https://interview-prep.coderboi.com/sql/window-functions/frames-and-offsets#q-lead-function)
- 🟡 [What are the optional arguments of LAG() and LEAD()?](https://interview-prep.coderboi.com/sql/window-functions/frames-and-offsets#q-lag-lead-offset-default)
- 🟡 [What do FIRST_VALUE() and LAST_VALUE() return?](https://interview-prep.coderboi.com/sql/window-functions/frames-and-offsets#q-first-value-last-value)
- 🔴 [Why does LAST_VALUE() often return the current row instead of the last?](https://interview-prep.coderboi.com/sql/window-functions/frames-and-offsets#q-last-value-frame-gotcha)
- 🟡 [What does NTH_VALUE() do?](https://interview-prep.coderboi.com/sql/window-functions/frames-and-offsets#q-nth-value)
- 🟡 [How does the frame turn an aggregate into a running vs windowed total?](https://interview-prep.coderboi.com/sql/window-functions/frames-and-offsets#q-running-total-vs-frame)
- 🟡 [Why use LAG/LEAD instead of a self-join for row comparisons?](https://interview-prep.coderboi.com/sql/window-functions/frames-and-offsets#q-lag-lead-vs-self-join)
- 🔴 [How do offset/ranking functions solve gaps-and-islands problems?](https://interview-prep.coderboi.com/sql/window-functions/frames-and-offsets#q-gaps-and-islands)
- 🔴 [Can RANGE frames use intervals (e.g. time-based windows)?](https://interview-prep.coderboi.com/sql/window-functions/frames-and-offsets#q-frame-with-range-interval)
- 🟡 [How do LAG/LEAD and FIRST_VALUE handle NULLs and partition edges?](https://interview-prep.coderboi.com/sql/window-functions/frames-and-offsets#q-offset-functions-null-handling)
- 🟡 [How do frames interact with PARTITION BY?](https://interview-prep.coderboi.com/sql/window-functions/frames-and-offsets#q-combining-frames-with-partition)

[Full answers with code examples →](https://interview-prep.coderboi.com/sql/window-functions/frames-and-offsets)

---

## DML

INSERT/UPDATE/DELETE basics plus views — know when a view is appropriate vs when it becomes a performance trap.

### INSERT, UPDATE & DELETE

- 🟢 [What is the syntax for inserting a row into a table?](https://interview-prep.coderboi.com/sql/dml/insert-update-delete#q-basic-insert)
- 🟢 [How do you insert rows from another table?](https://interview-prep.coderboi.com/sql/dml/insert-update-delete#q-insert-select)
- 🟡 [What is an UPSERT and how do you write one in SQL?](https://interview-prep.coderboi.com/sql/dml/insert-update-delete#q-upsert-on-conflict)
- 🟢 [How do you silently ignore a duplicate row on INSERT?](https://interview-prep.coderboi.com/sql/dml/insert-update-delete#q-on-conflict-do-nothing)
- 🟢 [What is the syntax for updating rows in SQL?](https://interview-prep.coderboi.com/sql/dml/insert-update-delete#q-basic-update)
- 🟡 [How do you update rows using values from another table?](https://interview-prep.coderboi.com/sql/dml/insert-update-delete#q-update-join)
- 🟢 [What is the DELETE statement and what happens if you omit WHERE?](https://interview-prep.coderboi.com/sql/dml/insert-update-delete#q-basic-delete)
- 🟡 [How do you delete rows based on a condition in a related table?](https://interview-prep.coderboi.com/sql/dml/insert-update-delete#q-delete-join)
- 🟡 [What does the RETURNING clause do in Postgres?](https://interview-prep.coderboi.com/sql/dml/insert-update-delete#q-returning-clause)
- 🟡 [What is soft delete and how is it implemented in SQL?](https://interview-prep.coderboi.com/sql/dml/insert-update-delete#q-soft-delete)
- 🔴 [How do you safely delete millions of rows from a large table?](https://interview-prep.coderboi.com/sql/dml/insert-update-delete#q-batch-delete-large-table)
- 🟢 [When should you use TRUNCATE instead of DELETE?](https://interview-prep.coderboi.com/sql/dml/insert-update-delete#q-truncate-vs-delete)
- 🟡 [What is the difference between UPDATE and REPLACE in MySQL?](https://interview-prep.coderboi.com/sql/dml/insert-update-delete#q-update-vs-replace)
- 🟡 [How do you update a column to different values based on a condition?](https://interview-prep.coderboi.com/sql/dml/insert-update-delete#q-conditional-update)
- 🔴 [How do you use a CTE with INSERT, UPDATE, or DELETE?](https://interview-prep.coderboi.com/sql/dml/insert-update-delete#q-cte-with-dml)

[Full answers with code examples →](https://interview-prep.coderboi.com/sql/dml/insert-update-delete)

### Views

- 🟢 [What is a view in SQL?](https://interview-prep.coderboi.com/sql/dml/views#q-what-is-view)
- 🟢 [How do you create, replace, and drop a view?](https://interview-prep.coderboi.com/sql/dml/views#q-create-replace-view)
- 🟢 [What are the main use cases for views?](https://interview-prep.coderboi.com/sql/dml/views#q-view-use-cases)
- 🟡 [Can you INSERT, UPDATE, or DELETE through a view?](https://interview-prep.coderboi.com/sql/dml/views#q-updatable-views)
- 🟡 [What does WITH CHECK OPTION do on a view?](https://interview-prep.coderboi.com/sql/dml/views#q-with-check-option)
- 🟡 [When should you use a view vs a CTE?](https://interview-prep.coderboi.com/sql/dml/views#q-view-vs-cte)
- 🟡 [What is the difference between a view and a materialized view?](https://interview-prep.coderboi.com/sql/dml/views#q-materialized-view-vs-view)
- 🟡 [Do views have a performance cost compared to writing the query inline?](https://interview-prep.coderboi.com/sql/dml/views#q-view-performance)
- 🟡 [How do views implement row-level security?](https://interview-prep.coderboi.com/sql/dml/views#q-security-view)
- 🔴 [What happens to a view when the underlying table schema changes?](https://interview-prep.coderboi.com/sql/dml/views#q-schema-changes-view)
- 🔴 [Can a view be recursive?](https://interview-prep.coderboi.com/sql/dml/views#q-recursive-view)
- 🔴 [What is an indexed view in SQL Server?](https://interview-prep.coderboi.com/sql/dml/views#q-indexed-view-sql-server)
- 🔴 [When would you use a table-valued function instead of a view?](https://interview-prep.coderboi.com/sql/dml/views#q-view-vs-table-function)
- 🟡 [How do you find which tables and columns a view depends on?](https://interview-prep.coderboi.com/sql/dml/views#q-view-dependencies)
- 🟡 [What does SCHEMABINDING do on a view in SQL Server?](https://interview-prep.coderboi.com/sql/dml/views#q-view-schemabinding)

[Full answers with code examples →](https://interview-prep.coderboi.com/sql/dml/views)

---

## Schema

Normalization, constraints, and DDL. Know 1NF through 3NF and be able to explain when denormalization makes sense.

### Data Types

- 🟢 [Why does picking the right data type matter?](https://interview-prep.coderboi.com/sql/schema/data-types#q-why-types-matter)
- 🟢 [What are the main integer types and when do you choose each?](https://interview-prep.coderboi.com/sql/schema/data-types#q-integer-types)
- 🟡 [What is the difference between NUMERIC/DECIMAL and FLOAT/REAL?](https://interview-prep.coderboi.com/sql/schema/data-types#q-numeric-vs-float)
- 🟢 [What is the difference between CHAR, VARCHAR, and TEXT?](https://interview-prep.coderboi.com/sql/schema/data-types#q-char-vs-varchar-vs-text)
- 🟡 [What date and time types does SQL offer and how do they differ?](https://interview-prep.coderboi.com/sql/schema/data-types#q-date-time-types)
- 🟢 [How do databases handle boolean values?](https://interview-prep.coderboi.com/sql/schema/data-types#q-boolean-type)
- 🟡 [What is NULL and how does three-valued logic work in SQL?](https://interview-prep.coderboi.com/sql/schema/data-types#q-null-semantics)
- 🟡 [What are UUIDs and when should you use them as primary keys?](https://interview-prep.coderboi.com/sql/schema/data-types#q-uuid-type)
- 🟡 [When should you store data as JSON in a relational column?](https://interview-prep.coderboi.com/sql/schema/data-types#q-json-type)
- 🟡 [What are ENUM types and what are their trade-offs?](https://interview-prep.coderboi.com/sql/schema/data-types#q-enum-type)
- 🟡 [How do you choose precision and scale for NUMERIC(p, s)?](https://interview-prep.coderboi.com/sql/schema/data-types#q-choosing-numeric-precision)
- 🟡 [What is the difference between SERIAL and GENERATED AS IDENTITY?](https://interview-prep.coderboi.com/sql/schema/data-types#q-serial-vs-identity)
- 🟡 [What is the best way to store monetary values in SQL?](https://interview-prep.coderboi.com/sql/schema/data-types#q-storing-money)
- 🟢 [When would you store binary data in a SQL column?](https://interview-prep.coderboi.com/sql/schema/data-types#q-binary-types)
- 🟡 [What is implicit type casting and why can it be dangerous?](https://interview-prep.coderboi.com/sql/schema/data-types#q-implicit-vs-explicit-casting)
- 🔴 [When should you use array columns (Postgres) instead of a child table?](https://interview-prep.coderboi.com/sql/schema/data-types#q-array-types)

[Full answers with code examples →](https://interview-prep.coderboi.com/sql/schema/data-types)

### DDL — Creating & Altering Tables

- 🟢 [What is DDL and how does it differ from DML?](https://interview-prep.coderboi.com/sql/schema/ddl#q-what-is-ddl)
- 🟢 [What are the essential parts of a CREATE TABLE statement?](https://interview-prep.coderboi.com/sql/schema/ddl#q-create-table-basics)
- 🟡 [What can you do with ALTER TABLE and what are the risks?](https://interview-prep.coderboi.com/sql/schema/ddl#q-alter-table)
- 🟢 [What is the difference between DROP TABLE and TRUNCATE?](https://interview-prep.coderboi.com/sql/schema/ddl#q-drop-vs-truncate)
- 🟡 [What is a SQL schema (namespace) and why use one?](https://interview-prep.coderboi.com/sql/schema/ddl#q-schemas-namespacing)
- 🟡 [What is a sequence and how does it relate to auto-increment columns?](https://interview-prep.coderboi.com/sql/schema/ddl#q-sequences)
- 🟡 [What is the DDL to create and drop an index, and when does CREATE INDEX CONCURRENTLY matter?](https://interview-prep.coderboi.com/sql/schema/ddl#q-create-index-ddl)
- 🟡 [What are temporary tables and when should you use them?](https://interview-prep.coderboi.com/sql/schema/ddl#q-temp-tables)
- 🔴 [Can DDL statements be run inside a transaction and rolled back?](https://interview-prep.coderboi.com/sql/schema/ddl#q-ddl-in-transactions)
- 🟢 [What does CREATE TABLE IF NOT EXISTS do and why is it useful in migrations?](https://interview-prep.coderboi.com/sql/schema/ddl#q-if-not-exists)
- 🟢 [How do you rename a table in SQL?](https://interview-prep.coderboi.com/sql/schema/ddl#q-rename-table)
- 🔴 [What are generated (computed) columns?](https://interview-prep.coderboi.com/sql/schema/ddl#q-generated-columns)
- 🔴 [How do you create a partitioned table in Postgres?](https://interview-prep.coderboi.com/sql/schema/ddl#q-partitioning-ddl)
- 🟡 [How do you create and replace a view?](https://interview-prep.coderboi.com/sql/schema/ddl#q-view-ddl)
- 🔴 [What is a materialized view and how does it differ from a regular view?](https://interview-prep.coderboi.com/sql/schema/ddl#q-materialized-view)

[Full answers with code examples →](https://interview-prep.coderboi.com/sql/schema/ddl)

### Constraints & Integrity

- 🟢 [What is a constraint and why use one?](https://interview-prep.coderboi.com/sql/schema/constraints#q-what-is-constraint)
- 🟢 [What is a PRIMARY KEY constraint?](https://interview-prep.coderboi.com/sql/schema/constraints#q-primary-key)
- 🟢 [What is a FOREIGN KEY constraint and what does it enforce?](https://interview-prep.coderboi.com/sql/schema/constraints#q-foreign-key)
- 🟡 [What are ON DELETE / ON UPDATE referential actions on a foreign key?](https://interview-prep.coderboi.com/sql/schema/constraints#q-referential-actions)
- 🟢 [What is a UNIQUE constraint and how does it differ from a PRIMARY KEY?](https://interview-prep.coderboi.com/sql/schema/constraints#q-unique-constraint)
- 🟡 [What is a CHECK constraint and what can it express?](https://interview-prep.coderboi.com/sql/schema/constraints#q-check-constraint)
- 🟢 [What does NOT NULL enforce and when should you omit it?](https://interview-prep.coderboi.com/sql/schema/constraints#q-not-null-constraint)
- 🔴 [What are deferrable constraints and when do you need them?](https://interview-prep.coderboi.com/sql/schema/constraints#q-deferrable-constraints)
- 🔴 [What is an exclusion constraint in Postgres?](https://interview-prep.coderboi.com/sql/schema/constraints#q-exclusion-constraint)
- 🟡 [Why should you name your constraints explicitly?](https://interview-prep.coderboi.com/sql/schema/constraints#q-naming-constraints)
- 🔴 [What is a partial unique index and when does it replace a constraint?](https://interview-prep.coderboi.com/sql/schema/constraints#q-partial-unique-index)
- 🟡 [Can you disable a constraint temporarily and should you?](https://interview-prep.coderboi.com/sql/schema/constraints#q-disable-enable-constraint)
- 🟡 [How does a UNIQUE constraint relate to a unique index?](https://interview-prep.coderboi.com/sql/schema/constraints#q-index-vs-constraint)
- 🟢 [What error do you get when a constraint is violated, and how do you handle it?](https://interview-prep.coderboi.com/sql/schema/constraints#q-constraint-violations-errors)
- 🟢 [What is the difference between a column-level and a table-level constraint?](https://interview-prep.coderboi.com/sql/schema/constraints#q-table-vs-column-constraint)

[Full answers with code examples →](https://interview-prep.coderboi.com/sql/schema/constraints)

### Normalization

- 🟢 [What is database normalization and why does it matter?](https://interview-prep.coderboi.com/sql/schema/normalization#q-what-is-normalization)
- 🟡 [What are the three update anomalies normalization prevents?](https://interview-prep.coderboi.com/sql/schema/normalization#q-update-anomalies)
- 🟢 [What is First Normal Form (1NF)?](https://interview-prep.coderboi.com/sql/schema/normalization#q-first-normal-form)
- 🟡 [What is a functional dependency?](https://interview-prep.coderboi.com/sql/schema/normalization#q-functional-dependency)
- 🟡 [What is Second Normal Form (2NF) and what does it fix?](https://interview-prep.coderboi.com/sql/schema/normalization#q-second-normal-form)
- 🟡 [What is Third Normal Form (3NF) and what does it eliminate?](https://interview-prep.coderboi.com/sql/schema/normalization#q-third-normal-form)
- 🔴 [What is Boyce-Codd Normal Form (BCNF) and how does it differ from 3NF?](https://interview-prep.coderboi.com/sql/schema/normalization#q-bcnf)
- 🟡 [What is denormalization and when is it justified?](https://interview-prep.coderboi.com/sql/schema/normalization#q-denormalization)
- 🟡 [What is a star schema and how does it differ from a normalized OLTP schema?](https://interview-prep.coderboi.com/sql/schema/normalization#q-star-schema)
- 🟡 [How do you balance normalization and query performance in practice?](https://interview-prep.coderboi.com/sql/schema/normalization#q-normalization-vs-performance)
- 🟡 [What is the difference between a surrogate key and a natural key?](https://interview-prep.coderboi.com/sql/schema/normalization#q-surrogate-vs-natural-key)
- 🔴 [What is Fourth Normal Form (4NF) and what does it address?](https://interview-prep.coderboi.com/sql/schema/normalization#q-fourth-normal-form)
- 🟢 [How do you quickly check if a table is in 3NF?](https://interview-prep.coderboi.com/sql/schema/normalization#q-normalization-checklist)
- 🟢 [What is a junction (bridge) table and when do you use one?](https://interview-prep.coderboi.com/sql/schema/normalization#q-junction-table)
- 🟡 [When should you deliberately stop normalizing?](https://interview-prep.coderboi.com/sql/schema/normalization#q-when-not-to-normalize)

[Full answers with code examples →](https://interview-prep.coderboi.com/sql/schema/normalization)

---

## Functions

String, numeric, date, and NULL handling functions — the practical toolkit for manipulating data in queries.

### String & Numeric Functions

- 🟢 [How do you concatenate strings in SQL?](https://interview-prep.coderboi.com/sql/functions/string-numeric-functions#q-concat)
- 🟢 [How do you extract a part of a string?](https://interview-prep.coderboi.com/sql/functions/string-numeric-functions#q-substring)
- 🟢 [How do you change string case in SQL?](https://interview-prep.coderboi.com/sql/functions/string-numeric-functions#q-upper-lower)
- 🟢 [How do you remove whitespace or specific characters from a string?](https://interview-prep.coderboi.com/sql/functions/string-numeric-functions#q-trim)
- 🟢 [How do you replace occurrences of a substring?](https://interview-prep.coderboi.com/sql/functions/string-numeric-functions#q-replace)
- 🟢 [How do you get the length of a string in SQL?](https://interview-prep.coderboi.com/sql/functions/string-numeric-functions#q-length)
- 🟡 [How do you search for a substring within a string?](https://interview-prep.coderboi.com/sql/functions/string-numeric-functions#q-string-search)
- 🟢 [How do you round numeric values in SQL?](https://interview-prep.coderboi.com/sql/functions/string-numeric-functions#q-round-ceil-floor)
- 🟢 [What are MOD, ABS, and POWER and how do you use them?](https://interview-prep.coderboi.com/sql/functions/string-numeric-functions#q-mod-abs-power)
- 🟡 [How do you convert a value from one data type to another?](https://interview-prep.coderboi.com/sql/functions/string-numeric-functions#q-cast-convert)
- 🟢 [How do you pad a string to a fixed length?](https://interview-prep.coderboi.com/sql/functions/string-numeric-functions#q-string-padding)
- 🟡 [How do you format numbers and dates as strings?](https://interview-prep.coderboi.com/sql/functions/string-numeric-functions#q-format-to-char)
- 🟡 [How do you split a delimited string in SQL?](https://interview-prep.coderboi.com/sql/functions/string-numeric-functions#q-string-split)
- 🟡 [How do you aggregate multiple rows into a single string?](https://interview-prep.coderboi.com/sql/functions/string-numeric-functions#q-aggregate-string)
- 🟡 [How do you use regular expressions in SQL?](https://interview-prep.coderboi.com/sql/functions/string-numeric-functions#q-regex-functions)

[Full answers with code examples →](https://interview-prep.coderboi.com/sql/functions/string-numeric-functions)

### Date & Time Functions

- 🟢 [How do you get the current date and time in SQL?](https://interview-prep.coderboi.com/sql/functions/date-functions#q-current-date-time)
- 🟢 [How do you add or subtract time from a date?](https://interview-prep.coderboi.com/sql/functions/date-functions#q-date-arithmetic)
- 🟡 [What does DATE_TRUNC do and how is it used for grouping?](https://interview-prep.coderboi.com/sql/functions/date-functions#q-date-trunc)
- 🟢 [How do you extract a specific part of a date (year, month, day)?](https://interview-prep.coderboi.com/sql/functions/date-functions#q-extract)
- 🟡 [How do you calculate the difference between two dates?](https://interview-prep.coderboi.com/sql/functions/date-functions#q-age-datediff)
- 🟡 [How do you handle timezones when storing and querying timestamps?](https://interview-prep.coderboi.com/sql/functions/date-functions#q-timezone-handling)
- 🟢 [How do you format a date as a string?](https://interview-prep.coderboi.com/sql/functions/date-functions#q-date-format)
- 🔴 [How do you generate a date series to fill gaps in time-series data?](https://interview-prep.coderboi.com/sql/functions/date-functions#q-generate-series)
- 🟡 [What is the INTERVAL type and how do you use it?](https://interview-prep.coderboi.com/sql/functions/date-functions#q-interval-type)
- 🔴 [What is the difference between now() and clock_timestamp() in Postgres?](https://interview-prep.coderboi.com/sql/functions/date-functions#q-now-vs-clock-timestamp)
- 🔴 [How do you efficiently query by time period without slowing down writes?](https://interview-prep.coderboi.com/sql/functions/date-functions#q-date-trunc-index)
- 🔴 [How do you calculate time between consecutive events per user?](https://interview-prep.coderboi.com/sql/functions/date-functions#q-lag-lead-dates)
- 🟢 [How do you construct a date from year, month, and day components?](https://interview-prep.coderboi.com/sql/functions/date-functions#q-make-date)
- 🟢 [How do you calculate a person's age or the time elapsed between two dates?](https://interview-prep.coderboi.com/sql/functions/date-functions#q-age-function)
- 🔴 [How do you find rows where two date ranges overlap?](https://interview-prep.coderboi.com/sql/functions/date-functions#q-date-range-overlap)

[Full answers with code examples →](https://interview-prep.coderboi.com/sql/functions/date-functions)

### Conditional & NULL Functions

- 🟢 [What is the CASE expression and what are its two forms?](https://interview-prep.coderboi.com/sql/functions/conditional-null-functions#q-case-expression)
- 🟢 [What does COALESCE do?](https://interview-prep.coderboi.com/sql/functions/conditional-null-functions#q-coalesce)
- 🟡 [What does NULLIF do and when is it useful?](https://interview-prep.coderboi.com/sql/functions/conditional-null-functions#q-nullif)
- 🟢 [What are IFNULL, NVL, and ISNULL — and how do they compare to COALESCE?](https://interview-prep.coderboi.com/sql/functions/conditional-null-functions#q-ifnull-nvl-isnull)
- 🟢 [What is IIF and when can you use it?](https://interview-prep.coderboi.com/sql/functions/conditional-null-functions#q-iif)
- 🟡 [Why do comparisons with NULL often return unexpected results?](https://interview-prep.coderboi.com/sql/functions/conditional-null-functions#q-null-in-comparisons)
- 🟡 [How does NULL affect aggregate functions?](https://interview-prep.coderboi.com/sql/functions/conditional-null-functions#q-null-in-aggregates)
- 🟡 [What is conditional aggregation and how do you use it?](https://interview-prep.coderboi.com/sql/functions/conditional-null-functions#q-conditional-aggregation)
- 🟢 [What are GREATEST and LEAST?](https://interview-prep.coderboi.com/sql/functions/conditional-null-functions#q-greatest-least)
- 🟡 [How do you compare two values that may both be NULL?](https://interview-prep.coderboi.com/sql/functions/conditional-null-functions#q-null-safe-equals)
- 🔴 [How does three-valued logic affect AND and OR with NULLs?](https://interview-prep.coderboi.com/sql/functions/conditional-null-functions#q-boolean-logic-nulls)
- 🟢 [How do you handle multiple conditional mappings cleanly?](https://interview-prep.coderboi.com/sql/functions/conditional-null-functions#q-decode-decode)
- 🟡 [How do you safely cast a string to a number or date without raising an error?](https://interview-prep.coderboi.com/sql/functions/conditional-null-functions#q-try-convert)
- 🟡 [How can you use CASE in ORDER BY to create custom sort orders?](https://interview-prep.coderboi.com/sql/functions/conditional-null-functions#q-case-in-order-by)
- 🔴 [How do you pivot rows into columns using CASE?](https://interview-prep.coderboi.com/sql/functions/conditional-null-functions#q-pivot-with-case)

[Full answers with code examples →](https://interview-prep.coderboi.com/sql/functions/conditional-null-functions)

---

## Transactions

ACID properties and isolation levels come up in backend interviews. Know what "read committed" vs "serializable" actually means for concurrent reads.

### Transactions & ACID

- 🟢 [What is a database transaction?](https://interview-prep.coderboi.com/sql/transactions/transactions#q-what-is-transaction)
- 🟢 [What are the ACID properties?](https://interview-prep.coderboi.com/sql/transactions/transactions#q-acid-properties)
- 🟢 [What do BEGIN, COMMIT, and ROLLBACK do?](https://interview-prep.coderboi.com/sql/transactions/transactions#q-begin-commit-rollback)
- 🟢 [What is autocommit and how does it affect transactions?](https://interview-prep.coderboi.com/sql/transactions/transactions#q-autocommit)
- 🟡 [What is a SAVEPOINT and when would you use one?](https://interview-prep.coderboi.com/sql/transactions/transactions#q-savepoint)
- 🟡 [What does RELEASE SAVEPOINT do?](https://interview-prep.coderboi.com/sql/transactions/transactions#q-release-savepoint)
- 🟡 [What is an implicit transaction in SQL Server?](https://interview-prep.coderboi.com/sql/transactions/transactions#q-implicit-transaction)
- 🟡 [What is the transaction log (WAL) and why does it matter?](https://interview-prep.coderboi.com/sql/transactions/transactions#q-transaction-log)
- 🟡 [Why are long-running transactions harmful?](https://interview-prep.coderboi.com/sql/transactions/transactions#q-long-running-transactions)
- 🟡 [What is a deadlock and how does the database resolve it?](https://interview-prep.coderboi.com/sql/transactions/transactions#q-deadlock)
- 🔴 [What is the difference between optimistic and pessimistic locking?](https://interview-prep.coderboi.com/sql/transactions/transactions#q-optimistic-vs-pessimistic)
- 🟡 [What does SELECT FOR UPDATE do?](https://interview-prep.coderboi.com/sql/transactions/transactions#q-select-for-update)
- 🔴 [How do you implement a concurrent job queue with SKIP LOCKED?](https://interview-prep.coderboi.com/sql/transactions/transactions#q-skip-locked)
- 🔴 [What is two-phase commit (2PC) and when is it used?](https://interview-prep.coderboi.com/sql/transactions/transactions#q-two-phase-commit)
- 🟡 [What are the most important best practices for writing transactions?](https://interview-prep.coderboi.com/sql/transactions/transactions#q-transaction-best-practices)

[Full answers with code examples →](https://interview-prep.coderboi.com/sql/transactions/transactions)

### Isolation Levels & Concurrency

- 🟢 [What is transaction isolation?](https://interview-prep.coderboi.com/sql/transactions/isolation-concurrency#q-what-is-isolation)
- 🟡 [What are the three read phenomena isolation levels protect against?](https://interview-prep.coderboi.com/sql/transactions/isolation-concurrency#q-read-phenomena)
- 🟢 [What is READ UNCOMMITTED and when (if ever) is it useful?](https://interview-prep.coderboi.com/sql/transactions/isolation-concurrency#q-read-uncommitted)
- 🟢 [What does READ COMMITTED guarantee and what can still go wrong?](https://interview-prep.coderboi.com/sql/transactions/isolation-concurrency#q-read-committed)
- 🟡 [What does REPEATABLE READ guarantee?](https://interview-prep.coderboi.com/sql/transactions/isolation-concurrency#q-repeatable-read)
- 🔴 [What does SERIALIZABLE isolation guarantee?](https://interview-prep.coderboi.com/sql/transactions/isolation-concurrency#q-serializable)
- 🔴 [What is MVCC and how does it enable concurrency without locking reads?](https://interview-prep.coderboi.com/sql/transactions/isolation-concurrency#q-mvcc)
- 🔴 [What is write skew and how does SERIALIZABLE prevent it?](https://interview-prep.coderboi.com/sql/transactions/isolation-concurrency#q-write-skew)
- 🟡 [What is a lost update and how do you prevent it?](https://interview-prep.coderboi.com/sql/transactions/isolation-concurrency#q-lost-update)
- 🟡 [What is a phantom read and what isolation level prevents it?](https://interview-prep.coderboi.com/sql/transactions/isolation-concurrency#q-phantom-read)
- 🔴 [What are gap locks and next-key locks in MySQL InnoDB?](https://interview-prep.coderboi.com/sql/transactions/isolation-concurrency#q-gap-locks)
- 🟢 [What is the default isolation level in Postgres, MySQL, and SQL Server?](https://interview-prep.coderboi.com/sql/transactions/isolation-concurrency#q-default-isolation-levels)
- 🔴 [How should application code handle a serialization failure?](https://interview-prep.coderboi.com/sql/transactions/isolation-concurrency#q-serialization-failure-retry)
- 🔴 [What is snapshot isolation and how does it differ from SERIALIZABLE?](https://interview-prep.coderboi.com/sql/transactions/isolation-concurrency#q-snapshot-isolation)
- 🔴 [What lock modes do databases use and how do they interact?](https://interview-prep.coderboi.com/sql/transactions/isolation-concurrency#q-lock-modes)

[Full answers with code examples →](https://interview-prep.coderboi.com/sql/transactions/isolation-concurrency)

---

## Performance

Indexes are the most-asked SQL performance topic. Know how a B-tree index works, what makes a query use one vs not, and what covering indexes are.

### Indexes

- 🟢 [What is a database index and how does it speed up queries?](https://interview-prep.coderboi.com/sql/performance/indexes#q-what-is-index)
- 🟢 [What is a B-tree index and what kinds of queries does it support?](https://interview-prep.coderboi.com/sql/performance/indexes#q-btree-index)
- 🟡 [What is a composite index and what is the left-prefix rule?](https://interview-prep.coderboi.com/sql/performance/indexes#q-composite-index)
- 🟡 [What is a covering index and how does it eliminate table lookups?](https://interview-prep.coderboi.com/sql/performance/indexes#q-covering-index)
- 🟡 [What is a partial index and when does it help?](https://interview-prep.coderboi.com/sql/performance/indexes#q-partial-index)
- 🟡 [When should you use a hash index instead of a B-tree?](https://interview-prep.coderboi.com/sql/performance/indexes#q-hash-index)
- 🔴 [What is a GIN index and when do you use it in Postgres?](https://interview-prep.coderboi.com/sql/performance/indexes#q-gin-index)
- 🔴 [What is index bloat and how do you fix it?](https://interview-prep.coderboi.com/sql/performance/indexes#q-index-bloat)
- 🟡 [When should you NOT add an index?](https://interview-prep.coderboi.com/sql/performance/indexes#q-when-not-to-index)
- 🟡 [When does the optimizer choose a sequential scan over an index scan?](https://interview-prep.coderboi.com/sql/performance/indexes#q-index-scan-vs-seq-scan)
- 🔴 [What is a functional (expression) index?](https://interview-prep.coderboi.com/sql/performance/indexes#q-expression-index)
- 🟡 [How do you find and remove duplicate or unused indexes?](https://interview-prep.coderboi.com/sql/performance/indexes#q-index-maintenance)
- 🟡 [What is the difference between a clustered and a non-clustered index?](https://interview-prep.coderboi.com/sql/performance/indexes#q-clustered-vs-nonclustered)
- 🟢 [Should you always index a foreign key column?](https://interview-prep.coderboi.com/sql/performance/indexes#q-index-on-foreign-key)
- 🟢 [What index types are available in Postgres and when do you use each?](https://interview-prep.coderboi.com/sql/performance/indexes#q-index-types-summary)

[Full answers with code examples →](https://interview-prep.coderboi.com/sql/performance/indexes)

### Query Optimization

- 🟢 [What does EXPLAIN do and how do you read its output?](https://interview-prep.coderboi.com/sql/performance/query-optimization#q-what-is-explain)
- 🟡 [You see a Seq Scan on a large table — what do you check first?](https://interview-prep.coderboi.com/sql/performance/query-optimization#q-seq-scan-optimization)
- 🟡 [What is the N+1 query problem and how do you fix it in SQL?](https://interview-prep.coderboi.com/sql/performance/query-optimization#q-n-plus-one)
- 🔴 [What are the three join strategies and when does the optimizer choose each?](https://interview-prep.coderboi.com/sql/performance/query-optimization#q-join-strategies)
- 🟡 [What are table statistics and how do you update them?](https://interview-prep.coderboi.com/sql/performance/query-optimization#q-statistics-analyze)
- 🟡 [Why is OFFSET-based pagination slow and what is the alternative?](https://interview-prep.coderboi.com/sql/performance/query-optimization#q-pagination-offset)
- 🟡 [When does a subquery perform worse than a JOIN and how do you fix it?](https://interview-prep.coderboi.com/sql/performance/query-optimization#q-subquery-vs-join)
- 🟡 [How can OR in a WHERE clause hurt performance and how do you fix it?](https://interview-prep.coderboi.com/sql/performance/query-optimization#q-query-rewrite-or)
- 🟢 [Why should you avoid SELECT * in production queries?](https://interview-prep.coderboi.com/sql/performance/query-optimization#q-avoid-select-star)
- 🔴 [Can CTEs hurt query performance and how?](https://interview-prep.coderboi.com/sql/performance/query-optimization#q-cte-performance)
- 🔴 [What is table bloat and how does VACUUM address it?](https://interview-prep.coderboi.com/sql/performance/query-optimization#q-vacuum-and-bloat)
- 🟡 [How do you set and enforce query timeouts in SQL?](https://interview-prep.coderboi.com/sql/performance/query-optimization#q-query-timeout)
- 🟡 [How do you proactively find slow queries and missing indexes in production?](https://interview-prep.coderboi.com/sql/performance/query-optimization#q-missing-index-detection)
- 🔴 [What is partition pruning and how does it improve query performance?](https://interview-prep.coderboi.com/sql/performance/query-optimization#q-partition-pruning)
- 🟡 [What is an Index Only Scan and how do you enable it?](https://interview-prep.coderboi.com/sql/performance/query-optimization#q-index-only-scan)

[Full answers with code examples →](https://interview-prep.coderboi.com/sql/performance/query-optimization)

---

## Security

SQL injection and permissions are must-knows. Know how parameterized queries prevent injection at the driver level.

### Permissions & Roles

- 🟢 [What do GRANT and REVOKE do?](https://interview-prep.coderboi.com/sql/security/permissions#q-grant-revoke)
- 🟢 [What is the principle of least privilege and how does it apply to SQL?](https://interview-prep.coderboi.com/sql/security/permissions#q-least-privilege)
- 🟡 [What are roles and how do they differ from users?](https://interview-prep.coderboi.com/sql/security/permissions#q-roles)
- 🟡 [What does WITH GRANT OPTION do?](https://interview-prep.coderboi.com/sql/security/permissions#q-grant-with-grant-option)
- 🔴 [What is Row-Level Security (RLS) in Postgres?](https://interview-prep.coderboi.com/sql/security/permissions#q-row-level-security)
- 🟡 [How do schema-level permissions work?](https://interview-prep.coderboi.com/sql/security/permissions#q-schema-permissions)
- 🟡 [Can you grant permissions on specific columns rather than whole tables?](https://interview-prep.coderboi.com/sql/security/permissions#q-column-level-grants)
- 🟡 [What are superuser privileges and why should you avoid using them for applications?](https://interview-prep.coderboi.com/sql/security/permissions#q-superuser-privileges)
- 🔴 [How do you audit who changed what in a database?](https://interview-prep.coderboi.com/sql/security/permissions#q-audit-logging)
- 🔴 [Why is the PUBLIC schema dangerous in Postgres and how do you secure it?](https://interview-prep.coderboi.com/sql/security/permissions#q-revoking-public-schema)
- 🟡 [How do you manage database user passwords securely?](https://interview-prep.coderboi.com/sql/security/permissions#q-password-policies)
- 🟡 [How do you restrict which hosts can connect to the database?](https://interview-prep.coderboi.com/sql/security/permissions#q-connection-security)
- 🟡 [How can views be used to implement access control?](https://interview-prep.coderboi.com/sql/security/permissions#q-view-as-security)
- 🟡 [What are default privileges and why do they matter?](https://interview-prep.coderboi.com/sql/security/permissions#q-default-privileges)
- 🟡 [How do you inspect what permissions a user or role currently has?](https://interview-prep.coderboi.com/sql/security/permissions#q-privilege-inspection)

[Full answers with code examples →](https://interview-prep.coderboi.com/sql/security/permissions)

### SQL Injection

- 🟢 [What is SQL injection?](https://interview-prep.coderboi.com/sql/security/sql-injection#q-what-is-sql-injection)
- 🟢 [What are parameterised queries (prepared statements) and why do they prevent injection?](https://interview-prep.coderboi.com/sql/security/sql-injection#q-parameterised-queries)
- 🟡 [Are ORM queries safe from SQL injection by default?](https://interview-prep.coderboi.com/sql/security/sql-injection#q-orm-safety)
- 🟡 [What are the main types of SQL injection attacks?](https://interview-prep.coderboi.com/sql/security/sql-injection#q-injection-types)
- 🔴 [Can stored procedures be vulnerable to SQL injection?](https://interview-prep.coderboi.com/sql/security/sql-injection#q-stored-procedure-injection)
- 🔴 [What is second-order (stored) SQL injection?](https://interview-prep.coderboi.com/sql/security/sql-injection#q-second-order-injection)
- 🟡 [Is input validation sufficient to prevent SQL injection?](https://interview-prep.coderboi.com/sql/security/sql-injection#q-input-validation)
- 🟡 [How do database error messages contribute to SQL injection risk?](https://interview-prep.coderboi.com/sql/security/sql-injection#q-error-messages)
- 🟡 [What role does a Web Application Firewall (WAF) play in preventing SQL injection?](https://interview-prep.coderboi.com/sql/security/sql-injection#q-waf-and-defence-in-depth)
- 🔴 [Does SQL injection also apply to NoSQL databases?](https://interview-prep.coderboi.com/sql/security/sql-injection#q-nosql-injection)
- 🟡 [What is mass assignment and how does it relate to database security?](https://interview-prep.coderboi.com/sql/security/sql-injection#q-orm-mass-assignment)
- 🟡 [How do you detect SQL injection vulnerabilities in an existing codebase?](https://interview-prep.coderboi.com/sql/security/sql-injection#q-detecting-sqli)
- 🔴 [How do you safely handle a dynamic ORDER BY clause?](https://interview-prep.coderboi.com/sql/security/sql-injection#q-dynamic-order-by-injection)
- 🟡 [What is the difference between escaping and parameterising?](https://interview-prep.coderboi.com/sql/security/sql-injection#q-escape-vs-parameterise)
- 🟡 [How does least-privilege database access reduce SQL injection impact?](https://interview-prep.coderboi.com/sql/security/sql-injection#q-least-privilege-sqli)

[Full answers with code examples →](https://interview-prep.coderboi.com/sql/security/sql-injection)

---

## How to Use This

Use the checkboxes as a study tracker — go through each section, click the link to read the full answer, then come back and tick it off. The full answers include:

- A clear written explanation
- A working code example with inline comments
- A "Rule of thumb" line you can actually say out loud in an interview

Full site: [interview-prep.coderboi.com/sql](https://interview-prep.coderboi.com/sql)
