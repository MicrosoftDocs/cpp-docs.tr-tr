---
title: Bir koleksiyonun tüm üyelerine erişme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 320457928ef8bc1a03d86b3a898bc0b719e116a2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442883"
---
# <a name="accessing-all-members-of-a-collection"></a>Bir Koleksiyonun Tüm Üyelerine Erişme

MFC dizi koleksiyon sınıfları — şablon tabanlı değil; öğeleri erişmek için dizinler kullanın. MFC liste ve eşleme koleksiyon sınıfları — şablon tabanlı ve — türünün bir göstergesi kullanın **konumu** koleksiyonundaki belirli bir pozisyon tanımlamak için. Bir veya daha fazla bu koleksiyonların üyelerinin erişmek için ilk konum göstergesi başlatmak ve daha sonra tekrar tekrar o konumdan koleksiyona geçirin ve sonraki öğeyi döndürmek için isteyin. Toplama ilerleme durumu ile ilgili durum bilgilerini yinelemenin bakımından sorumlu değildir. Bu bilgileri, Konum göstergesi tutulur. Ancak, belirli bir konuma göz önünde bulundurulduğunda, koleksiyon sonraki öğeye döndürmekten sorumludur.

Aşağıdaki yordamlar, başlıca üç türdeki MFC ile sağlanan koleksiyon üzerinden yineleme yapma gösterilmektedir:

- [Bir dizi yineleme](#_core_to_iterate_an_array)

- [Bir liste yineleme](#_core_to_iterate_a_list)

- [Bir harita yineleme](#_core_to_iterate_a_map)

### <a name="_core_to_iterate_an_array"></a> Bir dizi yineleme yapmak için

1. İle sıralı dizin numaralarını kullanın `GetAt` üye işlevi:

     [!code-cpp[NVC_MFCCollections#12](../mfc/codesnippet/cpp/accessing-all-members-of-a-collection_1.cpp)]

     Bu örnek, işaretçileri içeren bir işaretçi türü belirlenmiş dizi kullanır `CPerson` nesneleri. Dizi sınıfından türetilir `CObArray`, önceden tanımlanmış bir şablon Olmayandan sınıfları. `GetAt` bir işaretçi döndüren bir `CPerson` nesne. İşaretçi türü belirlenmiş koleksiyon sınıfları için — diziler veya listeleri — temel sınıf; ilk parametre belirtir İkinci parametre depolamak için türünü belirtir.

     `CTypedPtrArray` Sınıfı da aşırı **[]** işleci dizi öğelerine erişim için her zamanki dizi indisi sözdizimi kullanabilmesi için. Deyim gövdesine alternatif **için** yukarıdaki döngü

     [!code-cpp[NVC_MFCCollections#13](../mfc/codesnippet/cpp/accessing-all-members-of-a-collection_2.cpp)]

     Bu işleç ikisi de mevcut **const** ve olmayan-**const** sürümleri. **Const** için çağrılan sürüm **const** diziler, yalnızca sağ tarafta Atama ifadesinin görünebilir.

### <a name="_core_to_iterate_a_list"></a> Bir liste yinelemek için

1. Üye işlevlerini `GetHeadPosition` ve `GetNext` listesinde istediğiniz şekilde çalışmak için:

     [!code-cpp[NVC_MFCCollections#14](../mfc/codesnippet/cpp/accessing-all-members-of-a-collection_3.cpp)]

     Bu örnek, işaretçileri içeren için türü belirtilmiş işaretçi listesini kullanır. `CPerson` nesneleri. Bir dizi yordamın listesi bildirimini benzer [bir dizi yineleme yapmak için](#_core_to_iterate_an_array) sınıfından türetilen ancak `CObList`. `GetNext` bir işaretçi döndüren bir `CPerson` nesne.

### <a name="_core_to_iterate_a_map"></a> Bir harita yinelemek için

1. Kullanım `GetStartPosition` eşleme başına almak ve `GetNextAssoc` art arda sonraki anahtar ve değer haritasında, aşağıdaki örnekte gösterildiği gibi almak için:

     [!code-cpp[NVC_MFCCollections#15](../mfc/codesnippet/cpp/accessing-all-members-of-a-collection_4.cpp)]

     Bu örnekte basit harita şablonu (yazılan işaretçi koleksiyonu yerine) kullanan `CString` anahtarları ve işaretçileri depolar `CPerson` nesneleri. Erişim işlevleri gibi kullandığınızda `GetNextAssoc`, sınıf işaretçileri sağlar `CPerson` nesneleri. Şablon Olmayandan harita koleksiyonlardan biri bunun yerine kullanırsanız döndürülen dönüştürmelisiniz `CObject` işaretçisinin işaretçisi için bir `CPerson`.

    > [!NOTE]
    >  Şablon Olmayandan eşlemeleri için derleyici başvurusu gerektirir. bir `CObject` son parametresi içinde işaretçi `GetNextAssoc`. Giriş, sonraki örnekte gösterildiği gibi işaretçiler o türe dönüştürmeniz gerekir.

     Şablon çözüm basittir ve daha iyi tür güvenliği sağlamaya yardımcı olur. Burada gördüğünüz gibi şablon Olmayandan kod daha karmaşık bir işlemdir:

     [!code-cpp[NVC_MFCCollections#16](../mfc/codesnippet/cpp/accessing-all-members-of-a-collection_5.cpp)]

Daha fazla bilgi için [CObject koleksiyonundaki tüm nesneleri silme](../mfc/deleting-all-objects-in-a-cobject-collection.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Koleksiyonlar](../mfc/collections.md)

