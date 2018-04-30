### <a name="different-exception-handling-for-objectcontextcreatedatabase-and-dbproviderservicescreatedatabase-methods"></a><span data-ttu-id="78261-101">Diversa gestione delle eccezioni per i metodi ObjectContext.CreateDatabase e DbProviderServices.CreateDatabase</span><span class="sxs-lookup"><span data-stu-id="78261-101">Different exception handling for ObjectContext.CreateDatabase and DbProviderServices.CreateDatabase methods</span></span>

|   |   |
|---|---|
|<span data-ttu-id="78261-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="78261-102">Details</span></span>|<span data-ttu-id="78261-103">A partire da .NET 4.5, se la creazione del database non riesce, i metodi <code>CreateDatabase</code> tenteranno di eliminare il database vuoto.</span><span class="sxs-lookup"><span data-stu-id="78261-103">Beginning in .NET 4.5, if database creation fails, <code>CreateDatabase</code> methods will attempt to drop the empty database.</span></span> <span data-ttu-id="78261-104">Se tale operazione ha esito positivo, verrà propagata l'eccezione <xref:System.Data.SqlClient.SqlException?displayProperty=name> originale, al posto dell'eccezione <xref:System.InvalidOperationException?displayProperty=name> che viene sempre generata in .NET 4.0.</span><span class="sxs-lookup"><span data-stu-id="78261-104">If that operation succeeds, the original <xref:System.Data.SqlClient.SqlException?displayProperty=name> will be propagated (instead of the <xref:System.InvalidOperationException?displayProperty=name> that was always thrown in .NET 4.0)</span></span>|
|<span data-ttu-id="78261-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="78261-105">Suggestion</span></span>|<span data-ttu-id="78261-106">Quando si rileva un oggetto <xref:System.InvalidOperationException?displayProperty=name> durante l'esecuzione di <xref:System.Data.Objects.ObjectContext.CreateDatabase> o <xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)>, ora deve essere rilevato anche SQLExceptions.</span><span class="sxs-lookup"><span data-stu-id="78261-106">When catching an <xref:System.InvalidOperationException?displayProperty=name> while executing <xref:System.Data.Objects.ObjectContext.CreateDatabase> or <xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)>, SQLExceptions should now also be caught.</span></span>|
|<span data-ttu-id="78261-107">Ambito</span><span class="sxs-lookup"><span data-stu-id="78261-107">Scope</span></span>|<span data-ttu-id="78261-108">Secondario</span><span class="sxs-lookup"><span data-stu-id="78261-108">Minor</span></span>|
|<span data-ttu-id="78261-109">Versione</span><span class="sxs-lookup"><span data-stu-id="78261-109">Version</span></span>|<span data-ttu-id="78261-110">4.5</span><span class="sxs-lookup"><span data-stu-id="78261-110">4.5</span></span>|
|<span data-ttu-id="78261-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="78261-111">Type</span></span>|<span data-ttu-id="78261-112">Runtime</span><span class="sxs-lookup"><span data-stu-id="78261-112">Runtime</span></span>|
|<span data-ttu-id="78261-113">API interessate</span><span class="sxs-lookup"><span data-stu-id="78261-113">Affected APIs</span></span>|<ul><li><xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)?displayProperty=nameWithType></li></ul>|
