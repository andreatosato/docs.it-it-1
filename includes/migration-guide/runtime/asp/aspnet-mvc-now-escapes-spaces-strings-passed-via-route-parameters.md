### <a name="aspnet-mvc-now-escapes-spaces-in-strings-passed-in-via-route-parameters"></a><span data-ttu-id="3e1e3-101">ASP.NET MVC usa ora caratteri di escape per gli spazi nelle stringhe passate tramite i parametri di una route</span><span class="sxs-lookup"><span data-stu-id="3e1e3-101">ASP.NET MVC now escapes spaces in strings passed in via route parameters</span></span>

|   |   |
|---|---|
|<span data-ttu-id="3e1e3-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="3e1e3-102">Details</span></span>|<span data-ttu-id="3e1e3-103">Per conformità allo standard RFC 2396, vengono ora usati caratteri di escape per gli spazi nei percorsi di route durante il popolamento dei parametri di azione da una route.</span><span class="sxs-lookup"><span data-stu-id="3e1e3-103">In order to conform to RFC 2396, spaces in route paths are now escaped when populating action parameters from a route.</span></span> <span data-ttu-id="3e1e3-104">Pertanto, mentre <code>/controller/action/some data</code> in precedenza corrispondeva alla route <code>/controller/action/{data}</code> e forniva il parametro dati <code>some data</code>, ora fornisce invece <code>some%20data</code>.</span><span class="sxs-lookup"><span data-stu-id="3e1e3-104">So, whereas  <code>/controller/action/some data</code> would previously match the route <code>/controller/action/{data}</code> and provide <code>some data</code> as the data parameter, it will now provide <code>some%20data</code> instead.</span></span>|
|<span data-ttu-id="3e1e3-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="3e1e3-105">Suggestion</span></span>|<span data-ttu-id="3e1e3-106">È necessario aggiornare il codice per rimuovere i caratteri di escape dai parametri stringa da una route.</span><span class="sxs-lookup"><span data-stu-id="3e1e3-106">Code should be updated to unescape string parameters from a route.</span></span> <span data-ttu-id="3e1e3-107">Se è necessario l'URI originale, è possibile accedervi con l'API <xref:System.Net.HttpWebRequest.RequestUri>.OriginalString.</span><span class="sxs-lookup"><span data-stu-id="3e1e3-107">If the original URI is needed, it can be accessed with the <xref:System.Net.HttpWebRequest.RequestUri>.OriginalString API.</span></span>|
|<span data-ttu-id="3e1e3-108">Ambito</span><span class="sxs-lookup"><span data-stu-id="3e1e3-108">Scope</span></span>|<span data-ttu-id="3e1e3-109">Secondario</span><span class="sxs-lookup"><span data-stu-id="3e1e3-109">Minor</span></span>|
|<span data-ttu-id="3e1e3-110">Versione</span><span class="sxs-lookup"><span data-stu-id="3e1e3-110">Version</span></span>|<span data-ttu-id="3e1e3-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="3e1e3-111">4.5.2</span></span>|
|<span data-ttu-id="3e1e3-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="3e1e3-112">Type</span></span>|<span data-ttu-id="3e1e3-113">Runtime</span><span class="sxs-lookup"><span data-stu-id="3e1e3-113">Runtime</span></span>|
|<span data-ttu-id="3e1e3-114">API interessate</span><span class="sxs-lookup"><span data-stu-id="3e1e3-114">Affected APIs</span></span>|<ul><li><xref:System.Web.Mvc.RouteAttribute.%23ctor(System.String)?displayProperty=nameWithType></li></ul>|
