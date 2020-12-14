---
description: 'Hakkında daha fazla bilgi edinin: CArchive &lt; &lt; ve &gt; &gt; işleçlerini kullanma'
title: CArchive &lt; &lt; ve &gt; &gt; işleçlerini kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], loading from previously stored values
- CArchive class [MFC], storing and loading objects
- CArchive class [MFC], operators
ms.assetid: 56aef326-02dc-4992-8282-f0a4b78a064e
ms.openlocfilehash: a3e6d65ac2ff024f779edb6d23a43f7331628c3b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314574"
---
# <a name="using-the-carchive-ltlt-and-gtgt-operators"></a>CArchive &lt; &lt; ve &gt; &gt; işleçlerini kullanma

`CArchive` , \< and > bir dosyanın yanı sıra basit veri türlerini yazmak ve okumak için <> işleçleri sağlar `CObject` .

#### <a name="to-store-an-object-in-a-file-via-an-archive"></a>Bir nesneyi bir arşiv aracılığıyla bir dosyada depolamak için

1. Aşağıdaki örnek, bir nesnenin bir arşiv aracılığıyla bir dosyada nasıl depolanacağını göstermektedir:

   [!code-cpp[NVC_MFCSerialization#7](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_1.cpp)]

#### <a name="to-load-an-object-from-a-value-previously-stored-in-a-file"></a>Daha önce bir dosyada depolanan bir değerden bir nesne yüklemek için

1. Aşağıdaki örnek, daha önce bir dosyada depolanan bir değerden bir nesnenin nasıl yükleneceğini göstermektedir:

   [!code-cpp[NVC_MFCSerialization#8](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_2.cpp)]

Genellikle, ' ın ' de `Serialize` `CObject` DECLARE_SERIALIZE makrosuna göre bildirdiğiniz, türetilmiş sınıfların işlevlerinde bulunan bir arşiv aracılığıyla bir dosyadan veri depolayıp yükler. Bir `CArchive` nesneye başvuru, `Serialize` işlevinizi geçti. `IsLoading` `CArchive` `Serialize` İşlevin, dosyadaki verileri yüklemek ya da verileri depolamak için döndürülüp çağrılmadığını anlamak için nesnesinin işlevini çağırın.

`Serialize`Seri hale getirilebilir türetilmiş bir `CObject` sınıfın işlevi, genellikle aşağıdaki biçimdedir:

[!code-cpp[NVC_MFCSerialization#9](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_3.cpp)]

Yukarıdaki kod şablonu, `Serialize` belgenin (öğesinden türetilmiş bir sınıf) işlevi için bir AppWizard tarafından oluşturulan ile tamamen aynıdır `CDocument` . Bu kod şablonu, aşağıdaki örnekte olduğu gibi, depolama kodu ve yükleme kodu her zaman paralel olması gerektiğinden, incelenmesi daha kolay olan kodu yazmanıza yardımcı olur:

[!code-cpp[NVC_MFCSerialization#10](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_4.cpp)]

Kitaplığı, **`<<`** **`>>`** `CArchive` ikinci işlenen olarak ilk işlenen ve aşağıdaki veri türleri ve sınıf türleri için ve işleçlerini tanımlar:

:::row:::
   :::column span="":::
      `BYTE`\
      `CObject*`\
      `COleCurrency`\
      `COleDateTime`\
      `COleDateTimeSpan`
   :::column-end:::
   :::column span="":::
      `COleVariant`\
      `CString`\
      `CTime` ' `CTimeSpan`\
      `Double`
   :::column-end:::
   :::column span="":::
      `DWORD`\
      `Float`\
      `Int`\
      `LONG`
   :::column-end:::
   :::column span="":::
      `POINT` ' `CPoint`\
      `RECT` ' `CRect`\
      `SIZE` ' `CSize`\
      `WORD`
   :::column-end:::
:::row-end:::

> [!NOTE]
> `CObject`Bir arşiv aracılığıyla depolamak ve yüklemek ek bir değerlendirme gerektirir. Daha fazla bilgi için bkz. [bir arşiv aracılığıyla CObjects depolama ve yükleme](../mfc/storing-and-loading-cobjects-via-an-archive.md).

`CArchive` **`<<`** Ve **`>>`** işleçleri her zaman, `CArchive` ilk işlenen olan nesneye bir başvuru döndürür. Bu, aşağıda gösterildiği gibi işleçleri zincirlemenize olanak sağlar:

[!code-cpp[NVC_MFCSerialization#11](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_5.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Serileştirme: bir nesneyi seri hale getirme](../mfc/serialization-serializing-an-object.md)
