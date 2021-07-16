# Developer assignment 1 - Tønsberg
During the recruitment process we want the candidates to solve a few development tasks. We use these tasks in our interviews to assess the candidate's ability to solve relevant problems. These solutions will be discussed during the interview process, giving the candidate the opportunity to demonstrate her or his skill level.
## Instructions
1. Clone this repository
2. Read through the whole assignment. The tasks are somewhat related.
3. Use Visual Studio or any other IDE you may prefer.
4. To the best of your ability, try to solve each and every one of the following tasks.
5. Prepare to demonstrate your solution in an interview process, either online or on site.
6. [Good luck!](https://www.finn.no/job/apply?adId=225170022 "Apply here!")


## Assignment

***

### Given the following classes

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

<ol start="1">
  <li>
    <ol type="a">
      <li>Create a LINQ expression for all guest names that occur on more than once (across all invoice groups and invoices, not per invoice group or invoice)</li>
      <li>Create a LINQ expression for the total number of nights per travel agent for invoice groups issued in 2015.</li>
    </ol>
  </li>
</ol>

***

### Given the following class

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

<ol start="2">
  <li>
    <ol type="a">
      <li>Refactor the class so that it can be unit-tested in isolation.</li>
      <li>Write a unit test that asserts that the Logger.Log method prefixes the input string with the current date and time.</li>
    </ol>
  </li>
</ol>

***

### Given the following class

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
    /// Verifies the given VAT number for the given country using the EU VIES web service.
    /// </summary>
    /// <param name="countryCode"></param>
    /// <param name="vatNumber"></param>
    /// <returns>Verification status</returns>
    // TODO: Implement Verify method
}
```

<ol start="3">
  <li>Implement the missing Verify method that uses EU VIES web service to verify VAT numbers.
    <ul>
      <li>WSDL URL: http://ec.europa.eu/taxation_customs/vies/checkVatService.wsdl</li>
      <li>Example of valid German VAT number: DE118856456</li>
    </ul>
  </li>
</ol>

***

<ol start="4">
  <li>Create a website with a Web API controller that uses the VatVerifier class, and a simple front-end using Angular, React or any other frontend framework. Implement a VAT validation form that uses the controller to verify a given VAT number for a given country.
  </li>
</ol>
