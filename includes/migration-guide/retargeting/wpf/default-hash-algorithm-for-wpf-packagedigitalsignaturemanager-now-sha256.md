### <a name="the-default-hash-algorithm-for-wpf-packagedigitalsignaturemanager-is-now-sha256"></a><span data-ttu-id="aedd6-101">L'algoritmo hash predefinito per WPF PackageDigitalSignatureManager è ora SHA256</span><span class="sxs-lookup"><span data-stu-id="aedd6-101">The default hash algorithm for WPF PackageDigitalSignatureManager is now SHA256</span></span>

|   |   |
|---|---|
|<span data-ttu-id="aedd6-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="aedd6-102">Details</span></span>|<span data-ttu-id="aedd6-103"><code>System.IO.Packaging.PackageDigitalSignatureManager</code> offre funzionalità per le firme digitali in relazione ai pacchetti WPF.</span><span class="sxs-lookup"><span data-stu-id="aedd6-103">The <code>System.IO.Packaging.PackageDigitalSignatureManager</code> provides functionality for digital signatures in relation to WPF packages.</span></span>  <span data-ttu-id="aedd6-104">In .NET Framework 4.7 e versioni precedenti, l'algoritmo predefinito (<xref:System.IO.Packaging.PackageDigitalSignatureManager.DefaultHashAlgorithm?displayProperty=nameWithType>) usato per firmare le parti di un pacchetto era SHA1.</span><span class="sxs-lookup"><span data-stu-id="aedd6-104">In the .NET Framework 4.7 and earlier versions, the default algorithm (<xref:System.IO.Packaging.PackageDigitalSignatureManager.DefaultHashAlgorithm?displayProperty=nameWithType>) used for signing parts of a package was SHA1.</span></span>  <span data-ttu-id="aedd6-105">A causa di problemi di sicurezza recenti con SHA1, questa impostazione predefinita è stata cambiata in SHA256 a partire da .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="aedd6-105">Due to recent security concerns with SHA1, this default has been changed to SHA256 starting with the .NET Framework 4.7.1.</span></span>  <span data-ttu-id="aedd6-106">Questa modifica interessa la firma di tutti i pacchetti, inclusi i documenti XPS.</span><span class="sxs-lookup"><span data-stu-id="aedd6-106">This change affects all package signing, including XPS documents.</span></span>|
|<span data-ttu-id="aedd6-107">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="aedd6-107">Suggestion</span></span>|<span data-ttu-id="aedd6-108">Uno sviluppatore che desidera usare questa modifica per una versione del framework precedente a .NET 4.7.1 o uno sviluppatore che richiede la funzionalità precedente per il framework .NET 4.7.1 o versione successiva può impostare nel modo appropriato il flag AppContext seguente.</span><span class="sxs-lookup"><span data-stu-id="aedd6-108">A developer who wants to utilize this change while targeting a framework version below .NET 4.7.1 or a developer who requires the previous functionality while targeting .NET 4.7.1 or greater can set the following AppContext flag appropriately.</span></span>  <span data-ttu-id="aedd6-109">Se il valore è true viene usato come algoritmo predefinito SHA1; se è false viene usato SHA256.</span><span class="sxs-lookup"><span data-stu-id="aedd6-109">A value of true will result in SHA1 being used as the default algorithm; false results in SHA256.</span></span><pre><code class="language-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.UseSha1AsDefaultHashAlgorithmForDigitalSignatures=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="aedd6-110">Ambito</span><span class="sxs-lookup"><span data-stu-id="aedd6-110">Scope</span></span>|<span data-ttu-id="aedd6-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="aedd6-111">Edge</span></span>|
|<span data-ttu-id="aedd6-112">Versione</span><span class="sxs-lookup"><span data-stu-id="aedd6-112">Version</span></span>|<span data-ttu-id="aedd6-113">4.7.1</span><span class="sxs-lookup"><span data-stu-id="aedd6-113">4.7.1</span></span>|
|<span data-ttu-id="aedd6-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="aedd6-114">Type</span></span>|<span data-ttu-id="aedd6-115">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="aedd6-115">Retargeting</span></span>|
|<span data-ttu-id="aedd6-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="aedd6-116">Affected APIs</span></span>|<ul><li><xref:System.IO.Packaging.PackageDigitalSignatureManager.DefaultHashAlgorithm?displayProperty=nameWithType></li></ul>|
