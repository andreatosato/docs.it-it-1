### <a name="aspnet-accessibility-improvements-in-net-471"></a><span data-ttu-id="7ef0e-101">Miglioramenti di accessibilità ASP.NET in .NET 4.7.1</span><span class="sxs-lookup"><span data-stu-id="7ef0e-101">ASP.NET Accessibility Improvements in .NET 4.7.1</span></span>

|   |   |
|---|---|
|<span data-ttu-id="7ef0e-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="7ef0e-102">Details</span></span>|<span data-ttu-id="7ef0e-103">A partire da .NET Framework 4.7.1, in ASP.NET è stato migliorato il funzionamento dei controlli Web ASP.NET con tecnologia di accessibilità in Visual Studio per supportare al meglio i clienti ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="7ef0e-103">Starting with the .NET Framework 4.7.1, ASP.NET has improved how ASP.NET Web Controls work with accessibility technology in Visual Studio to better support ASP.NET customers.</span></span>  <span data-ttu-id="7ef0e-104">Sono incluse le modifiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="7ef0e-104">These include the following changes:</span></span><ul><li><span data-ttu-id="7ef0e-105">Modifiche per implementare pattern di accessibilità dell'interfaccia utente mancanti nei controlli, come la finestra di dialogo Aggiungi campo nella procedura guidata DetailsView o la finestra di dialogo Configura ListView nella procedura guidata ListView.</span><span class="sxs-lookup"><span data-stu-id="7ef0e-105">Changes to implement missing UI accessibility patterns in controls, like the Add Field dialog in the Details View wizard, or the Configure ListView dialog of the ListView wizard.</span></span></li><li><span data-ttu-id="7ef0e-106">Modifiche per migliorare la visualizzazione nella modalità a contrasto elevato, ad esempio l'Editor campi del pager di dati.</span><span class="sxs-lookup"><span data-stu-id="7ef0e-106">Changes to improve the display in High Contrast mode, like the Data Pager Fields Editor.</span></span></li><li><span data-ttu-id="7ef0e-107">Modifiche per migliorare la navigazione tramite tastiera per controlli, come la finestra di dialogo Campi nella procedura guidata Modifica campi del pager del controllo DataPager, la finestra di dialogo Configura ObjectContext o la finestra di dialogo Configura selezione dati della procedura guidata Configura origine dati.</span><span class="sxs-lookup"><span data-stu-id="7ef0e-107">Changes to improve the keyboard navigation experiences for controls, like the Fields dialog in the Edit Pager Fields wizard of the DataPager control, the Configure ObjectContext dialog, or the Configure Data Selction dialog of the Configure Data Source wizard.</span></span></li></ul>|
|<span data-ttu-id="7ef0e-108">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="7ef0e-108">Suggestion</span></span>|<span data-ttu-id="7ef0e-109"><strong>Come accettare o rifiutare queste modifiche</strong>Affinché nella finestra di progettazione di Visual Studio Designer si possano usare queste modifiche, è necessario che la finestra sia eseguita in .NET Framework 4.7.1 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="7ef0e-109"><strong>How to opt in or out of these changes</strong>In order for the Visual Studio Designer to benefit from these changes, it must run on the .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="7ef0e-110">L'applicazione Web può trarre vantaggio da queste modifiche in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7ef0e-110">The web application can benefit from these changes in either of the following ways:</span></span><ul><li><span data-ttu-id="7ef0e-111">Installare Visual Studio 2017 15.3 o versione successiva, che supporta le nuove funzionalità di accessibilità con l'opzione di AppContext seguente per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="7ef0e-111">Install Visual Studio 2017 15.3 or later, which supports the new accessibility features with the following AppContext Switch by default.</span></span></li><li><span data-ttu-id="7ef0e-112">Rifiutare i comportamenti di accessibilità legacy aggiungendo l'<code>Switch.UseLegacyAccessibilityFeatures</code>opzione di AppContext alla sezione <code>&lt;runtime&gt;</code> del file di configurazione devenv.config e impostandola su <code>false</code>, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="7ef0e-112">Opt out of the legacy accessibility behaviors by adding the <code>Switch.UseLegacyAccessibilityFeatures</code> AppContext switch to the <code>&lt;runtime&gt;</code> section in the devenv.exe.config file and setting it to <code>false</code>, as the following example shows.</span></span></li></ul><pre><code class="language-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;...&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false&#39;  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;...;Switch.UseLegacyAccessibilityFeatures=false&quot; /&gt;&#13;&#10;...&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre><span data-ttu-id="7ef0e-113">Le applicazioni che usano .NET Framework 4.7.1 o versione successiva e che vogliono mantenere il comportamento di accessibilità legacy possono scegliere di usare le funzionalità di accessibilità legacy impostando in modo esplicito questa opzione di AppContext su <code>true</code>.</span><span class="sxs-lookup"><span data-stu-id="7ef0e-113">Applications that target the .NET Framework 4.7.1 or later and want to preserve the legacy accessibility behavior can opt in to the use of legacy accessibility features by explicitly setting this AppContext switch to <code>true</code>.</span></span>|
|<span data-ttu-id="7ef0e-114">Ambito</span><span class="sxs-lookup"><span data-stu-id="7ef0e-114">Scope</span></span>|<span data-ttu-id="7ef0e-115">Secondario</span><span class="sxs-lookup"><span data-stu-id="7ef0e-115">Minor</span></span>|
|<span data-ttu-id="7ef0e-116">Versione</span><span class="sxs-lookup"><span data-stu-id="7ef0e-116">Version</span></span>|<span data-ttu-id="7ef0e-117">4.7.1</span><span class="sxs-lookup"><span data-stu-id="7ef0e-117">4.7.1</span></span>|
|<span data-ttu-id="7ef0e-118">Tipo</span><span class="sxs-lookup"><span data-stu-id="7ef0e-118">Type</span></span>|<span data-ttu-id="7ef0e-119">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="7ef0e-119">Retargeting</span></span>|
