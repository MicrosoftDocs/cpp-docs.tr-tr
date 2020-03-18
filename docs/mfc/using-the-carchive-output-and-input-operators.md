---
title: CArchive &lt;&lt; ve &gt;&gt; Işleçlerini kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], loading from previously stored values
- CArchive class [MFC], storing and loading objects
- CArchive class [MFC], operators
ms.assetid: 56aef326-02dc-4992-8282-f0a4b78a064e
ms.openlocfilehash: 8e175f35f2218341c69571c818711596180df4a6
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79442181"
---
# <a name="using-the-carchive-ltlt-and-gtgt-operators"></a>CArchive &lt;&lt; ve &gt;&gt; Işleçlerini kullanma

`CArchive`, <\< ve > basit veri türlerini yazmak ve okumak için > işleçleri ve bir dosyaya ve bu dosya üzerinden `CObject`.

#### <a name="to-store-an-object-in-a-file-via-an-archive"></a>Bir nesneyi bir arşiv aracılığıyla bir dosyada depolamak için

1. Aşağıdaki örnek, bir nesnenin bir arşiv aracılığıyla bir dosyada nasıl depolanacağını göstermektedir:

   [!code-cpp[NVC_MFCSerialization#7](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_1.cpp)]

#### <a name="to-load-an-object-from-a-value-previously-stored-in-a-file"></a>Daha önce bir dosyada depolanan bir değerden bir nesne yüklemek için

1. Aşağıdaki örnek, daha önce bir dosyada depolanan bir değerden bir nesnenin nasıl yükleneceğini göstermektedir:

   [!code-cpp[NVC_MFCSerialization#8](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_2.cpp)]

Genellikle, `CObject`türetilmiş sınıfların `Serialize` işlevlerde bir arşiv aracılığıyla bir dosyayı ve DECLARE_SERIALIZE makroıyla bildirdiğiniz bir arşiv aracılığıyla verileri depolayıp yüklersiniz. Bir `CArchive` nesnesine bir başvuru `Serialize` işleviniz geçirilir. `Serialize` işlevinin dosyadaki verileri yüklemek veya dosyaya veri depolamak için mi çağrıldığını öğrenmek için `CArchive` nesnesinin `IsLoading` işlevini çağırın.

Seri hale getirilebilir `CObject`türetilmiş sınıfın `Serialize` işlevi, genellikle aşağıdaki biçimdedir:

[!code-cpp[NVC_MFCSerialization#9](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_3.cpp)]

Yukarıdaki kod şablonu, belgenin `Serialize` işlevi (`CDocument`türetilmiş bir sınıf) için bir AppWizard 'ın oluşturduğu şekilde tamamen aynıdır. Bu kod şablonu, aşağıdaki örnekte olduğu gibi, depolama kodu ve yükleme kodu her zaman paralel olması gerektiğinden, incelenmesi daha kolay olan kodu yazmanıza yardımcı olur:

[!code-cpp[NVC_MFCSerialization#10](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_4.cpp)]

Kitaplığı, ilk işlenen olarak `CArchive` için **<\<** ve **>>** işleçlerini ve ikinci işlenen olarak aşağıdaki veri türlerini ve sınıf türlerini tanımlar:

||||
|-|-|-|
|`CObject*`|**Boyut** ve `CSize`|**float**|
|**WORD**|`CString`|**Nokta** ve `CPoint`|
|`DWORD`|**BAYT**|`RECT` ve `CRect`|
|**Çift**|**KALACAĞıNı**|`CTime` ve `CTimeSpan`|
|`Int`|**Colet para birimi**|`COleVariant`|
|`COleDateTime`|`COleDateTimeSpan`||

> [!NOTE]
>  `CObject`s 'yi bir arşiv aracılığıyla depolamak ve yüklemek ek bir değerlendirme gerektirir. Daha fazla bilgi için bkz. [bir arşiv aracılığıyla CObjects depolama ve yükleme](../mfc/storing-and-loading-cobjects-via-an-archive.md).

**CArchive <\<** ve **>>** işleçleri her zaman ilk işlenen olan `CArchive` nesnesine bir başvuru döndürür. Bu, aşağıda gösterildiği gibi işleçleri zincirlemenize olanak sağlar:

[!code-cpp[NVC_MFCSerialization#11](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_5.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Seri hale getirme: Bir Nesneyi Seri Hale Getirme](../mfc/serialization-serializing-an-object.md)
