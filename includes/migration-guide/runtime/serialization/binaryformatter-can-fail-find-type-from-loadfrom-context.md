### <a name="binaryformatter-can-fail-to-find-type-from-loadfrom-context"></a><span data-ttu-id="005d3-101">BinaryFormatter potrebbe non trovare il tipo dal contesto LoadFrom</span><span class="sxs-lookup"><span data-stu-id="005d3-101">BinaryFormatter can fail to find type from LoadFrom context</span></span>

|   |   |
|---|---|
|<span data-ttu-id="005d3-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="005d3-102">Details</span></span>|<span data-ttu-id="005d3-103">A partire da .NET Framework 4.5, diverse modifiche di <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> potrebbero causare differenze nella deserializzazione quando si usa <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=name> per deserializzare tipi caricati nel contesto LoadFrom.</span><span class="sxs-lookup"><span data-stu-id="005d3-103">As of .NET Framework 4.5, a number of <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> changes may cause differences in deserialization when using <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=name> to deserialize types that had been loaded in the LoadFrom context.</span></span> <span data-ttu-id="005d3-104">Queste modifiche sono dovute ai nuovi modi con cui <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> ora carica un tipo che determina un comportamento diverso quando <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=name> tenta di eseguire la deserializzazione per quel tipo in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="005d3-104">These changes are due to the new ways <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> now loads a type which causes different behavior when a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=name> attempts to deserialize to that type later on.</span></span> <span data-ttu-id="005d3-105">Il binder di serializzazione predefinito non esegue automaticamente la ricerca del contesto LoadFrom, anche se in alcuni casi potrebbe aver funzionato in base al comportamento precedente di XmlSerializer.</span><span class="sxs-lookup"><span data-stu-id="005d3-105">The default serialization binder does not automatically search the LoadFrom context, although it may have worked in some circumstances based on the old behavior of XmlSerializer.</span></span> <span data-ttu-id="005d3-106">A causa delle modifiche, quando un tipo viene caricato da un assembly caricato in un contesto diverso potrebbe essere generato <xref:System.IO.FileNotFoundException?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="005d3-106">Due to the changes, when a type is being loaded from an assembly loaded in a different context, a <xref:System.IO.FileNotFoundException?displayProperty=name> may be thrown.</span></span>|
|<span data-ttu-id="005d3-107">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="005d3-107">Suggestion</span></span>|<span data-ttu-id="005d3-108">Se si verifica questa eccezione, la proprietà <code>Binder</code> di <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=name> può essere impostata su un binder personalizzato che troverà il tipo corretto.</span><span class="sxs-lookup"><span data-stu-id="005d3-108">If this exception is seen, the <code>Binder</code> property of the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=name> can be set to a custom binder that will find the correct type.</span></span><pre><code class="language-C#">var formatter = new BinaryFormatter { Binder = new TypeFinderBinder() }&#13;&#10;</code></pre><span data-ttu-id="005d3-109">Binder personalizzato:</span><span class="sxs-lookup"><span data-stu-id="005d3-109">And then the custom binder:</span></span><pre><code class="language-C#">public class TypeFinderBinder : SerializationBinder&#13;&#10;{&#13;&#10;private static readonly string s_assemblyName = Assembly.GetExecutingAssembly().FullName;&#13;&#10;&#13;&#10;public override Type BindToType(string assemblyName, string typeName)&#13;&#10;{&#13;&#10;return Type.GetType(String.Format(CultureInfo.InvariantCulture, &quot;{0}, {1}&quot;, typeName, s_assemblyName));&#13;&#10;}&#13;&#10;}&#13;&#10;</code></pre>|
|<span data-ttu-id="005d3-110">Ambito</span><span class="sxs-lookup"><span data-stu-id="005d3-110">Scope</span></span>|<span data-ttu-id="005d3-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="005d3-111">Edge</span></span>|
|<span data-ttu-id="005d3-112">Versione</span><span class="sxs-lookup"><span data-stu-id="005d3-112">Version</span></span>|<span data-ttu-id="005d3-113">4.5</span><span class="sxs-lookup"><span data-stu-id="005d3-113">4.5</span></span>|
|<span data-ttu-id="005d3-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="005d3-114">Type</span></span>|<span data-ttu-id="005d3-115">Runtime</span><span class="sxs-lookup"><span data-stu-id="005d3-115">Runtime</span></span>|
|<span data-ttu-id="005d3-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="005d3-116">Affected APIs</span></span>|<ul><li><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)?displayProperty=nameWithType></li></ul>|
