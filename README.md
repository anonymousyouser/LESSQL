# LESSQL Framework Home Page

Here you will find discussions about the LESSQL framework!

Our [dataset](https://github.com/anonymousyouser/LESSQL/blob/master/dataset.zip) is currently available!

## Dataset Limitations

I. In the dataset, the number of attributes that suffered modifications in a single schema change is reasonably small, on average. The biggest schema change was on version 21, that is, 27 attribute modifications in total. However, this dataset covers 4 years of development in the Wikipedia project and is representative for all the problems we tackle, since it went through a high diversity of schema structural changes.

II. Another limitation of our experiment was the number of relations for all schema versions of the Wikipedia dataset. Our Joining Network Expression generation algorithm (JNG) computes the joining network expressions (JNE) according to the changes in the target schema. As said in (I), since we worked with a relatively small number of schema changes per schema version, LESSQL may have been limited to structural refactoring changes in a few tables. Nevertheless,  Qiu et al. [4] suggests that only a minor portion of the schema is changed over the lifetime of a database. Also, the generation time depends directly on the number of tables involved in the schema changes. In this dataset, the longest time was 39 seconds for a query that referred to 9 attributes. Overall, our JNE generation approach can be considered as a specification of the Steiner Tree Problem in which we must find the shortest interconnection between relations that contain all attributes from a LESSQL query. The Steiner Tree Problem is said to be NP-Complete so our JNG algorithm uses a heuristic approach, which can be improved in the future.

## Metrics Limitations

III. The obtained results were based on the Success Rate (SR) of SQL query generation, that is, whether LESSQL was able to successfully generate an SQL query that could be executed over the target schema. The SR metric shows that  SQL queries could be successfully generated for the target schema. As a consequence, the correct generation of SQL queries would enable developers to avoid application source code maintenance, the purpose of this approach.

IV. We do not measure how the adoption of LESSQL affects development processes. For instance, we do not know how the syntax of LESSQL may interfere in how developers understand the query and surrounding code.

## Solution Limitations

V. Depending on the type and number of changes, the SchemaDiff algorithm may struggle to find the correct attribute mappings. For example, an attribute previously named "person” renamed to “identification” is a significant change since SchemaDiff relies on syntactic similarity. This situation can be circumvented by using the hybrid or supervised configurations.
