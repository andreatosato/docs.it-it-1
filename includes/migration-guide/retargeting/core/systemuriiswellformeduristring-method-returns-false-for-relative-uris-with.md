### <a name="systemuriiswellformeduristring-method-returns-false-for-relative-uris-with-a-colon-char-in-first-segment"></a><span data-ttu-id="0f9fb-101">Il metodo System.Uri.IsWellFormedUriString restituisce false per gli URI relativi con un carattere due punti nel primo segmento</span><span class="sxs-lookup"><span data-stu-id="0f9fb-101">System.Uri.IsWellFormedUriString method returns false for relative URIs with a colon char in first segment</span></span>

|   |   |
|---|---|
|<span data-ttu-id="0f9fb-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="0f9fb-102">Details</span></span>|<span data-ttu-id="0f9fb-103">A partire da .NET Framework 4.5, <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)> tratterà gli URI relativi con <code>:</code> nella primo segmento come non ben formati.</span><span class="sxs-lookup"><span data-stu-id="0f9fb-103">Beginning with the .NET Framework 4.5, <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)> will treat relative URIs with a <code>:</code> in their first segment as not well formed.</span></span> <span data-ttu-id="0f9fb-104">Si tratta di una modifica rispetto al comportamento di <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=name> in .NET Framework 4.0, introdotta per conformarsi a RFC3986.</span><span class="sxs-lookup"><span data-stu-id="0f9fb-104">This is a change from <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=name> behavior in the .NET Framework 4.0 that was made to conform to RFC3986.</span></span>|
|<span data-ttu-id="0f9fb-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="0f9fb-105">Suggestion</span></span>|<span data-ttu-id="0f9fb-106">Questa modifica (come molte altre modifiche relative agli URI) influirà solo sulle applicazioni destinate a .NET Framework 4.5 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="0f9fb-106">This change (like many other URI changes) will only affect applications targeting the .NET Framework 4.5 (or later).</span></span> <span data-ttu-id="0f9fb-107">Per continuare a usare il comportamento precedente, scegliere .NET Framework 4.0 come destinazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="0f9fb-107">To keep using the old behavior, target the app against the .NET Framework 4.0.</span></span> <span data-ttu-id="0f9fb-108">In alternativa, analizzare l'URI prima di chiamare <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=name> per cercare caratteri <code>:</code> che è possibile rimuovere ai fini della convalida, se si desidera mantenere il comportamento precedente.</span><span class="sxs-lookup"><span data-stu-id="0f9fb-108">Alternatively, scan URI's prior to calling <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=name> looking for <code>:</code> characters that you may want to remove for validation purposes, if the old behavior is desirable.</span></span>|
|<span data-ttu-id="0f9fb-109">Ambito</span><span class="sxs-lookup"><span data-stu-id="0f9fb-109">Scope</span></span>|<span data-ttu-id="0f9fb-110">Secondario</span><span class="sxs-lookup"><span data-stu-id="0f9fb-110">Minor</span></span>|
|<span data-ttu-id="0f9fb-111">Versione</span><span class="sxs-lookup"><span data-stu-id="0f9fb-111">Version</span></span>|<span data-ttu-id="0f9fb-112">4.5</span><span class="sxs-lookup"><span data-stu-id="0f9fb-112">4.5</span></span>|
|<span data-ttu-id="0f9fb-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="0f9fb-113">Type</span></span>|<span data-ttu-id="0f9fb-114">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="0f9fb-114">Retargeting</span></span>|
|<span data-ttu-id="0f9fb-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="0f9fb-115">Affected APIs</span></span>|<ul><li><xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=nameWithType></li></ul>|
