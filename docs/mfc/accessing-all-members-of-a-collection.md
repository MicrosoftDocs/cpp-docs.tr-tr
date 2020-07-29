---
title: Bir Koleksiyonun Tüm Üyelerine Erişme
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, collections
- enumerations [MFC]
- enumerating collections [MFC]
- collections [MFC], accessing
- collection classes [MFC]
- ', '
- ', '
- ', '
- ', '
- ', '
- ', '
- ', '
ms.assetid: 7bbae518-062e-4393-81f9-b22abd2e5f59
ms.openlocfilehash: cc058e6e4bf0058adb13f83e7ea071ebb4570ec4
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214184"
---
# <a name="accessing-all-members-of-a-collection"></a>Bir Koleksiyonun Tüm Üyelerine Erişme

MFC dizi koleksiyonu sınıfları — şablon tabanlı ve değil), öğelerine erişmek için dizinleri kullanır. MFC listesi ve eşleme koleksiyonu sınıfları — şablon tabanlı ve değil), koleksiyonda belirli bir konumu belirtmek için **konum** türünde bir gösterge kullanır. Bu koleksiyonların bir veya daha fazla üyesine erişmek için, önce konum göstergesini başlatın ve sonra bu konumu koleksiyona art arda geçirin ve sonraki öğeyi döndürmesini isteyin. Koleksiyon, yinelemenin ilerlemesi hakkında durum bilgilerinin korunmasından sorumludur. Bu bilgiler konum göstergesinde tutulur. Ancak, belirli bir konum verildiğinde, koleksiyon bir sonraki öğeyi döndürmekten sorumludur.

Aşağıdaki yordamlarda, MFC ile birlikte sunulan üç ana koleksiyon türünün nasıl yineyapılacağı gösterilmektedir:

- [Bir diziyi yineleme](#_core_to_iterate_an_array)

- [Liste yineleme](#_core_to_iterate_a_list)

- [Eşleme yineleme](#_core_to_iterate_a_map)

### <a name="to-iterate-an-array"></a><a name="_core_to_iterate_an_array"></a>Bir diziyi yinelemek için

1. Üye işleviyle sıralı dizin numaralarını kullanın `GetAt` :

   [!code-cpp[NVC_MFCCollections#12](codesnippet/cpp/accessing-all-members-of-a-collection_1.cpp)]

   Bu örnek, nesnelere işaretçiler içeren türü belirlenmiş bir işaretçi dizisi kullanır `CPerson` . Dizi `CObArray` , şablon olmayan önceden tanımlanmış sınıflardan biri sınıfından türetilir. `GetAt`nesnesine bir işaretçi döndürür `CPerson` . Türü belirtilmiş işaretçi koleksiyon sınıfları için — diziler veya listeler — ilk parametre temel sınıfı belirtir; ikinci parametre, depolanacak türü belirtir.

   `CTypedPtrArray`Sınıf Ayrıca bir dizinin öğelerine erişmek için normal dizi alt simge sözdizimini kullanabilmeniz için **[]** işlecini aşırı yükler. Yukarıdaki döngünün gövdesinde yer aldığı ifadeye alternatif olarak **`for`**

   [!code-cpp[NVC_MFCCollections#13](codesnippet/cpp/accessing-all-members-of-a-collection_2.cpp)]

   Bu işleç hem hem de **`const`** sürümler içinde bulunur **`const`** . **`const`** Diziler için çağrılan sürüm, **`const`** yalnızca atama ifadesinin sağ tarafında görünebilir.

### <a name="to-iterate-a-list"></a><a name="_core_to_iterate_a_list"></a>Bir listeyi yinelemek için

1. Üye işlevlerini kullanın `GetHeadPosition` ve `GetNext` listede bir şekilde çalışmak için:

   [!code-cpp[NVC_MFCCollections#14](codesnippet/cpp/accessing-all-members-of-a-collection_3.cpp)]

   Bu örnek, nesne işaretçileri içermesi için türü belirlenmiş bir işaretçi listesini kullanır `CPerson` . Liste bildirimi, bir diziyi yinelemek, ancak sınıfından türetilmeyi [sağlamak için](#_core_to_iterate_an_array) prosedürünün bir diziye benzer `CObList` . `GetNext`nesnesine bir işaretçi döndürür `CPerson` .

### <a name="to-iterate-a-map"></a><a name="_core_to_iterate_a_map"></a>Bir Haritayı yinelemek için

1. `GetStartPosition`Haritanın başlangıcına ulaşmak ve `GetNextAssoc` Aşağıdaki örnekte gösterildiği gibi haritadan bir sonraki anahtarı ve değeri tekrar tekrar almak için kullanın:

   [!code-cpp[NVC_MFCCollections#15](codesnippet/cpp/accessing-all-members-of-a-collection_4.cpp)]

   Bu örnek `CString` , anahtarları kullanan ve nesnelere işaretçiler depolayan bir basit harita şablonu (türü belirlenmiş bir işaretçi koleksiyonu yerine) kullanır `CPerson` . Gibi erişim işlevleri kullandığınızda `GetNextAssoc` , sınıfı nesnelere işaretçiler sağlar `CPerson` . Bunun yerine şablon olmayan eşleme koleksiyonlarından birini kullanırsanız, döndürülen `CObject` işaretçiyi bir işaretçisine dönüştürmeniz gerekir `CPerson` .

    > [!NOTE]
    >  Şablon olmayan haritalar için, derleyici son parametresindeki işaretçisine bir başvuru gerektirir `CObject` `GetNextAssoc` . Girişte, bir sonraki örnekte gösterildiği gibi işaretçilerinizi bu türe dönüştürmeniz gerekir.

   Şablon çözümü daha basittir ve daha iyi tür güvenliği sağlamaya yardımcı olur. Şablon olmayan kod, burada görebileceğiniz gibi daha karmaşıktır:

   [!code-cpp[NVC_MFCCollections#16](codesnippet/cpp/accessing-all-members-of-a-collection_5.cpp)]

Daha fazla bilgi için, bkz. [CObject koleksiyonundaki tüm nesneleri silme](deleting-all-objects-in-a-cobject-collection.md).

## <a name="see-also"></a>Ayrıca bkz.

[Koleksiyonlar](collections.md)
