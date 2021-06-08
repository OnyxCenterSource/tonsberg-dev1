# Developer assignments - Tønsberg
During the recruitment process we want the candidates to solve a few development tasks. We use these tasks in our interviews to assess the candidate's ability to solve relevant problems. These solutions will be discussed during the interview process, giving the candidate the oportunity to demonstrate her or his skill level.
## Instructions
1. Fork this repository
2. Read through the whole assignment. The tasks are somewhat related.
3. ...

### Assignment
1. Given the following classes
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

// a) IEnumerable<string> repeatedGuestNames = invoiceGroups... 
// b) IEnumerable<TravelAgentInfo> numberOfNightsByTravelAgent = invoiceGroups..

```
