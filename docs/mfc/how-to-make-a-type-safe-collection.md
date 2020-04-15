---
title: 'Nasıl yapılır: Tür Kullanımı Uyumlu Koleksiyon Yapma'
ms.date: 11/04/2016
helpviewer_keywords:
- type-safe collections [MFC]
- serializing collection-class elements [MFC]
- collection classes [MFC], type safety
- SerializeElements function [MFC]
- collection classes [MFC], template-based
- serialization [MFC], collection classes
- collection classes [MFC], deriving from nontemplate
ms.assetid: 7230b2db-4283-4083-b098-eb231bf5b89e
ms.openlocfilehash: 1901100996a776244b57efe0951795ceec3c630a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377254"
---
# <a name="how-to-make-a-type-safe-collection"></a>Nasıl yapılır: Tür Kullanımı Uyumlu Koleksiyon Yapma

Bu makalede, kendi veri türleri için tür güvenli koleksiyonları yapmak nasıl açıklanmaktadır. Konu başlıkları şunlardır:

- [Tür güvenliği için şablon tabanlı sınıfları kullanma](#_core_using_template.2d.based_classes_for_type_safety)

- [Yardımcı işlevlerin uygulanması](#_core_implementing_helper_functions)

- [Şablon dışı toplama sınıflarını kullanma](#_core_using_nontemplate_collection_classes)

Microsoft Hazırlık Sınıfı Kitaplığı, C++ şablonlarını temel alan önceden tanımlanmış tür güvenli koleksiyonlar sağlar. Şablon olduklarından, bu sınıflar tür dökümü ve bu amaç için şablon olmayan bir sınıf kullanmayla ilgili diğer ekstra işler olmadan tür güvenliği ve kullanım kolaylığı sağlamaya yardımcı olur. MFC örnek [COLLECT,](../overview/visual-cpp-samples.md) bir MFC uygulamasında şablon tabanlı toplama sınıflarının kullanımını gösterir. Genel olarak, yeni koleksiyonkodu yazdığınızda bu sınıfları kullanın.

## <a name="using-template-based-classes-for-type-safety"></a><a name="_core_using_template.2d.based_classes_for_type_safety"></a>Tür Güvenliği için Şablon Tabanlı Sınıfları Kullanma

#### <a name="to-use-template-based-classes"></a>Şablon tabanlı sınıfları kullanmak için

1. Koleksiyon sınıfı türünden bir değişken bildirin. Örneğin:

   [!code-cpp[NVC_MFCCollections#7](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_1.cpp)]

1. Koleksiyon nesnesinin üye işlevlerini çağırın. Örneğin:

   [!code-cpp[NVC_MFCCollections#8](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_2.cpp)]

1. Gerekirse, yardımcı [işlevleri](../mfc/reference/collection-class-helpers.md) uygulayın ve [Öğeleri Serialize.](../mfc/reference/collection-class-helpers.md#serializeelements) Bu işlevleriuygulama hakkında bilgi için [bkz.](#_core_implementing_helper_functions)

Bu örnek, tamsayılar listesinin bildirimini gösterir. Adım 1'deki ilk parametre, listenin öğeleri olarak depolanan veri türüdür. İkinci parametre, verilerin koleksiyon sınıfının üye işlevlerine nasıl aktarılsüreceğini `Add` ve `GetAt`döndürüleceğini belirtir.

## <a name="implementing-helper-functions"></a><a name="_core_implementing_helper_functions"></a>Yardımcı Işlevlerin Uygulanması

Şablon tabanlı koleksiyon `CArray`sınıfları `CList` `CMap` ve türemiş koleksiyon sınıfınız için gerektiği gibi özelleştirebileceğiniz beş genel yardımcı işlevi kullanın. Bu yardımcı işlevler hakkında bilgi *için, MFC Başvurusu'ndaki* [Toplama Sınıfı Yardımcıları'na](../mfc/reference/collection-class-helpers.md) bakın. Şablon tabanlı koleksiyon sınıflarının çoğu kullanımı için serileştirme işlevinin uygulanması gereklidir.

### <a name="serializing-elements"></a><a name="_core_serializing_elements"></a>Elementleri Serileştirme

, `CArray` `CList`ve `CMap` sınıflar `SerializeElements` koleksiyon öğelerini bir arşivden depolamayı veya bunları okumayı çağırır.

Yardımcı işlevin `SerializeElements` varsayılan uygulaması, nesnelerden arşive doğru biraz yazı mı yazabilir, yoksa nesnelerin arşivde depolanıp depolanmadığına veya arşivden alınıp alınmadığına bağlı olarak arşivden nesnelere biraz okunur. Bu `SerializeElements` eylem uygun değilse geçersiz kılın.

Koleksiyonunuz türetilen nesneleri `CObject` depolarsa `IMPLEMENT_SERIAL` ve toplama öğesi sınıfının uygulanmasında makroyu kullanıyorsanız, yerleşik `CArchive` serileştirme işlevinden yararlanabilirsiniz ve: `CObject`

[!code-cpp[NVC_MFCCollections#9](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_3.cpp)]

Her `CArchive` `CPerson` nesne için çağrı `CObject::Serialize` (veya bu işlevin geçersiz kılınan) için aşırı yüklü ekleme işleçleri.

## <a name="using-nontemplate-collection-classes"></a><a name="_core_using_nontemplate_collection_classes"></a>Şablon Olmayan Toplama Sınıflarını Kullanma

MFC ayrıca MFC sürüm 1.0 ile tanıtılan toplama sınıflarını da destekler. Bu sınıflar şablonları temel almıyor. Desteklenen türlerin `CObject*`verilerini içermek için kullanılabilirler, `DWORD`, `CString` `UINT`, ve. Bu önceden tanımlanmış koleksiyonları (örneğin) `CObList`türetilen `CObject`nesnelerin koleksiyonlarını tutmak için kullanabilirsiniz. MFC ayrıca, işaretçiler ve boşluk işaretçileri (*) gibi `UINT` ilkel türleri tutmak için diğer önceden tanımlanmış koleksiyonlar da sağlar.`void` Ancak genel olarak, daha belirli bir sınıfın ve türevlerinin nesnelerini tutmak için kendi tür güvenli koleksiyonlarınızı tanımlamak genellikle yararlıdır. Şablonlara dayanmayan koleksiyon sınıflarıyla bunu yapmanın şablon tabanlı sınıfları kullanmaktan daha fazla iş olduğunu unutmayın.

Şablon olmayan koleksiyonlarla tür güvenli koleksiyonlar oluşturmanın iki yolu vardır:

1. Gerekirse tip döküm ile, şablon olmayan koleksiyonları kullanın. Bu daha kolay bir yaklaşımdır.

1. Şablon olmayan bir tür güvenli koleksiyonundan türetin ve genişletin.

#### <a name="to-use-the-nontemplate-collections-with-type-casting"></a>Tür döküm ile şablon olmayan koleksiyonları kullanmak için

1. Doğrudan , şablonsuz `CWordArray`sınıflardan birini kullanın.

   Örneğin, bir oluşturabilir `CWordArray` ve herhangi bir 32-bit değerleri ekleyebilirsiniz, sonra bunları almak. Yapacak başka bir şey yok. Sadece önceden tanımlanmış işlevselliği kullanın.

   Türetilen nesneleri tutmak için `CObList`önceden tanımlanmış bir koleksiyon da `CObject`kullanabilirsiniz. İşaretçileri `CObList` `CObject`' niçin tutmak için bir koleksiyon tanımlanır Bir nesneyi listeden aldığınızda, `CObList` işlevler işaretçileri `CObject`'ye döndürdüğünde niçin sonucu uygun türe dökmeniz gerekebilir Örneğin, nesneleri bir `CPerson` `CObList` koleksiyonda depolarsanız, bir `CPerson` nesneye işaretçi olmak için alınan bir öğeyi dökmeniz gerekir. Aşağıdaki örneknesneleri `CObList` tutmak `CPerson` için bir koleksiyon kullanır:

   [!code-cpp[NVC_MFCCollections#10](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_4.cpp)]

   Önceden tanımlanmış bir toplama türü ve gerektiğinde döküm kullanma bu teknik toplama ihtiyaçlarının çoğu için yeterli olabilir. Daha fazla işlevselliğe veya daha fazla tür güvenliğine ihtiyacınız varsa, şablon tabanlı bir sınıf kullanın veya bir sonraki yordamı izleyin.

#### <a name="to-derive-and-extend-a-nontemplate-type-safe-collection"></a>Şablon olmayan bir tür güvenli koleksiyonu türetmek ve genişletmek için

1. Kendi koleksiyon sınıfınızı önceden tanımlanmış olmayan şablon sınıflarından birinden türetin.

   Sınıfınızı türeterken, varolan işlevlere tür güvenli bir arabirim sağlamak için tür güvenli sarıcı işlevleri ekleyebilirsiniz.

   `CObList` Örneğin, nesneleri tutmak `CPerson` için bir liste türetilmişse, sarıcı işlevlerini `AddHeadPerson` ve `GetHeadPerson`aşağıda gösterildiği gibi ekleyebilirsiniz.

   [!code-cpp[NVC_MFCCollections#11](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_5.h)]

   Bu sarıcı işlevleri, türetilen listeden `CPerson` nesne eklemek ve almak için tür güvenli bir yol sağlar. Bu `GetHeadPerson` işlev için, sadece tür döküm kapsülleme olduğunu görebilirsiniz.

   Ayrıca, varolan işlevleri tür güvenli sarmalayıcılara sarmak yerine koleksiyonun özelliklerini genişleten yeni işlevler tanımlayarak yeni işlevler ekleyebilirsiniz. Örneğin, [CObject Koleksiyonundaki Tüm Nesneleri Silme](../mfc/deleting-all-objects-in-a-cobject-collection.md) makalesi, bir listede bulunan tüm nesneleri silmek için bir işlev açıklar. Bu işlev, türemiş sınıfa üye işlev olarak eklenebilir.

## <a name="see-also"></a>Ayrıca bkz.

[Koleksiyonlar](../mfc/collections.md)
