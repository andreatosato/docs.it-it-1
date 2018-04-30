### <a name="wcf-addressheadercollection-now-throws-an-argumentexception-if-an-addressheader-element-is-null"></a><span data-ttu-id="5a172-101">L'oggetto AddressHeaderCollection di WCF ora genera un'eccezione ArgumentException se un elemento addressHeader è Null</span><span class="sxs-lookup"><span data-stu-id="5a172-101">WCF AddressHeaderCollection now throws an ArgumentException if an addressHeader element is null</span></span>

|   |   |
|---|---|
|<span data-ttu-id="5a172-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="5a172-102">Details</span></span>|<span data-ttu-id="5a172-103">A partire da .NET Framework 4.7.1 il costruttore <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> genera un'eccezione <xref:System.ArgumentException> se uno degli elementi è <code>null</code>.</span><span class="sxs-lookup"><span data-stu-id="5a172-103">Starting with the .NET Framework 4.7.1, the <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> constructor throws an <xref:System.ArgumentException> if one of the elements is <code>null</code>.</span></span> <span data-ttu-id="5a172-104">In .NET Framework 4.7 e versioni precedenti non viene generata alcuna eccezione.</span><span class="sxs-lookup"><span data-stu-id="5a172-104">In the .NET Framework 4.7 and earlier versions, no exception is thrown.</span></span>|
|<span data-ttu-id="5a172-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="5a172-105">Suggestion</span></span>|<span data-ttu-id="5a172-106">Se si riscontrano problemi di compatibilità con questa modifica in .NET Framework 4.7.1 o versione successiva, è possibile rifiutarla esplicitamente aggiungendo la riga seguente alla sezione <code>&lt;runtime&gt;</code> del file app.config:</span><span class="sxs-lookup"><span data-stu-id="5a172-106">If you encounter compatibility issues with this change on the .NET Framework 4.7.1 or a later version, you can opt-out of it by adding the following line to the <code>&lt;runtime&gt;</code> section of the app.config file::</span></span><pre><code class="language-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableAddressHeaderCollectionValidation=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="5a172-107">Ambito</span><span class="sxs-lookup"><span data-stu-id="5a172-107">Scope</span></span>|<span data-ttu-id="5a172-108">Secondario</span><span class="sxs-lookup"><span data-stu-id="5a172-108">Minor</span></span>|
|<span data-ttu-id="5a172-109">Versione</span><span class="sxs-lookup"><span data-stu-id="5a172-109">Version</span></span>|<span data-ttu-id="5a172-110">4.7.1</span><span class="sxs-lookup"><span data-stu-id="5a172-110">4.7.1</span></span>|
|<span data-ttu-id="5a172-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="5a172-111">Type</span></span>|<span data-ttu-id="5a172-112">Runtime</span><span class="sxs-lookup"><span data-stu-id="5a172-112">Runtime</span></span>|
|<span data-ttu-id="5a172-113">API interessate</span><span class="sxs-lookup"><span data-stu-id="5a172-113">Affected APIs</span></span>|<ul><li><xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})?displayProperty=nameWithType></li></ul>|
