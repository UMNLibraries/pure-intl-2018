# Pure Intl 2018 Talk Brainstorm

* Title: Escape from the Dark
  * Based on "In the Dark" podcast: what went wrong in the Jacob Wetterling investigation?
  * What went wrong with UMN's Pure automation?
* Bounded Rationality: "we obtain an infinite sequence of levels k = 2, 3 , ...
  provided that finding an optimal method for Level k continues to be unfamiliar
  for every k. Level k: Finding a method for Level k-1."
  -- From the section "Impossibility of Unfamiliar Optimization When Decision Time Is Scarce",
     in Seiten, "What is Bounded Rationality?", 2001
  * I could use this to define "the dark" in my title!
  * Kinds of Darkness (i.e., sources of unfamiliarity)
    * Academic research output metadata
    * Pure
      * Data volume from Pure web services?
    * Scopus
    * Your institution's...
      * HR data
        * Volume?
        * Simple and reliable? Or complex and unpredictable?
      * HR policies
      * HR systems
        * PeopleSoft
        * OIT Data Warehouse
    * Database technology, e.g., Oracle
    * Implementation language, including its core and contributed libraries.
    * ETL experience
    * ETL products to buy or re-use
    * Other (non-ETL) products to buy or re-use, which may be a better fit for this problem (e.g., Kafka)
    * Knowledge and experience building automated systems
      * Automated provisioning of remote machines
      * Automated deployment of software
      * Ensure that software restarts when machine restarts
      * Resilient, fault-tolerant, idempotent software, that can safely pick up where it left off after some sort of failure
        * Implies need for strong, automated tests
      * Notifications of errors and anomalies, which may require human intervention
      * Ensure that long-running processes do not run out of memory
      * Ability to handle occasional and unpredictable spurts of larger-than-normal volumes of data.
* Rationalism vs Empiricism
  * Also: Waterfall, aka Big Up-front Design vs Agile
  * Tried to design too much without empirical analysis of the data.
    * Helps us to break out of the bounded rationality infinite regress described above.
    * Real data tends to contain surprises, which tend to expose invalid assumptions in designs.
      Those designs may be only vague mental models. Recognizing those assumptions helps to constrain
      design possibilities, helping us to escape the infinite regress.
    * New Pure web services API "documentation" allows us to easily see actual data.
    * UMN HR data has no unique identifiers for jobs! Never would have expected that without
      looking at actual data.
    * UMN HR also has no consistent definitions that separate one job from another:
      * Some people define a job as a position in a department, which could include a series of
        different roles or duties (jobcodes). Others define roles with different jobcodes as separate jobs.
    * UMN HR data contains no reliable way to determine when jobs start and end. See above for 
      one reason why--we don't have a consistent definition of "job". Even if we did, we have
      several columns that _may_ determine start and dates, none of which is consistently used:
      * effdt combined with effseq, empl_status, status_flg, and job_terminated
      * job_entry_dt
      * position_entry_dt
      * last_date_worked
* Ways to Increase Light
  * Short feedback loops!
    * Pure is great at this with Pure API docs, terrible at this with syncs, which require loading all data every time.
