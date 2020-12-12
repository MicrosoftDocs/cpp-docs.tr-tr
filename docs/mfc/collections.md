---
description: 'Daha fazla bilgi edinin: Koleksiyonlar'
title: Koleksiyonlar
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, collections
- arrays [MFC], classes
- MFC collection classes
- shapes, collection
- collection classes [MFC], MFC
- collections, about collections
- array templates [MFC]
- collection classes [MFC], template-based
- collection classes [MFC], about collection classes
- collection classes [MFC], maps
- collection classes [MFC], arrays
- shapes
- collection classes [MFC], lists
- collection classes [MFC], shapes
ms.assetid: 02586e4c-851d-41d0-a722-feb11c17c74c
ms.openlocfilehash: 63bc61b73a9ba654fd22ecf3a238f8ef89734221
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283478"
---
# <a name="collections"></a>Koleksiyonlar

Microsoft Foundation Class Kitaplığı, nesne gruplarını yönetmek için koleksiyon sınıfları sağlar. Bu sınıfların iki türü vardır:

- [C++ şablonlarından oluşturulan koleksiyon sınıfları](#_core_the_template_based_collection_classes)

- [Şablondan oluşturulmayan koleksiyon sınıfları](#_core_the_collection_classes_not_based_on_templates)

> [!NOTE]
> Kodunuz zaten şablon olmayan koleksiyon sınıfları kullanıyorsa, bunları kullanmaya devam edebilirsiniz. Kendi veri türlerinizin yeni tür açısından güvenli koleksiyon sınıfları yazarsanız, daha yeni şablon tabanlı sınıfları kullanmanızı öneririz.

## <a name="collection-shapes"></a><a name="_core_collection_shapes"></a> Koleksiyon şekilleri

Koleksiyon sınıfı, "Shape" ve kendi öğelerinin türlerine göre belirlenir. Şekil, nesnelerin koleksiyon tarafından düzenlenme ve depolanma biçimini ifade eder. MFC üç temel koleksiyon şekli sağlar: listeler, diziler ve haritalar (sözlük olarak da bilinir). Belirli programlama sorununuzun en uygun koleksiyon şeklini seçebilirsiniz.

Bu konunun ilerleyen kısımlarında, belirtilen üç koleksiyon şekli kısaca açıklanmaktadır. Programınız için en iyi olan kararı vermenize yardımcı olacak şekillerin özelliklerini karşılaştırmak için bkz. [bir koleksiyon sınıfı seçme önerileri](recommendations-for-choosing-a-collection-class.md).

- Liste

   Liste sınıfı, düzenli olarak bağlanmış bir liste olarak uygulanan sıralı ve dizine alınmamış öğelerin bir listesini sağlar. Listede bir "baş" ve "kuyruk" bulunur ve baş veya kuyruklu öğeleri ekleme veya kaldırma ya da ortadaki öğeleri ekleme veya silme işlemi çok hızlıdır.

- Dizi

   Array sınıfı, dinamik olarak boyutlandırılmış, sıralı ve tamsayı dizinli nesneler dizisi sağlar.

- Eşleme (sözlük olarak da bilinir)

   Eşleme, bir anahtar nesnesini bir değer nesnesiyle ilişkilendiren bir koleksiyondur.

## <a name="the-template-based-collection-classes"></a><a name="_core_the_template_based_collection_classes"></a> Template-Based koleksiyonu sınıfları

Herhangi bir türdeki nesneleri içeren tür açısından güvenli bir koleksiyon uygulamanın en kolay yolu, MFC şablon tabanlı sınıflardan birini kullanmaktır. Bu sınıfların örnekleri için bkz. MFC örnek [toplaması](../overview/visual-cpp-samples.md).

Aşağıdaki tabloda MFC şablon tabanlı koleksiyon sınıfları listelenmektedir.

### <a name="collection-template-classes"></a>Koleksiyon şablonu sınıfları

|Koleksiyon içerikleri|Diziler|Listeler|Haritalar|
|-------------------------|------------|-----------|----------|
|Herhangi bir türdeki nesne koleksiyonları|`CArray`|`CList`|`CMap`|
|Herhangi bir türdeki nesnelere yönelik işaretçilerin koleksiyonları|`CTypedPtrArray`|`CTypedPtrList`|`CTypedPtrMap`|

## <a name="the-collection-classes-not-based-on-templates"></a><a name="_core_the_collection_classes_not_based_on_templates"></a> Şablonları temel alan koleksiyon sınıfları

Uygulamanız zaten MFC sınıflarındaki olmayan sınıflar kullanıyorsa, bunları kullanmaya devam edebilirsiniz. Ancak, yeni koleksiyonlar için şablon tabanlı sınıfları kullanmanızı öneririz. Aşağıdaki tabloda, şablonları temel alan MFC koleksiyon sınıfları listelenmektedir.

### <a name="nontemplate-collection-classes"></a>Şablon olmayan koleksiyon sınıfları

|Diziler|Listeler|Haritalar|
|------------|-----------|----------|
|`CObArray`|`CObList`|`CMapPtrToWord`|
|`CByteArray`|`CPtrList`|`CMapPtrToPtr`|
|`CDWordArray`|`CStringList`|`CMapStringToOb`|
|`CPtrArray`||`CMapStringToPtr`|
|`CStringArray`||`CMapStringToString`|
|`CWordArray`||`CMapWordToOb`|
|`CUIntArray`||`CMapWordToPtr`|

[Bir koleksiyon sınıfı seçme önerilerinde](recommendations-for-choosing-a-collection-class.md) mfc koleksiyon sınıfları tablosunun ÖZELLIKLERI, mfc koleksiyon sınıflarını bu Özellikler (şekil dışında) açısından tanımlar:

- Sınıfın C++ şablonları kullanıp kullanmadığını belirtir

- Koleksiyonda depolanan öğelerin seri hale getirilebilir olup olmadığı

- Koleksiyonda depolanan öğelerin Tanılama için dökülebilir olup olmadığı

- Koleksiyonun tür açısından güvenli olup olmadığı

### <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

#### <a name="general-collection-class-tasks"></a>Genel Collection-Class görevleri

- [Koleksiyon sınıfı seçme önerileri](recommendations-for-choosing-a-collection-class.md)

- [Nasıl yapılır: Type-Safe koleksiyonu oluşturma](how-to-make-a-type-safe-collection.md)

- [Yığın ve kuyruk koleksiyonları oluşturma](creating-stack-and-queue-collections.md)

- [CArray:: Add](reference/carray-class.md#add)

#### <a name="template-based-collection-class-tasks"></a>Template-Based Collection-Class görevleri

- [Şablon tabanlı sınıflar](template-based-classes.md)

#### <a name="accessing-the-members-of-a-collection-template-based-or-not"></a>Bir koleksiyonun üyelerine erişme (şablon tabanlı veya olmayan)

- [Bir koleksiyonun tüm üyelerine erişme](accessing-all-members-of-a-collection.md)

- [CObject koleksiyonundaki tüm nesneleri silme](deleting-all-objects-in-a-cobject-collection.md)

## <a name="see-also"></a>Ayrıca bkz.

[Kavramlar](mfc-concepts.md)<br/>
[Genel MFC konuları](general-mfc-topics.md)
