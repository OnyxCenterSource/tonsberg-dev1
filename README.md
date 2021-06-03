# Developer assignment 1 - Tønsberg

During the recruitment process we want the candidates to solve a few development tasks. We use these tasks in our interviews to assess the candidate's ability to solve relevant problems. These solutions will be discussed during the interview process, giving the candidate the opportunity to demonstrate her or his skill level.

## Instructions
1. Clone this repository.
2. Read through the whole assignment, the tasks are somewhat related.
3. Use Visual Studio or any other IDE you prefer.
4. To the best of your ability, try to solve each and every one of the following tasks.
   * Think about how you would solve tasks you may not be able to solve.
5. Prepare to demonstrate your solution, either online or on site.

## Assignment

### Task 1

Given the below classes:

* a) Create a LINQ expression for all guest names that occur on more than once (across all invoice groups and invoices, not per invoice group or invoice).

* b) Create a LINQ expression for the total number of nights per travel agent for invoice groups issued in 2015.

```c#
class InvoiceGroup
{
    public DateTime IssueDate { get; set; }
    public List<Invoice> Invoices { get; set; }
}

class Invoice
{
    public List<Observation> Observations { get; set; }
}

class Observation
{
    public string TravelAgent { get; set; }
    public string GuestName { get; set; }
    public int NumberOfNights { get; set; }
}

class TravelAgentInfo
{
    public string TravelAgent { get; set; }
    public int TotalNumberOfNights { get; set; }
}

var invoiceGroups = newList<InvoiceGroup>();

// a)
IEnumerable<string> repeatedGuestNames = invoiceGroups... 

// b)
IEnumerable<TravelAgentInfo> numberOfNightsByTravelAgent = invoiceGroups..

```

Given corresponding database tables `TravelAgent` and `Observation`, both with a `TravelAgent` field being the primary and foreign key, respectively:

* c) Write a SQL query that finds all travel agents that does not have any observations.

     `SELECT * FROM TravelAgent ...`

* d) Write a SQL query that finds all travel agents that have more than two observations.

    `SELECT * FROM TravelAgent ...`

### Task 2

Given the below `Logger` class:

* a) Refactor the class so that it can be unit-tested in isolation (independent of external input/output, like file system and current time).

* b) Write a unit test that asserts that the `Logger.Log` method prefixes the input string with date and time (avoiding external input/output if possible).

```c#
class Logger
{
    private readonly StreamWriter _writer;

    public Logger(string path)
    {
        _writer = new StreamWriter(File.Open(path, FileMode.Append))
        {
            AutoFlush = true
        };

        Log("Logger initialized");
    }

    public void Log(string str)
    {
        _writer.WriteLine(string.Format("[{0:dd.MM.yy HH:mm:ss}] {1}", DateTime.Now, str));
    }
}
```

### Task 3

Given the below `VatVerifier` class:

* a) Implement the missing Verify method that uses EU VIES web service to verify VAT IDs.
  * EU VIES WSDL URL: http://ec.europa.eu/taxation_customs/vies/checkVatService.wsdl
  * Example of valid German VAT ID: DE118856456

```c#
class VatVerifier
{
    enum VerificationStatus
    {
        Valid,
        Invalid,
        // Unable to get status (e.g. service unavailable)
        Unavailable
    }

    /// <summary>
    /// Verifies the given VAT ID for the given country using the EU VIES web service.
    /// </summary>
    /// <param name="countryCode"></param>
    /// <param name="vatId"></param>
    /// <returns>Verification status</returns>
    // TODO: Implement Verify method
}
```

### Task 4

* a) Create an API with a controller that uses the `VatVerifier` class to verify a VAT ID based on a provided country code and VAT ID.

* b) Create simple front-end using Angular, React or any other frontend framework of your choosing, with a simple user interface that integrates with the API created in sub-task a) and allows validating VAT IDs and show their validation status.