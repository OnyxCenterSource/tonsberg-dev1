# Developer assignments - Tønsberg
During the recruitment process we want the candidates to solve a few development tasks. We use these tasks in our interviews to assess the candidate's ability to solve relevant problems. These solutions will be discussed during the interview process, giving the candidate the oportunity to demonstrate her or his skill level.
### Instructions
1. Fork this repository
2. Read through the assignment. The tasks are somewhat connected.
3. ...

### Assignment
1. Given the following class
```c#
classInvoiceGroup{ publicDateTime IssueDate { get; set; } publicList<Invoice> Invoices { get; set; } } classInvoice{ publicList<Observation> Observations { get; set; } } classObservation{ publicstring TravelAgent { get; set; } publicstring GuestName { get; set; } publicint NumberOfNights { get; set; } } classTravelAgentInfo{ publicstring TravelAgent { get; set; } publicint TotalNumberOfNights { get; set; } } var invoiceGroups = newList<InvoiceGroup>(); // a)IEnumerable<string> repeatedGuestNames = invoiceGroups... // b) IEnumerable<TravelAgentInfo> numberOfNightsByTravelAgent = invoiceGroups..

```
