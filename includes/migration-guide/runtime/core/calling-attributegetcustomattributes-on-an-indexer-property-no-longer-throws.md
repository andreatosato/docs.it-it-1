### <a name="calling-attributegetcustomattributes-on-an-indexer-property-no-longer-throws-ambiguousmatchexception-if-the-ambiguity-can-be-resolved-by-indexs-type"></a><span data-ttu-id="bc05b-101">La chiamata di Attribute.GetCustomAttributes su una proprietà indicizzatore non genera più AmbiguousMatchException se l'ambiguità può essere risolta dal tipo di indice</span><span class="sxs-lookup"><span data-stu-id="bc05b-101">Calling Attribute.GetCustomAttributes on an indexer property no longer throws AmbiguousMatchException if the ambiguity can be resolved by index's type</span></span>

|   |   |
|---|---|
|<span data-ttu-id="bc05b-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="bc05b-102">Details</span></span>|<span data-ttu-id="bc05b-103">Prima di .NET Framework 4.6, la chiamata di <code>GetCustomAttribute(s)</code> su una proprietà indicizzatore diversa da un'altra proprietà solo per il tipo di indice genera una eccezione <xref:System.Reflection.AmbiguousMatchException?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="bc05b-103">Prior to the .NET Framework 4.6, calling <code>GetCustomAttribute(s)</code> on an indexer property which differed from another property only by the type of the index would result in an <xref:System.Reflection.AmbiguousMatchException?displayProperty=name>.</span></span> <span data-ttu-id="bc05b-104">A partire da .NET Framework 4.6, gli attributi della proprietà verranno restituiti correttamente.</span><span class="sxs-lookup"><span data-stu-id="bc05b-104">Beginning in the .NET Framework 4.6, the property's attributes will be correctly returned.</span></span>|
|<span data-ttu-id="bc05b-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="bc05b-105">Suggestion</span></span>|<span data-ttu-id="bc05b-106">Tenere presente che GetCustomAttribute funzionerà più frequentemente.</span><span class="sxs-lookup"><span data-stu-id="bc05b-106">Be aware that GetCustomAttribute(s) will work more frequently now.</span></span> <span data-ttu-id="bc05b-107">Se un'app dipende da <xref:System.Reflection.AmbiguousMatchException?displayProperty=name> nelle versioni precedenti, è ora necessario usare la reflection per cercare in modo esplicito più indicizzatori.</span><span class="sxs-lookup"><span data-stu-id="bc05b-107">If an app was previously relying on the <xref:System.Reflection.AmbiguousMatchException?displayProperty=name>, reflection should now be used to explicitly look for multiple indexers, instead.</span></span>|
|<span data-ttu-id="bc05b-108">Ambito</span><span class="sxs-lookup"><span data-stu-id="bc05b-108">Scope</span></span>|<span data-ttu-id="bc05b-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="bc05b-109">Edge</span></span>|
|<span data-ttu-id="bc05b-110">Versione</span><span class="sxs-lookup"><span data-stu-id="bc05b-110">Version</span></span>|<span data-ttu-id="bc05b-111">4.6</span><span class="sxs-lookup"><span data-stu-id="bc05b-111">4.6</span></span>|
|<span data-ttu-id="bc05b-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="bc05b-112">Type</span></span>|<span data-ttu-id="bc05b-113">Runtime</span><span class="sxs-lookup"><span data-stu-id="bc05b-113">Runtime</span></span>|
|<span data-ttu-id="bc05b-114">API interessate</span><span class="sxs-lookup"><span data-stu-id="bc05b-114">Affected APIs</span></span>|<ul><li><xref:System.Attribute.GetCustomAttribute(System.Reflection.MemberInfo,System.Type)?displayProperty=nameWithType></li><li><xref:System.Attribute.GetCustomAttribute(System.Reflection.MemberInfo,System.Type,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo)?displayProperty=nameWithType></li><li><xref:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Type)?displayProperty=nameWithType></li><li><xref:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Type,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute(System.Reflection.MemberInfo,System.Type)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute(System.Reflection.MemberInfo,System.Type,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%60%601(System.Reflection.MemberInfo)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%60%601(System.Reflection.MemberInfo,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Type)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Type,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%60%601(System.Reflection.MemberInfo)?displayProperty=nameWithType></li><li><xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%60%601(System.Reflection.MemberInfo,System.Boolean)?displayProperty=nameWithType></li></ul>|
