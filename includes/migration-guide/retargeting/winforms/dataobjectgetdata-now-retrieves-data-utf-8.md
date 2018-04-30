### <a name="dataobjectgetdata-now-retrieves-data-as-utf-8"></a><span data-ttu-id="16815-101">DataObject.GetData ora recupera i dati come UTF-8</span><span class="sxs-lookup"><span data-stu-id="16815-101">DataObject.GetData now retrieves data as UTF-8</span></span>

|   |   |
|---|---|
|<span data-ttu-id="16815-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="16815-102">Details</span></span>|<span data-ttu-id="16815-103">Per le app destinate a .NET Framework 4 o che vengono eseguite in .NET Framework 4.5.1 o in versioni precedenti, <code>DataObject.GetData</code> recupera dati in formato HTML sotto forma di stringa ASCII.</span><span class="sxs-lookup"><span data-stu-id="16815-103">For apps that target the .NET Framework 4 or that run on the .NET Framework 4.5.1 or earlier versions, <code>DataObject.GetData</code> retrieves HTML-formatted data as an ASCII string.</span></span> <span data-ttu-id="16815-104">Di conseguenza, i caratteri non ASCII (caratteri con codici ASCII maggiori di 0x7F) sono rappresentati da due caratteri casuali. Per le app destinate a .NET Framework 4.5 o versioni successive ed eseguite in .NET Framework 4.5.2, <code>DataObject.GetData</code> recupera dati in formato HTML come UTF-8, che rappresenta correttamente i caratteri maggiori di 0x7F.</span><span class="sxs-lookup"><span data-stu-id="16815-104">As a result, non-ASCII characters (characters whose ASCII codes are greater than 0x7F) are represented by two random characters.For apps that target the .NET Framework 4.5 or later and run on the .NET Framework 4.5.2, <code>DataObject.GetData</code> retrieves HTML-formatted data as UTF-8, which represents characters greater than 0x7F correctly.</span></span>|
|<span data-ttu-id="16815-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="16815-105">Suggestion</span></span>|<span data-ttu-id="16815-106">Se è stata implementata una soluzione alternativa per il problema di codifica con le stringhe in formato HTML, ad esempio codificando in modo esplicito la stringa HTML recuperata dagli Appunti passandola a <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=name>, e si intende ridestinare l'app dalla versione 4 alla versione 4.5, è necessario rimuovere questa soluzione alternativa. Se per qualche motivo è necessario il comportamento precedente, l'app può essere destinata a .NET Framework 4.0 per ottenere tale comportamento.</span><span class="sxs-lookup"><span data-stu-id="16815-106">If you implemented a workaround for the encoding problem with HTML-formatted strings (for example, by explicitly encoding the HTML string retrieved from the Clipboard by passing it to <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=name>) and you're retargeting your app from version 4 to 4.5, that workaround should be removed.If the old behavior is needed for some reason, the app can target the .NET Framework 4.0 to get that behavior.</span></span>|
|<span data-ttu-id="16815-107">Ambito</span><span class="sxs-lookup"><span data-stu-id="16815-107">Scope</span></span>|<span data-ttu-id="16815-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="16815-108">Edge</span></span>|
|<span data-ttu-id="16815-109">Versione</span><span class="sxs-lookup"><span data-stu-id="16815-109">Version</span></span>|<span data-ttu-id="16815-110">4.5.2</span><span class="sxs-lookup"><span data-stu-id="16815-110">4.5.2</span></span>|
|<span data-ttu-id="16815-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="16815-111">Type</span></span>|<span data-ttu-id="16815-112">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="16815-112">Retargeting</span></span>|
|<span data-ttu-id="16815-113">API interessate</span><span class="sxs-lookup"><span data-stu-id="16815-113">Affected APIs</span></span>|<ul><li><xref:System.Windows.DataObject.GetData(System.String)?displayProperty=nameWithType></li><li><xref:System.Windows.DataObject.GetData(System.Type)?displayProperty=nameWithType></li><li><xref:System.Windows.DataObject.GetData(System.String,System.Boolean)?displayProperty=nameWithType></li></ul>|
