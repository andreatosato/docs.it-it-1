---
title: Supporto per valori DPI elevato in Windows Form
ms.custom: 
ms.date: 05/16/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- High DPI in Windows Forms
- Dynamic rescaling in Windows Forms
- Windows Forms layout
- Windows Forms dynamic resizing
ms.assetid: 075ea4c3-900c-4f8a-9dd2-13ea6804346b
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a2461c507c0d2a27f1c2bdfe85327d11318b17ee
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="high-dpi-support-in-windows-forms"></a><span data-ttu-id="c71a2-102">Supporto per valori DPI elevato in Windows Form</span><span class="sxs-lookup"><span data-stu-id="c71a2-102">High DPI support in Windows Forms</span></span>

<span data-ttu-id="c71a2-103">A partire dal 4.7 di .NET Framework, Windows Form include miglioramenti per valori DPI alti comuni e scenari di risoluzione dinamici.</span><span class="sxs-lookup"><span data-stu-id="c71a2-103">Starting with the .NET Framework 4.7, Windows Forms includes enhancements for common high DPI and dynamic DPI scenarios.</span></span> <span data-ttu-id="c71a2-104">tra cui:</span><span class="sxs-lookup"><span data-stu-id="c71a2-104">These include:</span></span> 

- <span data-ttu-id="c71a2-105">Miglioramenti nella scalabilità e layout di un numero di Windows Form controlli, ad esempio il <xref:System.Windows.Forms.MonthCalendar> controllo e <xref:System.Windows.Forms.CheckedListBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="c71a2-105">Improvements in the scaling and layout of a number of Windows Forms controls, such as the <xref:System.Windows.Forms.MonthCalendar> control and the <xref:System.Windows.Forms.CheckedListBox> control.</span></span> 

- <span data-ttu-id="c71a2-106">Scalabilità-passaggio singolo.</span><span class="sxs-lookup"><span data-stu-id="c71a2-106">Single-pass scaling.</span></span>  <span data-ttu-id="c71a2-107">In .NET Framework 4.6 e versioni precedenti, la scalabilità è stata eseguita tramite più passaggi, che ha provocato alcuni controlli scalabilità più necessarie.</span><span class="sxs-lookup"><span data-stu-id="c71a2-107">In the .NET Framework 4.6 and earlier versions, scaling was performed through multiple passes, which caused some controls to be scaled more than was necessary.</span></span>

- <span data-ttu-id="c71a2-108">Supporto per scenari di risoluzione dinamici in cui l'utente modifica il fattore di scala o DPI dopo che è stata avviata un'applicazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="c71a2-108">Support for dynamic DPI scenarios in which the user changes the DPI or scale factor after a Windows Forms application has been launched.</span></span>

<span data-ttu-id="c71a2-109">Nelle versioni di .NET Framework a partire dal 4.7 di .NET Framework, supporto avanzato per valori DPI elevato è una funzionalità di consenso esplicito.</span><span class="sxs-lookup"><span data-stu-id="c71a2-109">In versions of the .NET Framework starting with the .NET Framework 4.7, enhanced high DPI support is an opt-in feature.</span></span> <span data-ttu-id="c71a2-110">È necessario configurare l'applicazione per sfruttare i vantaggi.</span><span class="sxs-lookup"><span data-stu-id="c71a2-110">You must configure your application to take advantage of it.</span></span>

## <a name="configuring-your-windows-forms-app-for-high-dpi-support"></a><span data-ttu-id="c71a2-111">Configurare l'app di Windows Form per il supporto per valori DPI elevato</span><span class="sxs-lookup"><span data-stu-id="c71a2-111">Configuring your Windows Forms app for high DPI support</span></span>

<span data-ttu-id="c71a2-112">Le nuove funzionalità di Windows Form che supportano il riconoscimento DPI elevato sono disponibili solo nelle applicazioni destinate al 4.7 di .NET Framework e sono in esecuzione nei sistemi operativi Windows a partire da Windows 10 creatori di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="c71a2-112">The new Windows Forms features that support high DPI awareness are available only in applications that target the .NET Framework 4.7 and are running on Windows operating systems starting with the Windows 10 Creators Update.</span></span> 

<span data-ttu-id="c71a2-113">Inoltre, per configurare il supporto DPI elevato nell'applicazione Windows Form, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c71a2-113">In addition, to configure high DPI support in your Windows Forms application, you must do the following:</span></span>

- <span data-ttu-id="c71a2-114">Dichiarare la compatibilità con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="c71a2-114">Declare compatibility with Windows 10.</span></span>

  <span data-ttu-id="c71a2-115">A tale scopo, aggiungere quanto segue al file manifesto:</span><span class="sxs-lookup"><span data-stu-id="c71a2-115">To do this, add the following to your manifest file:</span></span>

  ```xml
  <compatibility xmlns="urn:schemas-microsoft.comn:compatibility.v1">
    <application>
      <!-- Windows 10 compatibility -->
      <supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
    </application>
  </compatibility>
  ```

- <span data-ttu-id="c71a2-116">Abilitare la consapevolezza DPI monitor il *app* file.</span><span class="sxs-lookup"><span data-stu-id="c71a2-116">Enable per-monitor DPI awareness in the *app.config* file.</span></span>

  <span data-ttu-id="c71a2-117">Introduce un nuovo Windows Form [ `<System.Windows.Forms.ApplicationConfigurationSection>` ](../../../docs/framework/configure-apps/file-schema/winforms/index.md) elemento per supportare nuove funzionalità e le personalizzazioni aggiunte a partire dal 4.7 di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c71a2-117">Windows Forms introduces a new [`<System.Windows.Forms.ApplicationConfigurationSection>`](../../../docs/framework/configure-apps/file-schema/winforms/index.md) element to support new features and customizations added starting with the .NET Framework 4.7.</span></span> <span data-ttu-id="c71a2-118">Per sfruttare i vantaggi delle nuove funzionalità che supportano valori DPI alti, aggiungere quanto segue al file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c71a2-118">To take advantage of the new features that support high DPI, add the following to your application configuration file.</span></span>   

  ```xml
  <System.Windows.Forms.ApplicationConfigurationSection>
    <add key="DpiAwareness" value="PerMonitorV2" />
  </System.Windows.Forms.ApplicationConfigurationSection>      
  ```
   
  > [!IMPORTANT]
  > <span data-ttu-id="c71a2-119">Nelle versioni precedenti di .NET Framework, il manifesto è utilizzato per aggiungere supporto per valori DPI elevato.</span><span class="sxs-lookup"><span data-stu-id="c71a2-119">In previous versions of the .NET Framework, you used the manifest to add high DPI support.</span></span> <span data-ttu-id="c71a2-120">Questo approccio non è più consigliato, perché esegue l'override delle impostazioni definite nel file app. config.</span><span class="sxs-lookup"><span data-stu-id="c71a2-120">This approach is no longer recommended, since it overrides settings defined on the app.config file.</span></span>
   
- <span data-ttu-id="c71a2-121">Chiamare il metodo statico <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="c71a2-121">Call the static <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>
   
  <span data-ttu-id="c71a2-122">Deve essere la prima chiamata al metodo nel punto di ingresso dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c71a2-122">This should be the first method call in your application entry point.</span></span> <span data-ttu-id="c71a2-123">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c71a2-123">For example:</span></span>
   
  ```csharp
  static void Main()
  {
      Application.EnableVisualStyles();
      Application.SetCompatibleTextRenderingDefault(false);
      Application.Run(new Form2());   
  }
  ```

## <a name="opting-out-of-individual-high-dpi-features"></a><span data-ttu-id="c71a2-124">Rifiuto esplicito singole funzionalità DPI elevata</span><span class="sxs-lookup"><span data-stu-id="c71a2-124">Opting out of individual high DPI features</span></span>

<span data-ttu-id="c71a2-125">L'impostazione di `DpiAwareness` valore `PerMonitorV2` Abilita le funzionalità di riconoscimento DPI elevate tutti supportate da versioni di .NET Framework a partire dal 4.7 di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c71a2-125">Setting the `DpiAwareness` value to `PerMonitorV2` enables all high DPI awareness features supported by .NET Framework versions starting with the .NET Framework 4.7.</span></span> <span data-ttu-id="c71a2-126">In genere, questo è sufficiente per la maggior parte delle applicazioni Windows Form.</span><span class="sxs-lookup"><span data-stu-id="c71a2-126">Typically, this is adequate for most Windows Forms applications.</span></span> <span data-ttu-id="c71a2-127">Tuttavia, è consigliabile escludere uno o più delle singole funzionalità.</span><span class="sxs-lookup"><span data-stu-id="c71a2-127">However, you may want to opt out of one or more individual features.</span></span> <span data-ttu-id="c71a2-128">Il motivo per eseguire questa operazione più importante è che il codice dell'applicazione esistente già gestisce tale funzionalità.</span><span class="sxs-lookup"><span data-stu-id="c71a2-128">The most important reason for doing this is that your existing application code already handles that feature.</span></span>  <span data-ttu-id="c71a2-129">Ad esempio, se l'applicazione gestisce il ridimensionamento automatico, è consigliabile disabilitare la funzionalità di ridimensionamento automatico, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="c71a2-129">For example, if your application handles auto scaling, you might want to disable the auto-resizing feature as follows:</span></span>

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="DpiAwareness" value="PerMonitorV2" />
  <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" /> 
</System.Windows.Forms.ApplicationConfigurationSection>    
```

<span data-ttu-id="c71a2-130">Per un elenco di singole chiavi e i relativi valori, vedere [elemento configurazione di Windows Form Add](../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md).</span><span class="sxs-lookup"><span data-stu-id="c71a2-130">For a list of individual keys and their values, see [Windows Forms Add Configuration Element](../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md).</span></span>

## <a name="new-dpi-change-events"></a><span data-ttu-id="c71a2-131">Nuovi eventi di modifica DPI</span><span class="sxs-lookup"><span data-stu-id="c71a2-131">New DPI change events</span></span>

<span data-ttu-id="c71a2-132">A partire dal 4.7 di .NET Framework, tre nuovi eventi consentono di gestire a livello di programmazione le modifiche dinamiche DPI:</span><span class="sxs-lookup"><span data-stu-id="c71a2-132">Starting with the .NET Framework 4.7, three new events allow you to programmatically handle dynamic DPI changes:</span></span>

- <span data-ttu-id="c71a2-133"><xref:System.Windows.Forms.Control.DpiChangedAfterParent>, che viene generato quando l'impostazione DPI per un controllo viene modificato a livello di codice dopo un evento di modifica DPI per il controllo padre o modulo che si è verificato.</span><span class="sxs-lookup"><span data-stu-id="c71a2-133"><xref:System.Windows.Forms.Control.DpiChangedAfterParent>, which is fired when the DPI setting for a control is changed programmatically after a DPI change event for it's parent control or form has occurred.</span></span>
- <span data-ttu-id="c71a2-134"><xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, che viene generato quando l'impostazione DPI per un controllo viene modificato a livello di codice prima di un evento di modifica DPI per relativo controllo padre o modulo che si è verificato.</span><span class="sxs-lookup"><span data-stu-id="c71a2-134"><xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, which is fired when the DPI setting for a control is changed programmatically before a DPI change event for its parent control or form has occurred.</span></span>
- <span data-ttu-id="c71a2-135"><xref:System.Windows.Forms.Form.DpiChanged>, che viene generato quando viene modificata l'impostazione DPI sul dispositivo di visualizzazione in cui il modulo è attualmente visualizzato.</span><span class="sxs-lookup"><span data-stu-id="c71a2-135"><xref:System.Windows.Forms.Form.DpiChanged>, which is fired when the DPI setting changes on the display device where the form is currently displayed.</span></span>

## <a name="new-helper-methods-and-properties"></a><span data-ttu-id="c71a2-136">Le proprietà e nuovi metodi di supporto</span><span class="sxs-lookup"><span data-stu-id="c71a2-136">New helper methods and properties</span></span>

<span data-ttu-id="c71a2-137">Il 4.7 di .NET Framework aggiunge anche il numero di nuovi metodi di supporto e le proprietà che forniscono informazioni sul ridimensionamento DPI e consentono di eseguire il ridimensionamento DPI.</span><span class="sxs-lookup"><span data-stu-id="c71a2-137">The .NET Framework 4.7 also adds a number of new helper methods and properties that provide information about DPI scaling and allow you to perform DPI scaling.</span></span> <span data-ttu-id="c71a2-138">tra cui:</span><span class="sxs-lookup"><span data-stu-id="c71a2-138">These include:</span></span>

- <span data-ttu-id="c71a2-139"><xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>, che consente di convertire un valore da coordinate logiche ai pixel del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c71a2-139"><xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>, which converts a value from logical to device pixels.</span></span>

- <span data-ttu-id="c71a2-140"><xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>, che ridimensiona un'immagine bitmap in DPI per un dispositivo logico.</span><span class="sxs-lookup"><span data-stu-id="c71a2-140"><xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>, which scales a bitmap image to the logical DPI for a device.</span></span>

- <span data-ttu-id="c71a2-141"><xref:System.Windows.Forms.Control.DeviceDpi%2A>, che restituisce il valore DPI per il dispositivo corrente.</span><span class="sxs-lookup"><span data-stu-id="c71a2-141"><xref:System.Windows.Forms.Control.DeviceDpi%2A>, which returns the DPI for the current device.</span></span>

## <a name="versioning-considerations"></a><span data-ttu-id="c71a2-142">Considerazioni sulla gestione delle versioni</span><span class="sxs-lookup"><span data-stu-id="c71a2-142">Versioning considerations</span></span>

<span data-ttu-id="c71a2-143">Oltre a eseguire in .NET Framework 4.7 e creatori di aggiornamento di Windows 10, l'applicazione possono essere eseguite anche in un ambiente in cui non è compatibile con i miglioramenti di DPI elevati.</span><span class="sxs-lookup"><span data-stu-id="c71a2-143">In addition to running on .NET Framework 4.7 and Windows 10 Creators Update, your application may also run in an environment in which it isn't compatible with high DPI improvements.</span></span> <span data-ttu-id="c71a2-144">In questo caso, è necessario sviluppare un fallback per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c71a2-144">In this case, you'll need to develop a fallback for your application.</span></span> <span data-ttu-id="c71a2-145">A tale scopo eseguire [disegno personalizzato](./controls/user-drawn-controls.md) per gestire la scalabilità.</span><span class="sxs-lookup"><span data-stu-id="c71a2-145">You can do this to perform [custom drawing](./controls/user-drawn-controls.md) to handle scaling.</span></span>

<span data-ttu-id="c71a2-146">A tale scopo, è necessario anche determinare il sistema operativo in cui l'app è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c71a2-146">To do this, you also need to determine the operating system on which your app is running.</span></span> <span data-ttu-id="c71a2-147">È possibile farlo con codice simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="c71a2-147">You can do that with code like the following:</span></span>

```csharp
// Create a reference to the OS version of Windows 10 Creators Update.
Version OsMinVersion = new Version(10, 0, 15063, 0);

// Access the platform/version of the current OS.
Console.WriteLine(Environment.OSVersion.Platform.ToString());
Console.WriteLine(Environment.OSVersion.VersionString);

// Compare the current version to the minimum required version.
Console.WriteLine(Environment.OSVersion.Version.CompareTo(OsMinVersion));
```

<span data-ttu-id="c71a2-148">Si noti che l'applicazione non correttamente rileva Windows 10, se non è stato elencato come un sistema operativo supportato nel manifesto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c71a2-148">Note that your application won't successfully detect Windows 10 if it wasn't listed as a supported operating system in the application manifest.</span></span>

<span data-ttu-id="c71a2-149">È inoltre possibile controllare la versione di .NET Framework è stata creata l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="c71a2-149">You can also check the version of the .NET Framework that the application was built against:</span></span>

```csharp
Console.WriteLine(AppDomain.CurrentDomain.SetupInformation.TargetFrameworkName);
```

## <a name="see-also"></a><span data-ttu-id="c71a2-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c71a2-150">See also</span></span>

[<span data-ttu-id="c71a2-151">Windows Form aggiungere l'elemento di configurazione</span><span class="sxs-lookup"><span data-stu-id="c71a2-151">Windows Forms Add Configuration Element</span></span>](../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)  
[<span data-ttu-id="c71a2-152">Regolazione delle dimensioni e della scala di Windows Form</span><span class="sxs-lookup"><span data-stu-id="c71a2-152">Adjusting the Size and Scale of Windows Forms</span></span>](../../../docs/framework/winforms/adjusting-the-size-and-scale-of-windows-forms.md)