### <a name="persian-calendar-now-uses-the-hijri-solar-algorithm"></a><span data-ttu-id="20b7c-101">Il calendario persiano ora usa l'algoritmo solare Hijri</span><span class="sxs-lookup"><span data-stu-id="20b7c-101">Persian calendar now uses the Hijri solar algorithm</span></span>

|   |   |
|---|---|
|<span data-ttu-id="20b7c-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="20b7c-102">Details</span></span>|<span data-ttu-id="20b7c-103">A partire da .NET Framework 4.6, la classe <xref:System.Globalization.PersianCalendar?displayProperty=name> usa l'algoritmo solare Hijri.</span><span class="sxs-lookup"><span data-stu-id="20b7c-103">Starting with the .NET Framework 4.6, the <xref:System.Globalization.PersianCalendar?displayProperty=name> class uses the Hijri solar algorithm.</span></span> <span data-ttu-id="20b7c-104">La conversione di date tra il calendario <xref:System.Globalization.PersianCalendar?displayProperty=name> e altri calendari può produrre risultati leggermente diversi a partire da .NET Framework 4.6 per le date precedenti al 1800 o successive al 2023 (calendario gregoriano). Inoltre, <xref:System.Globalization.PersianCalendar.MinSupportedDateTime> è ora <code>March 22, 0622 instead of March 21, 0622</code>.</span><span class="sxs-lookup"><span data-stu-id="20b7c-104">Converting dates between the <xref:System.Globalization.PersianCalendar?displayProperty=name> and other calendars may produce a slightly different result beginning with the .NET Framework 4.6 for dates earlier than 1800 or later than 2023 (Gregorian).Also, <xref:System.Globalization.PersianCalendar.MinSupportedDateTime> is now <code>March 22, 0622 instead of March 21, 0622</code>.</span></span>|
|<span data-ttu-id="20b7c-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="20b7c-105">Suggestion</span></span>|<span data-ttu-id="20b7c-106">Tenere presente che alcune date precedenti o successive potrebbero essere leggermente diverse quando si usa PersianCalendar in .NET 4.6.</span><span class="sxs-lookup"><span data-stu-id="20b7c-106">Be aware that some early or late dates may be slightly different when using the PersianCalendar in .NET 4.6.</span></span> <span data-ttu-id="20b7c-107">Inoltre, quando si serializzano le date tra processi che possono essere eseguiti in versioni diverse di .NET Framework, evitare di archiviarle come stringhe di data PersianCalendar, perché tali valori potrebbero essere diversi.</span><span class="sxs-lookup"><span data-stu-id="20b7c-107">Also, when serializing dates between processes which may run on different .NET Framework versions, do not store them as PersianCalendar date strings (since those values may be different).</span></span>|
|<span data-ttu-id="20b7c-108">Ambito</span><span class="sxs-lookup"><span data-stu-id="20b7c-108">Scope</span></span>|<span data-ttu-id="20b7c-109">Secondario</span><span class="sxs-lookup"><span data-stu-id="20b7c-109">Minor</span></span>|
|<span data-ttu-id="20b7c-110">Versione</span><span class="sxs-lookup"><span data-stu-id="20b7c-110">Version</span></span>|<span data-ttu-id="20b7c-111">4.6</span><span class="sxs-lookup"><span data-stu-id="20b7c-111">4.6</span></span>|
|<span data-ttu-id="20b7c-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="20b7c-112">Type</span></span>|<span data-ttu-id="20b7c-113">Runtime</span><span class="sxs-lookup"><span data-stu-id="20b7c-113">Runtime</span></span>|
|<span data-ttu-id="20b7c-114">API interessate</span><span class="sxs-lookup"><span data-stu-id="20b7c-114">Affected APIs</span></span>|<ul><li><xref:System.Globalization.PersianCalendar?displayProperty=nameWithType></li></ul>|
