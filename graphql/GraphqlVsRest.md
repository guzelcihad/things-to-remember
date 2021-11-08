Say that you want to fetch information to display
* Author name
* Courses authored
* Authors rating
* Most recent topic covered

In REST, you need to call lots of APIs
* /ps/author/<id>
* /ps/author/<id>/courses
* /ps/author/<id>/rating
* /ps/author/<id>/topic


REST | GraphQL
--- | --- |
Multiple round trips to collect information from multiple resources | One single request to collect information by aggregation of data | 283 |
Over fetching and under fetching data resources | You only get what you ask for | 283 |
Frontend teams rely heavily on beacked teams to deliver the APIs | Fron and backend teams can work independently | 283 |
