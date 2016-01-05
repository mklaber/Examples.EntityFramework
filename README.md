# Examples.EntityFramework
This is base project to test various Entity Framework 6 configurations.

Full description is on my blog http://bleedingnedge.com/2015/11/01/entity-framework-6-with-asp-net-5/

# NOTE: this has been forked and updated for bug reporting purposes

## Stack Trace

Just run the web app (set WebApplication.Mvc6 as the StartUp Project in Visual Studio and hit F5). You'll get the following stack trace:

```
System.IO.FileNotFoundException: Could not find file 'WebApplication.DataAccess.resources'.
   at System.Reflection.RuntimeAssembly.InternalGetSatelliteAssembly(String name, CultureInfo culture, Version version, Boolean throwOnFileNotFound, StackCrawlMark& stackMark)
   at System.Resources.ManifestBasedResourceGroveler.GetSatelliteAssembly(CultureInfo lookForCulture, StackCrawlMark& stackMark)
   at System.Resources.ManifestBasedResourceGroveler.GrovelForResourceSet(CultureInfo culture, Dictionary`2 localResourceSets, Boolean tryParents, Boolean createIfNotExists, StackCrawlMark& stackMark)
   at System.Resources.ResourceManager.InternalGetResourceSet(CultureInfo requestedCulture, Boolean createIfNotExists, Boolean tryParents, StackCrawlMark& stackMark)
   at System.Resources.ResourceManager.InternalGetResourceSet(CultureInfo culture, Boolean createIfNotExists, Boolean tryParents)
   at System.Resources.ResourceManager.GetString(String name, CultureInfo culture)
   at System.Resources.ResourceManager.GetString(String name)
   at System.Data.Entity.Migrations.DbMigrator.GetDefaultSchema(DbMigration migration)
   at System.Data.Entity.Migrations.DbMigrator.<GetHistorySchemas>b__6(<>f__AnonymousType10`2 <>h__TransparentIdentifier4)
   at System.Linq.Enumerable.<>c__DisplayClass7_0`3.<CombineSelectors>b__0(TSource x)
   at System.Linq.Enumerable.WhereSelectListIterator`2.MoveNext()
   at System.Linq.Enumerable.<ConcatIterator>d__58`1.MoveNext()
   at System.Linq.Enumerable.<ConcatIterator>d__58`1.MoveNext()
   at System.Linq.Enumerable.<DistinctIterator>d__63`1.MoveNext()
   at System.Linq.Buffer`1..ctor(IEnumerable`1 source)
   at System.Linq.Enumerable.<ReverseIterator>d__74`1.MoveNext()
   at System.Data.Entity.Migrations.History.HistoryRepository.QueryExists(String contextKey)
   at System.Data.Entity.Migrations.History.HistoryRepository.Exists(String contextKey)
   at System.Data.Entity.Migrations.History.HistoryRepository.<GetUpgradeOperations>d__16.MoveNext()
   at System.Linq.Enumerable.Any[TSource](IEnumerable`1 source)
   at System.Data.Entity.Migrations.DbMigrator.UpdateInternal(String targetMigration)
   at System.Data.Entity.Migrations.DbMigrator.<>c__DisplayClassc.<Update>b__b()
   at System.Data.Entity.Migrations.DbMigrator.EnsureDatabaseExists(Action mustSucceedToKeepDatabase)
   at System.Data.Entity.Migrations.Infrastructure.MigratorBase.EnsureDatabaseExists(Action mustSucceedToKeepDatabase)
   at System.Data.Entity.Migrations.DbMigrator.Update(String targetMigration)
   at System.Data.Entity.Migrations.Infrastructure.MigratorBase.Update()
   at System.Data.Entity.Internal.DatabaseCreator.CreateDatabase(InternalContext internalContext, Func`3 createMigrator, ObjectContext objectContext)
   at System.Data.Entity.Internal.InternalContext.CreateDatabase(ObjectContext objectContext, DatabaseExistenceState existenceState)
   at System.Data.Entity.Database.Create(DatabaseExistenceState existenceState)
   at System.Data.Entity.CreateDatabaseIfNotExists`1.InitializeDatabase(TContext context)
   at System.Data.Entity.Internal.InternalContext.<>c__DisplayClassf`1.<CreateInitializationAction>b__e()
   at System.Data.Entity.Internal.InternalContext.PerformInitializationAction(Action action)
   at System.Data.Entity.Internal.InternalContext.PerformDatabaseInitialization()
   at System.Data.Entity.Internal.LazyInternalContext.<InitializeDatabase>b__4(InternalContext c)
   at System.Data.Entity.Internal.RetryAction`1.PerformAction(TInput input)
   at System.Data.Entity.Internal.LazyInternalContext.InitializeDatabaseAction(Action`1 action)
   at System.Data.Entity.Internal.LazyInternalContext.InitializeDatabase()
   at System.Data.Entity.Internal.InternalContext.Initialize()
   at System.Data.Entity.Internal.InternalContext.GetEntitySetAndBaseTypeForType(Type entityType)
   at System.Data.Entity.Internal.Linq.InternalSet`1.Initialize()
   at System.Data.Entity.Internal.Linq.InternalSet`1.GetEnumerator()
   at System.Data.Entity.Infrastructure.DbQuery`1.System.Collections.Generic.IEnumerable<TResult>.GetEnumerator()
   at System.Collections.Generic.List`1..ctor(IEnumerable`1 collection)
   at System.Linq.Enumerable.ToList[TSource](IEnumerable`1 source)
   at WebApplication.Mvc6.Controllers.HomeController.Index() in C:\Code\Examples.EntityFramework\WebApplication.Mvc6\Controllers\HomeController.cs:line 21
--- End of stack trace from previous location where exception was thrown ---
   at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
   at Microsoft.AspNet.Mvc.Controllers.ControllerActionExecutor.ExecuteAsync(MethodInfo actionMethodInfo, Object instance, Object[] orderedActionArguments)
   at Microsoft.AspNet.Mvc.Controllers.ControllerActionInvoker.<InvokeActionAsync>d__6.MoveNext()
--- End of stack trace from previous location where exception was thrown ---
   at System.Runtime.CompilerServices.TaskAwaiter.ThrowForNonSuccess(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter`1.GetResult()
   at Microsoft.AspNet.Mvc.Controllers.FilterActionInvoker.<InvokeActionFilterAsync>d__53.MoveNext()
--- End of stack trace from previous location where exception was thrown ---
   at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
   at Microsoft.AspNet.Mvc.Controllers.FilterActionInvoker.<InvokeAsync>d__44.MoveNext()
--- End of stack trace from previous location where exception was thrown ---
   at System.Runtime.CompilerServices.TaskAwaiter.ThrowForNonSuccess(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter.GetResult()
   at Microsoft.AspNet.Mvc.Infrastructure.MvcRouteHandler.<RouteAsync>d__6.MoveNext()
--- End of stack trace from previous location where exception was thrown ---
   at System.Runtime.CompilerServices.TaskAwaiter.ThrowForNonSuccess(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter.GetResult()
   at Microsoft.AspNet.Routing.Template.TemplateRoute.<RouteAsync>d__27.MoveNext()
--- End of stack trace from previous location where exception was thrown ---
   at System.Runtime.CompilerServices.TaskAwaiter.ThrowForNonSuccess(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter.GetResult()
   at Microsoft.AspNet.Routing.RouteCollection.<RouteAsync>d__9.MoveNext()
--- End of stack trace from previous location where exception was thrown ---
   at System.Runtime.CompilerServices.TaskAwaiter.ThrowForNonSuccess(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter.GetResult()
   at Microsoft.AspNet.Builder.RouterMiddleware.<Invoke>d__4.MoveNext()
--- End of stack trace from previous location where exception was thrown ---
   at System.Runtime.CompilerServices.TaskAwaiter.ThrowForNonSuccess(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter.GetResult()
   at Microsoft.AspNet.IISPlatformHandler.IISPlatformHandlerMiddleware.<Invoke>d__8.MoveNext()
--- End of stack trace from previous location where exception was thrown ---
   at System.Runtime.CompilerServices.TaskAwaiter.ThrowForNonSuccess(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
   at System.Runtime.CompilerServices.TaskAwaiter.GetResult()
   at Microsoft.AspNet.Diagnostics.DeveloperExceptionPageMiddleware.<Invoke>d__7.MoveNext()
```
