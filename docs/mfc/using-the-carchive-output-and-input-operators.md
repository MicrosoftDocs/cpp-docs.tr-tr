---
title: CArchive &lt; &lt; ve &gt; &gt; Operatörler kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], loading from previously stored values
- CArchive class [MFC], storing and loading objects
- CArchive class [MFC], operators
ms.assetid: 56aef326-02dc-4992-8282-f0a4b78a064e
ms.openlocfilehash: 91ea565867cc0cb3b27ad9d5597037b637cb6544
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368970"
---
# <a name="using-the-carchive-ltlt-and-gtgt-operators"></a>CArchive &lt; &lt; ve &gt; &gt; Operatörler kullanma

`CArchive`basit \< veri türlerinin yanı sıra `CObject`dosyaya ve dosyadan <ve >> operatörlerini ve basit veri türlerini yazmave okumayı sağlar.

#### <a name="to-store-an-object-in-a-file-via-an-archive"></a>Bir nesneyi arşiv aracılığıyla dosyada depolamak için

1. Aşağıdaki örnek, bir nesnenin arşiv aracılığıyla dosyada nasıl depolanır olduğunu gösterir:

   [!code-cpp[NVC_MFCSerialization#7](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_1.cpp)]

#### <a name="to-load-an-object-from-a-value-previously-stored-in-a-file"></a>Bir nesneyi daha önce dosyada depolanmış bir değerden yüklemek için

1. Aşağıdaki örnek, bir nesnenin daha önce bir dosyada depolanan bir değerden nasıl yüklenirolduğunu gösterir:

   [!code-cpp[NVC_MFCSerialization#8](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_2.cpp)]

Genellikle, DECLARE_SERIALIZE makrosuyla beyan etmiş olması gereken `Serialize` -türetilmiş sınıfların `CObject`işlevlerinde bir arşiv aracılığıyla bir dosyaya veri depolar ve yüklersiniz. Bir `CArchive` nesneye yapılan başvuru `Serialize` işlevinize aktarılır. İşlevin `IsLoading` dosyadan `CArchive` veri yüklemek için çağrıldığını veya verileri dosyaya depolayıp depolamadığını belirlemek için nesnenin işlevini çağırırsınız. `Serialize`

Serileştirilebilir `Serialize` `CObject`türetilmiş sınıfın işlevi genellikle aşağıdaki formu oluşturur:

[!code-cpp[NVC_MFCSerialization#9](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_3.cpp)]

Yukarıdaki kod şablonu, AppWizard'ın belgenin `Serialize` işlevi için oluşturduğu şablonla tam `CDocument`olarak aynıdır (türetilmiş bir sınıf). Bu kod şablonu, aşağıdaki örnekte olduğu gibi, depolama kodu ve yükleme kodu her zaman paralel olması gerektiğinden, gözden geçirilmesi daha kolay kod yazmanıza yardımcı olur:

[!code-cpp[NVC_MFCSerialization#10](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_4.cpp)]

Kitaplık, ** < ** ilk **>>** operand `CArchive` olarak tanımlar ve işleçler ve ikinci operand olarak aşağıdaki veri türleri ve sınıf türleri:

||||
|-|-|-|
|`CObject*`|**BÜYÜKLÜK** ve`CSize`|**float**|
|**Kelime**|`CString`|**NOKTA** ve`CPoint`|
|`DWORD`|**BYTE**|`RECT` ve `CRect`|
|**Çift**|**Uzun**|`CTime` ve `CTimeSpan`|
|`Int`|**Colecurrency**|`COleVariant`|
|`COleDateTime`|`COleDateTimeSpan`||

> [!NOTE]
> Bir arşiv `CObject`üzerinden depolama ve yükleme ekstra dikkate gerektirir. Daha fazla bilgi için, [bir Arşiv üzerinden CObjects Depolama ve Yükleme](../mfc/storing-and-loading-cobjects-via-an-archive.md)bakın.

**CArchive <\< ** **>>** ve işleçleri her `CArchive` zaman ilk operand nesne, bir referans döndürür. Bu, aşağıda gösterildiği gibi operatörleri zincirlemenize olanak sağlar:

[!code-cpp[NVC_MFCSerialization#11](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_5.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Seri hale getirme: Bir Nesneyi Seri Hale Getirme](../mfc/serialization-serializing-an-object.md)
