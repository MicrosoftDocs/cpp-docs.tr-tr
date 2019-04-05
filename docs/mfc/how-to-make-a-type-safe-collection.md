---
title: 'Nasıl yapılır: Tür kullanımı uyumlu koleksiyon yapma'
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
ms.openlocfilehash: c8be781bad699edb8cb0be844d79802269c3e0c5
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58781529"
---
# <a name="how-to-make-a-type-safe-collection"></a>Nasıl yapılır: Tür kullanımı uyumlu koleksiyon yapma

Bu makalede, kendi veri türleri için tür kullanımı uyumlu koleksiyon yapma açıklanmaktadır. Konular şunlardır:

- [Şablona dayalı sınıflar için tür güvenliği kullanma](#_core_using_template.2d.based_classes_for_type_safety)

- [Uygulama yardımcı işlevleri](#_core_implementing_helper_functions)

- [Şablon Olmayandan koleksiyon sınıflarını kullanma](#_core_using_nontemplate_collection_classes)

Microsoft Foundation Class Kitaplığı, C++ şablonları temel alan önceden tanımlanmış tür kullanımı uyumlu koleksiyonlar sağlar. Şablonları oldukları için bu sınıflar, tür güvenliği ve tür atama ve bu amaç için bir şablon Olmayandan sınıfı kullanan diğer ek iş olmadan kullanım kolaylığı sağlamaya yardımcı olur. MFC örnek [TOPLAMAK](../overview/visual-cpp-samples.md) şablona dayalı koleksiyon sınıfları bir MFC uygulamasında kullanımını gösterir. Genel olarak, bu sınıflar, yeni Koleksiyonlar kod yazmak istediğiniz zaman kullanın.

##  <a name="_core_using_template.2d.based_classes_for_type_safety"></a> Şablona dayalı sınıflar için tür güvenliği kullanma

#### <a name="to-use-template-based-classes"></a>Şablona dayalı sınıflar kullanmak için

1. Koleksiyon sınıfı türünün bir değişkeni bildirir. Örneğin:

   [!code-cpp[NVC_MFCCollections#7](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_1.cpp)]

1. Üye işlevlerini koleksiyon nesnesinin çağırın. Örneğin:

   [!code-cpp[NVC_MFCCollections#8](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_2.cpp)]

1. Gerekirse, uygulama [yardımcı işlevleri](../mfc/reference/collection-class-helpers.md) ve [SerializeElements](../mfc/reference/collection-class-helpers.md#serializeelements). Bu işlevler uygulama hakkında daha fazla bilgi için bkz: [uygulama yardımcı işlevleri](#_core_implementing_helper_functions).

Bu örnek, tamsayı listesi bildirimi gösterir. 1. adımda ilk parametre listesi öğeleri olarak depolanan veri türüdür. İkinci parametre nasıl veri geçen ve koleksiyon sınıfın üye işlevleri gibi döndürülen belirtir `Add` ve `GetAt`.

##  <a name="_core_implementing_helper_functions"></a> Uygulama yardımcı işlevleri

Şablona dayalı koleksiyon sınıfları `CArray`, `CList`, ve `CMap` türetilmiş koleksiyon sınıfınız için gerektiği gibi özelleştirebileceğiniz beş genel yardımcı işlevleri kullanın. Bu yardımcı işlevleri hakkında daha fazla bilgi için bkz: [koleksiyon sınıfı Yardımcıları](../mfc/reference/collection-class-helpers.md) içinde *MFC başvurusu*. Serileştirme fonksiyonunun uygulanması, şablona dayalı koleksiyon sınıfları birçok kullanım için gereklidir.

###  <a name="_core_serializing_elements"></a> Öğeleri seri hale getirme

`CArray`, `CList`, Ve `CMap` sınıfların çağrısı `SerializeElements` depolamak için koleksiyon öğelerine veya bunların bir arşivden okumak için.

Varsayılan uygulaması `SerializeElements` yardımcı işlevini nesnelerden bir bit düzeyinde yazma arşive yapar veya bit düzeyinde mi nesneleri içinde depolanan bağlı olarak bu nesnelere arşivden okuma veya arşivden alınır. Geçersiz kılma `SerializeElements` bu eylemi uygun değilse.

Koleksiyonunuz öğesinden türetilen nesneler depoluyorsa `CObject` ve kullandığınız `IMPLEMENT_SERIAL` makro koleksiyon öğesi sınıfın uygulaması içinde yerleşik olarak seri hale getirme işlevselliğini avantajlarından faydalanabilirsiniz `CArchive` ve `CObject`:

[!code-cpp[NVC_MFCCollections#9](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_3.cpp)]

Aşırı yüklenmiş ekleme işleçleri `CArchive` çağrı `CObject::Serialize` (veya bu işlevi geçersiz kılma) her `CPerson` nesne.

##  <a name="_core_using_nontemplate_collection_classes"></a> Şablon Olmayandan koleksiyon sınıflarını kullanma

MFC, MFC sürüm 1.0 ile tanıtılan koleksiyon sınıfları da destekler. Bu sınıf şablonlarına dayalı değil. Desteklenen türler'ın verileri içeren için kullanılabilir `CObject*`, `UINT`, `DWORD`, ve `CString`. Bu önceden tanımlanmış koleksiyonları kullanabilirsiniz (gibi `CObList`) öğesinden türetilen herhangi bir nesne koleksiyonları tutacak `CObject`. MFC gibi ilkel türler tutmak için önceden tanımlanmış diğer derlemeler de sağlar `UINT` ve void işaretçileri (`void`*). Genel olarak, ancak genellikle daha belirli bir sınıf ve türevleri nesnelerin tutmak için kendi tür kullanımı uyumlu koleksiyonlar tanımlamak yararlıdır. Koleksiyon sınıfları ile bunu şablonlar temelinde şablona dayalı sınıflar kullanmaktan daha fazla iş olduğunu unutmayın.

Şablon Olmayandan koleksiyonlarla tür kullanımı uyumlu koleksiyonlar oluşturmanın iki yolu vardır:

1. Şablon Olmayandan koleksiyonlar gerekirse tür atama ile kullanın. Bu daha kolay bir yaklaşımdır.

1. Öğesinden türetilen ve şablon Olmayandan tür kullanımı uyumlu koleksiyon genişletebilirsiniz.

#### <a name="to-use-the-nontemplate-collections-with-type-casting"></a>Şablon Olmayandan koleksiyonları tür atama ile kullanmak için

1. Şablon Olmayandan sınıflardan biri gibi kullanın `CWordArray`, doğrudan.

   Örneğin, oluşturabileceğiniz bir `CWordArray` ve 32-bit değerleri ekleyin ve ardından saklayabilirsiniz. Daha fazla yapmak için bir şey yoktur. Yalnızca önceden tanımlanmış işlevlerini kullanırsınız.

   Önceden tanımlanmış bir koleksiyonu gibi kullanabilir `CObList`, türetilen herhangi bir nesne tutacak `CObject`. A `CObList` koleksiyon işaretçileri tutmak için tanımlanmış `CObject`. Listeden bir nesne aldığınızda, bu yana doğru türe sonucu cast gerekebilir `CObList` işlevler için işaretçiler döndürür `CObject`. Örneğin, depoladığınız `CPerson` nesneler bir `CObList` koleksiyonuna sahip bir işaretçi olarak alınan bir öğeyi dönüştürülecek bir `CPerson` nesne. Aşağıdaki örnekte bir `CObList` tutmak için koleksiyon `CPerson` nesneler:

   [!code-cpp[NVC_MFCCollections#10](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_4.cpp)]

   Bu teknik, önceden tanımlı bir koleksiyon türü kullanarak ve gerekirse atama birçok koleksiyon gereksinimleriniz için yeterli olabilir. Daha fazla işlevsellik veya daha fazla tür güvenliği gerekirse, şablona dayalı bir sınıf kullanma veya bir sonraki yordamı izleyin.

#### <a name="to-derive-and-extend-a-nontemplate-type-safe-collection"></a>Türetilir ve bir şablon Olmayandan tür kullanımı uyumlu koleksiyon genişletmek için

1. Kendi koleksiyon sınıfı önceden tanımlanmış bir şablon Olmayandan sınıflarının birinden türetilir.

   Sınıfınıza türetilen bir tür kullanımı uyumlu arabirimi var olan işlevleri sağlamak için tür açısından güvenli bir sarmalayıcı işlevleri ekleyebilirsiniz.

   Örneğin, bir listeden türetilmiş `CObList` tutacak `CPerson` sarmalayıcı işlevleri eklemek nesneleri `AddHeadPerson` ve `GetHeadPerson`, aşağıda gösterildiği gibi.

   [!code-cpp[NVC_MFCCollections#11](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_5.h)]

   Bu sarmalayıcı işlevleri ekleme ve alma için tür-güvenli bir yol sağlayan `CPerson` nesnelerden türetilen listesi. İçin gördüğünüz `GetHeadPerson` işlevi, yalnızca tür atama şifrelenmiş.

   Yalnızca tür kullanımı uyumlu sarmalayıcılar var olan işlevselliği sarmalama yerine koleksiyon özelliklerini genişleten yeni işlevlerini tanımlama, yeni işlevsellik de ekleyebilirsiniz. Örneğin, makaleyi [CObject koleksiyonundaki tüm nesneleri silme](../mfc/deleting-all-objects-in-a-cobject-collection.md) bir listede yer alan nesneleri silmek için bir işlev açıklar. Bu işlev için türetilmiş sınıf üyesi işlevi olarak eklenemedi.

## <a name="see-also"></a>Ayrıca bkz.

[Koleksiyonlar](../mfc/collections.md)
