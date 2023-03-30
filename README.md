# .NET-GraphQL-React-App

- Set up GraphQL using C# classes, and dependency injection of OMAContext
- Can view schema and run queries in Banana Cake Pop, which is a GraphQL IDE when running in local host with 'dotnet run' in backend folder

![image](https://user-images.githubusercontent.com/91037796/228725679-15b407ae-f2c3-4df6-ae02-65284a55bf9d.png)


```cs
using Core.Entities;
using Infrastructure.Data;

namespace API.GraphQL
{
    public class Query
    {

        [UseFiltering]  // can use one endpoint and filter the way we want with this!
        public IQueryable<Customer> GetCustomers([Service] OMAContext context )  //dependency injetion of service
        {
            context.Database.EnsureCreated();
            return context.Customers;
        }

        [UseFiltering]
        public IQueryable<Order> GetOrders([Service] OMAContext context)  //dependency injetion of service
        {
            context.Database.EnsureCreated();
            return context.Orders;
        }

    }
}
```



