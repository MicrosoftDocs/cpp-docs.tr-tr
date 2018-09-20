---
title: CArchive kullanarak &lt; &lt; ve &gt; &gt; işleçler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CArchive
dev_langs:
- C++
helpviewer_keywords:
- objects [MFC], loading from previously stored values
- CArchive class [MFC], storing and loading objects
- CArchive class [MFC], operators
ms.assetid: 56aef326-02dc-4992-8282-f0a4b78a064e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 49ea94258c163c241243934f41d55d896d0d1fa2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46372463"
---
# <a name="using-the-carchive-ltlt-and-gtgt-operators"></a>CArchive kullanarak &lt; &lt; ve &gt; &gt; işleçleri

`CArchive` sağlar <\< ve >> yazmak ve basit veri türleri okumak için işleçleri yanı `CObject`s için ve bir dosya.

#### <a name="to-store-an-object-in-a-file-via-an-archive"></a>Bir arşiv aracılığıyla bir dosyada bir nesneyi depolamak için

1. Aşağıdaki örnek, bir dosyada bir arşiv aracılığıyla bir nesneyi depolamak gösterilmektedir:

     [!code-cpp[NVC_MFCSerialization#7](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_1.cpp)]

#### <a name="to-load-an-object-from-a-value-previously-stored-in-a-file"></a>Daha önce bir dosyada depolanan bir değerden bir nesne yüklemek için

1. Aşağıdaki örnek, daha önce bir dosyada depolanan bir değerden bir nesne yüklenmeye gösterilmektedir:

     [!code-cpp[NVC_MFCSerialization#8](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_2.cpp)]

Genellikle, depolama ve Arşiv'de bir dosyaya gelen ve giden veri yükleme `Serialize` işlevlerini `CObject`-türetilmiş sınıfları ile DECLARE_SERIALIZE makrosu bildirildi gerekir. Bir başvuru bir `CArchive` nesnesi, `Serialize` işlevi. Çağırmanızı `IsLoading` işlevi `CArchive` belirlemek için nesne olup olmadığını `Serialize` işlevi çağrılıp çağrılmadığını dosyasından veri yükleme veya dosya verilerini depolamak için.

`Serialize` Seri hale getirilebilir bir işlevi `CObject`-türetilmiş sınıf genellikle aşağıdaki biçime sahiptir:

[!code-cpp[NVC_MFCSerialization#9](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_3.cpp)]

Yukarıdaki kodu tam olarak bir AppWizard oluşturur için aynı şablonudur `Serialize` belgenin işlevi (öğesinden türetilmiş bir sınıf `CDocument`). Bu kod şablon depolama kodunu ve yükleme kodunu her zaman paralel aşağıdaki gibi olması gerekir çünkü gözden geçirmek kolay kodlar yazmanıza yardımcı olur:

[!code-cpp[NVC_MFCSerialization#10](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_4.cpp)]

Kitaplığı tanımlar **< \<** ve **>>** işleçleri `CArchive` ilk işlenen aşağıdaki veri türleri ve ikinci işlenen olarak sınıf türleri olarak :

||||
|-|-|-|
|`CObject*`|**BOYUTU** ve `CSize`|**float**|
|**WORD**|`CString`|**NOKTASI** ve `CPoint`|
|`DWORD`|**BAYT**|`RECT` ve `CRect`|
|**çift**|**UZUN**|`CTime` ve `CTimeSpan`|
|`Int`|**COleCurrency**|`COleVariant`|
|`COleDateTime`|`COleDateTimeSpan`||

> [!NOTE]
>  Depolama ve yükleme `CObject`s bir arşiv aracılığıyla ek göz önünde bulundurarak gerektirir. Daha fazla bilgi için [depolama ve Arşiv yükleniyor Cobject'leri](../mfc/storing-and-loading-cobjects-via-an-archive.md).

**CArchive <\<**  ve **>>** işleçleri, her zaman bir başvuru döndürür `CArchive` ilk işlenen nesne. Bu, işleçler, zincir aşağıda gösterildiği gibi sağlar:

[!code-cpp[NVC_MFCSerialization#11](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_5.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[Seri hale getirme: Bir Nesneyi Seri Hale Getirme](../mfc/serialization-serializing-an-object.md)

