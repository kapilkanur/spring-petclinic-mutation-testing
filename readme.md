# Mutation testing with PIT 

## Running PetClinic application locally
Follow the readme [petclinic_readme](/readme.md) to run Spring PetClinic Application locally.

## Mutation Testing

The code is automatically seeded with errors (or mutations), and then the tests are executed. If the tests come back negative, the mutation is killed; otherwise, the mutation survives.

The percentage of mutations killed can be used to evaluate the effectiveness of your tests.

### Steps to execute mutation coverage goal analysis
1. *Clone the project*

```git clone git@github.com:kapilkanur/spring-petclinic-testing.git```

2. *Run the mvn command*

```mvn test-compile org.pitest:pitest-maven:mutationCoverage```

The output can be found at target/pit-reports/YYYYMMDDHHMI. I have uploaded the sample output at [Sample PIT reports](/src/main/resources/sample/pit-reports/202207031137)

3. *PIT Test Coverage Report*

 ![PIT test coverage report](/src/main/resources/static/resources/images/pit-test-report.png)


4. *Sample Output*
```
11:37:38 am PIT >> INFO : Created  16 mutation test units
/
|11:40:54 am PIT >> INFO : Completed in 214 seconds
================================================================================
- Mutators
================================================================================
> org.pitest.mutationtest.engine.gregor.mutators.returns.PrimitiveReturnsMutator
>> Generated 1 Killed 1 (100%)
> KILLED 1 SURVIVED 0 TIMED_OUT 0 NON_VIABLE 0 
> MEMORY_ERROR 0 NOT_STARTED 0 STARTED 0 RUN_ERROR 0 
> NO_COVERAGE 0 
--------------------------------------------------------------------------------
> org.pitest.mutationtest.engine.gregor.mutators.VoidMethodCallMutator
>> Generated 25 Killed 6 (24%)
> KILLED 6 SURVIVED 17 TIMED_OUT 0 NON_VIABLE 0 
> MEMORY_ERROR 0 NOT_STARTED 0 STARTED 0 RUN_ERROR 0 
> NO_COVERAGE 2 
--------------------------------------------------------------------------------
> org.pitest.mutationtest.engine.gregor.mutators.returns.BooleanTrueReturnValsMutator
>> Generated 2 Killed 1 (50%)
> KILLED 1 SURVIVED 1 TIMED_OUT 0 NON_VIABLE 0 
> MEMORY_ERROR 0 NOT_STARTED 0 STARTED 0 RUN_ERROR 0 
> NO_COVERAGE 0 
--------------------------------------------------------------------------------
> org.pitest.mutationtest.engine.gregor.mutators.returns.NullReturnValsMutator
>> Generated 18 Killed 15 (83%)
> KILLED 15 SURVIVED 3 TIMED_OUT 0 NON_VIABLE 0 
> MEMORY_ERROR 0 NOT_STARTED 0 STARTED 0 RUN_ERROR 0 
> NO_COVERAGE 0 
--------------------------------------------------------------------------------
> org.pitest.mutationtest.engine.gregor.mutators.MathMutator
>> Generated 2 Killed 0 (0%)
> KILLED 0 SURVIVED 2 TIMED_OUT 0 NON_VIABLE 0 
> MEMORY_ERROR 0 NOT_STARTED 0 STARTED 0 RUN_ERROR 0 
> NO_COVERAGE 0 
--------------------------------------------------------------------------------
> org.pitest.mutationtest.engine.gregor.mutators.returns.EmptyObjectReturnValsMutator
>> Generated 40 Killed 35 (88%)
> KILLED 35 SURVIVED 4 TIMED_OUT 0 NON_VIABLE 0 
> MEMORY_ERROR 0 NOT_STARTED 0 STARTED 0 RUN_ERROR 0 
> NO_COVERAGE 1 
--------------------------------------------------------------------------------
> org.pitest.mutationtest.engine.gregor.mutators.returns.BooleanFalseReturnValsMutator
>> Generated 1 Killed 1 (100%)
> KILLED 1 SURVIVED 0 TIMED_OUT 0 NON_VIABLE 0 
> MEMORY_ERROR 0 NOT_STARTED 0 STARTED 0 RUN_ERROR 0 
> NO_COVERAGE 0 
--------------------------------------------------------------------------------
> org.pitest.mutationtest.engine.gregor.mutators.NegateConditionalsMutator
>> Generated 28 Killed 24 (86%)
> KILLED 24 SURVIVED 4 TIMED_OUT 0 NON_VIABLE 0 
> MEMORY_ERROR 0 NOT_STARTED 0 STARTED 0 RUN_ERROR 0 
> NO_COVERAGE 0 
--------------------------------------------------------------------------------
================================================================================
- Timings
================================================================================
> pre-scan for mutations : < 1 second
> scan classpath : < 1 second
> coverage and dependency analysis : 18 seconds
> build mutation tests : < 1 second
> run mutation analysis : 3 minutes and 15 seconds
--------------------------------------------------------------------------------
> Total  : 3 minutes and 34 seconds
--------------------------------------------------------------------------------
================================================================================
- Statistics
================================================================================
>> Line Coverage: 236/245 (96%)
>> Generated 117 mutations Killed 83 (71%)
>> Mutations with no coverage 3. Test strength 73%
>> Ran 219 tests (1.87 tests per mutation)
Enhanced functionality available at https://www.arcmutate.com/

```
