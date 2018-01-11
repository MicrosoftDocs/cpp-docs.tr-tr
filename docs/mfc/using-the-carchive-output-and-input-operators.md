---
title: "CArchive kullanarak &lt; &lt; ve &gt; &gt; işleçleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CArchive
dev_langs: C++
helpviewer_keywords:
- objects [MFC], loading from previously stored values
- CArchive class [MFC], storing and loading objects
- CArchive class [MFC], operators
ms.assetid: 56aef326-02dc-4992-8282-f0a4b78a064e
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0ab2da8cc885f94bf15164ff17fdef2b2af13a41
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="using-the-carchive-ltlt-and-gtgt-operators"></a>CArchive kullanarak &lt; &lt; ve &gt; &gt; işleçleri
`CArchive`sağlar <\< ve >> yazma ve okuma basit veri türleri için işleçleri yanı `CObject`s için ve bir dosya.  
  
#### <a name="to-store-an-object-in-a-file-via-an-archive"></a>Bir arşiv aracılığıyla bir dosyada bir nesne depolamak için  
  
1.  Aşağıdaki örnek, bir dosyada bir arşiv aracılığıyla bir nesne depolamak gösterilmektedir:  
  
     [!code-cpp[NVC_MFCSerialization#7](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_1.cpp)]  
  
#### <a name="to-load-an-object-from-a-value-previously-stored-in-a-file"></a>Daha önce bir dosyada depolanan bir değerden bir nesne yüklemek için  
  
1.  Aşağıdaki örnek, daha önce bir dosyada depolanan bir değerden bir nesne yüklenmeye gösterilmektedir:  
  
     [!code-cpp[NVC_MFCSerialization#8](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_2.cpp)]  
  
 Genellikle, depolamak ve yüklemek için ve bir arşiv aracılığıyla bir dosyadan veri `Serialize` işlevlerini `CObject`-türetilmiş ile bildirilen gerekir sınıfları **DECLARE_SERIALIZE** makrosu. Bir başvuru bir `CArchive` nesne iletilir, `Serialize` işlevi. Çağırmanız `IsLoading` işlevinin `CArchive` belirlemek için nesne olup olmadığını `Serialize` işlevi çağrılıp çağrılmadığını dosyasından veri yükleme veya dosya verileri depolamak için.  
  
 `Serialize` Bir serileştirilebilir işlevinin `CObject`-türetilmiş sınıf genellikle aşağıdaki biçime sahiptir:  
  
 [!code-cpp[NVC_MFCSerialization#9](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_3.cpp)]  
  
 Yukarıdaki kod şablon tam olarak aynı AppWizard oluşturur `Serialize` belgenin işlevi (öğesinden türetilmiş bir sınıf **CDocument)**. Bu kod şablon depolanmasını kodu ve yükleme kodu her zaman aşağıdaki örnekteki paralel olması gerektiğinden, gözden geçirmek, daha kolay olan kod yazmanıza yardımcı olur:  
  
 [!code-cpp[NVC_MFCSerialization#10](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_4.cpp)]  
  
 Kitaplık tanımlar  **< \<**  ve  **>>**  işleçlerini `CArchive` ilk işlenen ve aşağıdaki veri türlerini ve ikinci işlenen olarak sınıf türleri olarak :  
  
||||  
|-|-|-|  
|`CObject*`|**Boyut ve CSize**|**float**|  
|**WORD**|`CString`|**NOKTASI** ve`CPoint`|  
|`DWORD`|**BAYT**|`RECT`ve`CRect`|  
|**Çift**|**UZUN**|`CTime`ve`CTimeSpan`|  
|`Int`|**COleCurrency**|`COleVariant`|  
|`COleDateTime`|`COleDateTimeSpan`||  
  
> [!NOTE]
>  Depolama ve yükleme `CObject`s bir arşiv aracılığıyla ek göz önünde bulundurarak gerektirir. Daha fazla bilgi için bkz: [saklama ve bir Arşiv yüklenirken Cobject'leri](../mfc/storing-and-loading-cobjects-via-an-archive.md).  
  
 **CArchive <\<**  ve  **>>**  işleçleri her zaman bir başvuru döndürür `CArchive` ilk işleneni nesnesi. Bu, işleçler zincir aşağıda gösterildiği gibi sağlar:  
  
 [!code-cpp[NVC_MFCSerialization#11](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_5.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Seri hale getirme: Bir Nesneyi Seri Hale Getirme](../mfc/serialization-serializing-an-object.md)

