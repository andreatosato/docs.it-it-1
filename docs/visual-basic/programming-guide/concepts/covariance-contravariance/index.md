---
title: Covarianza e controvarianza (Visual Basic)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 59224c46-9931-466b-8c6e-3648c3e609c6
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 775e4512a5ff31c7059961f6332c6bdc0dc5247a
ms.openlocfilehash: 8d31737fc3d02c9caa4c13ef2d69e5e3192ef3af
ms.contentlocale: it-it
ms.lasthandoff: 08/11/2017

---
# <a name="covariance-and-contravariance-visual-basic"></a><span data-ttu-id="5882f-102">Covarianza e controvarianza (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5882f-102">Covariance and Contravariance (Visual Basic)</span></span>
<span data-ttu-id="5882f-103">In Visual Basic, covarianza e controvarianza abilitano la conversione implicita del riferimento per i tipi di matrice, i tipi delegati e gli argomenti di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="5882f-103">In Visual Basic, covariance and contravariance enable implicit reference conversion for array types, delegate types, and generic type arguments.</span></span> <span data-ttu-id="5882f-104">La covarianza mantiene la compatibilità dell'assegnazione e la controvarianza la inverte.</span><span class="sxs-lookup"><span data-stu-id="5882f-104">Covariance preserves assignment compatibility and contravariance reverses it.</span></span>  
  
 <span data-ttu-id="5882f-105">Il codice seguente illustra la differenza tra la compatibilità dell'assegnazione, covarianza e controvarianza.</span><span class="sxs-lookup"><span data-stu-id="5882f-105">The following code demonstrates the difference between assignment compatibility, covariance, and contravariance.</span></span>  
  
```vb  
' Assignment compatibility.   
Dim str As String = "test"  
' An object of a more derived type is assigned to an object of a less derived type.   
Dim obj As Object = str  
  
' Covariance.   
Dim strings As IEnumerable(Of String) = New List(Of String)()  
' An object that is instantiated with a more derived type argument   
' is assigned to an object instantiated with a less derived type argument.   
' Assignment compatibility is preserved.   
Dim objects As IEnumerable(Of Object) = strings  
  
' Contravariance.             
' Assume that there is the following method in the class:   
' Shared Sub SetObject(ByVal o As Object)  
' End Sub  
Dim actObject As Action(Of Object) = AddressOf SetObject  
  
' An object that is instantiated with a less derived type argument   
' is assigned to an object instantiated with a more derived type argument.   
' Assignment compatibility is reversed.   
Dim actString As Action(Of String) = actObject  
```  
  
 <span data-ttu-id="5882f-106">La covarianza per le matrici consente la conversione implicita di una matrice di un tipo più derivato in una matrice di un tipo meno derivato.</span><span class="sxs-lookup"><span data-stu-id="5882f-106">Covariance for arrays enables implicit conversion of an array of a more derived type to an array of a less derived type.</span></span> <span data-ttu-id="5882f-107">Ma questa operazione non è indipendente dai tipi, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="5882f-107">But this operation is not type safe, as shown in the following code example.</span></span>  
  
```vb  
Dim array() As Object = New String(10) {}  
' The following statement produces a run-time exception.  
' array(0) = 10  
```  
  
 <span data-ttu-id="5882f-108">Il supporto di covarianza e controvarianza per i gruppi di metodi consente la corrispondenza delle firme del metodo con i tipi delegati.</span><span class="sxs-lookup"><span data-stu-id="5882f-108">Covariance and contravariance support for method groups allows for matching method signatures with delegate types.</span></span> <span data-ttu-id="5882f-109">Ciò consente di assegnare ai delegati non solo i metodi con firme corrispondenti, ma anche i metodi che restituiscono più tipi derivati (covarianza) o accettano parametri con meno tipi derivati (controvarianza) rispetto a quelli specificati dal tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="5882f-109">This enables you to assign to delegates not only methods that have matching signatures, but also methods that return more derived types (covariance) or that accept parameters that have less derived types (contravariance) than that specified by the delegate type.</span></span> <span data-ttu-id="5882f-110">Per altre informazioni, vedere [Varianza nei delegati (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) e [Uso della varianza nei delegati (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="5882f-110">For more information, see [Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) and [Using Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span></span>  
  
 <span data-ttu-id="5882f-111">L'esempio di codice seguente illustra il supporto di covarianza e controvarianza per i gruppi di metodi.</span><span class="sxs-lookup"><span data-stu-id="5882f-111">The following code example shows covariance and contravariance support for method groups.</span></span>  
  
```vb  
Shared Function GetObject() As Object  
    Return Nothing  
End Function  
  
Shared Sub SetObject(ByVal obj As Object)  
End Sub  
  
Shared Function GetString() As String  
    Return ""  
End Function  
  
Shared Sub SetString(ByVal str As String)  
  
End Sub  
  
Shared Sub Test()  
    ' Covariance. A delegate specifies a return type as object,  
    ' but you can assign a method that returns a string.  
    Dim del As Func(Of Object) = AddressOf GetString  
  
    ' Contravariance. A delegate specifies a parameter type as string,  
    ' but you can assign a method that takes an object.  
    Dim del2 As Action(Of String) = AddressOf SetObject  
End Sub  
```  
  
 <span data-ttu-id="5882f-112">In .NET Framework 4 o versioni più recenti Visual Basic supporta la covarianza e la controvarianza nelle interfacce e nei delegati generici e consente la conversione implicita dei parametri di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="5882f-112">In .NET Framework 4 or later Visual Basic support covariance and contravariance in generic interfaces and delegates and allow for implicit conversion of generic type parameters.</span></span> <span data-ttu-id="5882f-113">Per altre informazioni, vedere [Varianza nelle interfacce generiche (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md) e [Varianza nei delegati (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="5882f-113">For more information, see [Variance in Generic Interfaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md) and [Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).</span></span>  
  
 <span data-ttu-id="5882f-114">L'esempio di codice seguente illustra la conversione implicita del riferimento per le interfacce generiche.</span><span class="sxs-lookup"><span data-stu-id="5882f-114">The following code example shows implicit reference conversion for generic interfaces.</span></span>  
  
```vb  
Dim strings As IEnumerable(Of String) = New List(Of String)  
Dim objects As IEnumerable(Of Object) = strings  
```  
  
 <span data-ttu-id="5882f-115">Le interfacce o i delegati generici sono detti *varianti* se i relativi parametri generici vengono dichiarati come covarianti o controvarianti.</span><span class="sxs-lookup"><span data-stu-id="5882f-115">A generic interface or delegate is called *variant* if its generic parameters are declared covariant or contravariant.</span></span> <span data-ttu-id="5882f-116">Visual Basic consente di creare i propri delegati e interfacce varianti.</span><span class="sxs-lookup"><span data-stu-id="5882f-116">Visual Basic enables you to create your own variant interfaces and delegates.</span></span> <span data-ttu-id="5882f-117">Per altre informazioni, vedere [Creazione di interfacce generiche varianti (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md) e [Varianza nei delegati (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="5882f-117">For more information, see [Creating Variant Generic Interfaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md) and [Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="5882f-118">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="5882f-118">Related Topics</span></span>  
  
|<span data-ttu-id="5882f-119">Titolo</span><span class="sxs-lookup"><span data-stu-id="5882f-119">Title</span></span>|<span data-ttu-id="5882f-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5882f-120">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="5882f-121">Varianza nelle interfacce generiche (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5882f-121">Variance in Generic Interfaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)|<span data-ttu-id="5882f-122">Illustra la covarianza e la controvarianza nelle interfacce generiche e fornisce un elenco di interfacce generiche variant in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5882f-122">Discusses covariance and contravariance in generic interfaces and provides a list of variant generic interfaces in the .NET Framework.</span></span>|  
|[<span data-ttu-id="5882f-123">Creazione di interfacce generiche varianti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5882f-123">Creating Variant Generic Interfaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md)|<span data-ttu-id="5882f-124">Spiega come creare interfacce varianti personalizzate.</span><span class="sxs-lookup"><span data-stu-id="5882f-124">Shows how to create custom variant interfaces.</span></span>|  
|[<span data-ttu-id="5882f-125">Uso della varianza nelle interfacce per le raccolte generiche (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5882f-125">Using Variance in Interfaces for Generic Collections (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)|<span data-ttu-id="5882f-126">Spiega come il supporto di covarianza e controvarianza nelle interfacce <xref:System.Collections.Generic.IEnumerable%601> e <xref:System.IComparable%601> consente di riutilizzare il codice.</span><span class="sxs-lookup"><span data-stu-id="5882f-126">Shows how covariance and contravariance support in the <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IComparable%601> interfaces can help you reuse code.</span></span>|  
|[<span data-ttu-id="5882f-127">Varianza nei delegati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5882f-127">Variance in Delegates (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)|<span data-ttu-id="5882f-128">Illustra la covarianza e la controvarianza nei delegati generici e non generici e offre un elenco di delegati generici varianti in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5882f-128">Discusses covariance and contravariance in generic and non-generic delegates and provides a list of variant generic delegates in the .NET Framework.</span></span>|  
|[<span data-ttu-id="5882f-129">Uso della varianza nei delegati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5882f-129">Using Variance in Delegates (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md)|<span data-ttu-id="5882f-130">Spiega come usare il supporto di covarianza e controvarianza nei delegati non generici per la corrispondenza delle firme del metodo con i tipi delegati.</span><span class="sxs-lookup"><span data-stu-id="5882f-130">Shows how to use covariance and contravariance support in non-generic delegates to match method signatures with delegate types.</span></span>|  
|[<span data-ttu-id="5882f-131">Utilizzo della varianza per i delegati generici Func e Action (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5882f-131">Using Variance for Func and Action Generic Delegates (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)|<span data-ttu-id="5882f-132">Spiega come il supporto di covarianza e controvarianza nei delegati `Func` e `Action` consente di riutilizzare il codice.</span><span class="sxs-lookup"><span data-stu-id="5882f-132">Shows how covariance and contravariance support in the `Func` and `Action` delegates can help you reuse code.</span></span>|
