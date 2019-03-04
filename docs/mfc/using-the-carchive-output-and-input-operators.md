---
title: CArchive kullanarak &lt; &lt; ve &gt; &gt; işleçleri
ms.date: 11/04/2016
f1_keywords:
- CArchive
helpviewer_keywords:
- objects [MFC], loading from previously stored values
- CArchive class [MFC], storing and loading objects
- CArchive class [MFC], operators
ms.assetid: 56aef326-02dc-4992-8282-f0a4b78a064e
ms.openlocfilehash: 9b4192e79b68388e45eb9837e056bbd881de2933
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57259678"
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

## <a name="see-also"></a>Ayrıca bkz.

[Seri hale getirme: Bir nesneyi seri hale getirme](../mfc/serialization-serializing-an-object.md)
