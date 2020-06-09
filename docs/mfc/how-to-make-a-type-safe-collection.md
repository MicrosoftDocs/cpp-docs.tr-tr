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
ms.openlocfilehash: 6ee4603f03ef8a95c218b0fe040e9606aab99ebb
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620019"
---
# <a name="how-to-make-a-type-safe-collection"></a>Nasıl yapılır: Tür Kullanımı Uyumlu Koleksiyon Yapma

Bu makalede, kendi veri türlerinizin tür kullanımı açısından güvenli koleksiyonların nasıl yapılacağı açıklanır. Konu başlıkları şunlardır:

- [Tür güvenliği için şablon tabanlı sınıfları kullanma](#_core_using_template.2d.based_classes_for_type_safety)

- [Yardımcı işlevleri uygulama](#_core_implementing_helper_functions)

- [Şablon olmayan koleksiyon sınıfları kullanma](#_core_using_nontemplate_collection_classes)

Microsoft Foundation Class Kitaplığı, C++ şablonlarına göre önceden tanımlanmış tür kullanımı uyumlu koleksiyonlar sağlar. Şablonlar olduklarından, bu sınıflar tür ve bu amaçla şablon olmayan bir sınıf kullanmak dahil olmak üzere tür ve diğer ek işler olmadan tür güvenliği ve kullanım kolaylığı sağlanmasına yardımcı olur. MFC örnek [toplaması](../overview/visual-cpp-samples.md) , bir MFC uygulamasında şablon tabanlı koleksiyon sınıflarının kullanımını gösterir. Genel olarak, bu sınıfları yeni koleksiyon kodu yazdığınızda istediğiniz zaman kullanın.

## <a name="using-template-based-classes-for-type-safety"></a><a name="_core_using_template.2d.based_classes_for_type_safety"></a>Tür güvenliği için şablon tabanlı sınıfları kullanma

#### <a name="to-use-template-based-classes"></a>Şablon tabanlı sınıfları kullanmak için

1. Koleksiyon sınıfı türünde bir değişken bildirin. Örnek:

   [!code-cpp[NVC_MFCCollections#7](codesnippet/cpp/how-to-make-a-type-safe-collection_1.cpp)]

1. Koleksiyon nesnesinin üye işlevlerini çağırın. Örnek:

   [!code-cpp[NVC_MFCCollections#8](codesnippet/cpp/how-to-make-a-type-safe-collection_2.cpp)]

1. Gerekirse, [yardımcı işlevleri](reference/collection-class-helpers.md) ve [SerializeElements](reference/collection-class-helpers.md#serializeelements)' i uygulayın. Bu işlevleri uygulama hakkında daha fazla bilgi için bkz. [yardımcı Işlevleri uygulama](#_core_implementing_helper_functions).

Bu örnek, tamsayılar listesinin bildirimini gösterir. Adım 1 ' deki ilk parametre, listenin öğeleri olarak depolanan veri türüdür. İkinci parametre, ve gibi koleksiyon sınıfının üye işlevlerine nasıl geçirileceğini ve döndürüleceğini belirtir `Add` `GetAt` .

## <a name="implementing-helper-functions"></a><a name="_core_implementing_helper_functions"></a>Yardımcı Işlevleri uygulama

Şablon tabanlı koleksiyon sınıfları, `CArray` `CList` ve `CMap` türetilmiş koleksiyon sınıfınız için gerektiği şekilde özelleştirebileceğiniz beş genel yardımcı işlevi kullanır. Bu yardımcı işlevler hakkında daha fazla bilgi için bkz. *MFC başvurusunda* [koleksiyon sınıfı Yardımcıları](reference/collection-class-helpers.md) . Serileştirme işlevinin uygulanması, şablon tabanlı koleksiyon sınıflarının birçok kullanımı için gereklidir.

### <a name="serializing-elements"></a><a name="_core_serializing_elements"></a>Öğeler seri hale getiriliyor

`CArray` `CList` `CMap` `SerializeElements` Koleksiyon öğelerini depolamak veya bir arşivden okumak için,, ve sınıfları çağrısı.

Yardımcı işlevinin varsayılan uygulanması, nesnelerden `SerializeElements` Arşiv 'e veya arşivden alınan ya da alınan nesnelerin bir bit düzeyinde okunmasıdır. Bu, nesnelerin arşivden depolanıp depolanmadığını ya da Arşivden alınıp alınamayacağını bağlı olarak, arşivden nesnelere bit düzeyinde yazma işlemi yapar. `SerializeElements`Bu eylem uygun değilse geçersiz kılın.

Koleksiyonunuz öğesinden türetilmiş nesneleri depolularsa `CObject` ve bu `IMPLEMENT_SERIAL` makroyu koleksiyon öğesi sınıfının uygulamasında kullanıyorsanız, ve içinde yerleşik olarak bulunan serileştirme işlevlerinden faydalanabilirsiniz `CArchive` `CObject` :

[!code-cpp[NVC_MFCCollections#9](codesnippet/cpp/how-to-make-a-type-safe-collection_3.cpp)]

`CArchive` `CObject::Serialize` Her nesne için çağrı (veya bu işlevin geçersiz kılma) için aşırı yüklenmiş ekleme işleçleri `CPerson` .

## <a name="using-nontemplate-collection-classes"></a><a name="_core_using_nontemplate_collection_classes"></a>Şablon olmayan koleksiyon sınıfları kullanma

MFC Ayrıca MFC sürüm 1,0 ile tanıtılan koleksiyon sınıflarını da destekler. Bu sınıflar şablonları temel alır. Desteklenen türlerin,, ve türlerinin verilerini içermesi için kullanılabilirler `CObject*` `UINT` `DWORD` `CString` . Bu önceden tanımlı koleksiyonları (gibi `CObList` ), öğesinden türetilmiş nesnelerin koleksiyonlarını tutmak için kullanabilirsiniz `CObject` . MFC Ayrıca `UINT` , ve void işaretçiler (*) gibi temel türleri tutmak için önceden tanımlanmış diğer koleksiyonlar da sağlar `void` . Ancak genel olarak, daha belirli bir sınıfın ve türetme 'nin nesnelerini tutmak için kendi tür açısından güvenli koleksiyonlarınızı tanımlamak genellikle yararlıdır. Bu şekilde, şablonları temel alan koleksiyon sınıfları şablon tabanlı sınıfları kullanmaktan daha fazla çalışmadır.

Şablon olmayan koleksiyonlara sahip tür kullanımı uyumlu koleksiyonlar oluşturmanın iki yolu vardır:

1. Gerekirse tür atama ile şablon olmayan koleksiyonları kullanın. Bu, daha kolay bir yaklaşımdır.

1. Şablon olmayan tür açısından güvenli bir koleksiyondan türet ve genişlet.

#### <a name="to-use-the-nontemplate-collections-with-type-casting"></a>Şablon olmayan koleksiyonları tür atama ile kullanmak için

1. Şablon olmayan sınıflardan birini (örneğin, doğrudan) kullanın `CWordArray` .

   Örneğin, bir oluşturup `CWordArray` ona 32 bitlik değerler ekleyebilir ve bunları alabilirsiniz. Yapılacak daha fazla şey yok. Önceden tanımlanmış işlevselliği kullanmanız yeterlidir.

   `CObList`' Den türetilmiş nesneleri tutmak için gibi, önceden tanımlanmış bir koleksiyon da kullanabilirsiniz `CObject` . Bir `CObList` koleksiyon, işaretçileri tutmak için tanımlanır `CObject` . Listeden bir nesne aldığınızda, işlevler işaretçiler döndürdüğü için sonucu doğru türe atamalısınız `CObList` `CObject` . Örneğin, `CPerson` nesneleri bir `CObList` koleksiyonda depolarsanız, alınan bir öğeyi bir nesne işaretçisi olacak şekilde atamalısınız `CPerson` . Aşağıdaki örnek, `CObList` nesneleri tutmak için bir koleksiyon kullanır `CPerson` :

   [!code-cpp[NVC_MFCCollections#10](codesnippet/cpp/how-to-make-a-type-safe-collection_4.cpp)]

   Önceden tanımlanmış bir koleksiyon türü ve atama kullanılması gereken bu teknik, koleksiyon gereksinimlerinizin birçoğu için yeterli olabilir. Daha fazla işlevselliğe veya daha fazla güvenlik türüne ihtiyacınız varsa, şablon tabanlı bir sınıf kullanın veya sonraki yordamı izleyin.

#### <a name="to-derive-and-extend-a-nontemplate-type-safe-collection"></a>Şablon olmayan tür açısından güvenli bir koleksiyonu türetmek ve genişletmek için

1. Önceden tanımlanmış şablon sınıflarından birindeki kendi koleksiyon sınıfınızı türetebilirsiniz.

   Sınıfınızı türettiğinizde, var olan işlevlere tür açısından güvenli bir arabirim sağlamak için tür açısından güvenli sarmalayıcı işlevler ekleyebilirsiniz.

   Örneğin, öğesinden nesneleri tutacak bir liste türemiş olmanız `CObList` `CPerson` halinde sarmalayıcı işlevlerini `AddHeadPerson` ve `GetHeadPerson` aşağıda gösterildiği gibi ekleyebilirsiniz.

   [!code-cpp[NVC_MFCCollections#11](codesnippet/cpp/how-to-make-a-type-safe-collection_5.h)]

   Bu sarmalayıcı işlevleri türetilmiş listeye nesne eklemek ve almak için tür açısından güvenli bir yol sağlar `CPerson` . `GetHeadPerson`İşlev için yalnızca tür ataması kapsüllenmeniz gerektiğini görebilirsiniz.

   Ayrıca, tür kullanımı uyumlu sarmalayıcılara yalnızca var olan işlevselliği sarmalama yerine koleksiyonun yeteneklerini genişleten yeni işlevler tanımlayarak yeni işlevler ekleyebilirsiniz. Örneğin, [CObject koleksiyonundaki tüm nesneleri silme](deleting-all-objects-in-a-cobject-collection.md) makalesi bir listede bulunan tüm nesneleri silmek için bir işlevi tanımlar. Bu işlev, bir üye işlevi olarak türetilmiş sınıfa eklenebilir.

## <a name="see-also"></a>Ayrıca bkz.

[Koleksiyonlar](collections.md)
