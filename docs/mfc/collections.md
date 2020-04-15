---
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
ms.openlocfilehash: 3fba3a3c6cd3fecbda7f46575b1d72c450c44019
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361864"
---
# <a name="collections"></a>Koleksiyonlar

Microsoft Hazırlık Sınıf Kitaplığı, nesne gruplarını yönetmek için koleksiyon sınıfları sağlar. Bu sınıflar iki türdedir:

- [C++ şablonlarından oluşturulan toplama sınıfları](#_core_the_template_based_collection_classes)

- [Şablonlardan oluşturulmayan toplama sınıfları](#_core_the_collection_classes_not_based_on_templates)

> [!NOTE]
> Kodunuz zaten şablon olmayan toplama sınıflarını kullanıyorsa, bunları kullanmaya devam edebilirsiniz. Kendi veri türleriniz için yeni tür güvenli toplama sınıfları yazarsanız, yeni şablon tabanlı sınıfları kullanmanızı öneririz.

## <a name="collection-shapes"></a><a name="_core_collection_shapes"></a>Toplama Şekilleri

Bir toplama sınıfı "şekli" ve öğelerinin türleri ile karakterizedir. Şekil, nesnelerin koleksiyon tarafından düzenlenme ve depolanan biçimini ifade eder. MFC üç temel koleksiyon şekli sağlar: listeler, diziler ve haritalar (sözlükler olarak da bilinir). Belirli programlama sorununa en uygun koleksiyon şeklini seçebilirsiniz.

Sağlanan üç koleksiyon şeklinin her biri kısa bir süre sonra bu konuda açıklanmıştır. Programıniçin en iyi olanın hangisiolduğuna karar vermenize yardımcı olmak için şekillerin özelliklerini karşılaştırmak [için, Koleksiyon Sınıfı Seçme Önerileri'ne](../mfc/recommendations-for-choosing-a-collection-class.md)bakın.

- Liste

   Liste sınıfı, iki kat bağlı bir liste olarak uygulanan sıralı, dizine eklenmemiş öğeler listesi sağlar. Bir listenin bir "kafası" ve "kuyruğu" vardır ve kafa veya kuyruktaki öğelerin eklenmesi veya çıkarılması veya ortaya öğelerin eklenmesi veya silmesi çok hızlıdır.

- Dizi

   Dizi sınıfı dinamik olarak boyutlandırılmış, sıralı ve tamsayı dizili nesneler sağlar.

- Harita (sözlük olarak da bilinir)

   Harita, anahtar nesneyi bir değer nesnesiyle ilişkilendiren bir koleksiyondur.

## <a name="the-template-based-collection-classes"></a><a name="_core_the_template_based_collection_classes"></a>Şablon Tabanlı Koleksiyon Sınıfları

Herhangi bir türnesneleri içeren bir tür güvenli toplama uygulamak için en kolay yolu MFC şablon tabanlı sınıflardan birini kullanmaktır. Bu sınıflara örnek olarak, MFC örnek [COLLECT'e](../overview/visual-cpp-samples.md)bakın.

Aşağıdaki tabloda MFC şablon tabanlı koleksiyon sınıfları listelenir.

### <a name="collection-template-classes"></a>Koleksiyon Şablonu Sınıfları

|Koleksiyon içeriği|Diziler|Listeler|Haritalar|
|-------------------------|------------|-----------|----------|
|Herhangi bir türdeki nesnelerin koleksiyonları|`CArray`|`CList`|`CMap`|
|Herhangi bir türdeki nesnelere işaretçilerin koleksiyonları|`CTypedPtrArray`|`CTypedPtrList`|`CTypedPtrMap`|

## <a name="the-collection-classes-not-based-on-templates"></a><a name="_core_the_collection_classes_not_based_on_templates"></a>Şablonlara Dayalı Olmayan Toplama Sınıfları

Uygulamanız zaten MFC şablon olmayan sınıfları kullanıyorsa, bunları kullanmaya devam edebilirsiniz. Ancak, yeni koleksiyonlar için şablon tabanlı sınıfları kullanmanızı öneririz. Aşağıdaki tabloda şablonları temel alamayan MFC toplama sınıfları listelenir.

### <a name="nontemplate-collection-classes"></a>Şablon Olmayan Toplama Sınıfları

|Diziler|Listeler|Haritalar|
|------------|-----------|----------|
|`CObArray`|`CObList`|`CMapPtrToWord`|
|`CByteArray`|`CPtrList`|`CMapPtrToPtr`|
|`CDWordArray`|`CStringList`|`CMapStringToOb`|
|`CPtrArray`||`CMapStringToPtr`|
|`CStringArray`||`CMapStringToString`|
|`CWordArray`||`CMapWordToOb`|
|`CUIntArray`||`CMapWordToPtr`|

[Toplama Sınıfı Seçme Önerileri'ndeki](../mfc/recommendations-for-choosing-a-collection-class.md) MFC Koleksiyon Sınıfları tablosunun özellikleri, MFC toplama sınıflarını bu özellikler (şekil dışında) açısından açıklar:

- Sınıfın C++ şablonlarını kullanıp kullanmadığı

- Koleksiyonda depolanan öğelerin serihale edilip edilemeyeceği

- Koleksiyonda depolanan öğelerin tanılama için atılıp atılamayacağı

- Koleksiyonun tür güvenli olup olmadığı

### <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsun?

#### <a name="general-collection-class-tasks"></a>Genel Toplama-Sınıf Görevleri

- [Toplama Sınıfı Seçmek Için Öneriler](../mfc/recommendations-for-choosing-a-collection-class.md)

- [Nasıl yapılır: Tür Kullanımı Uyumlu Koleksiyon Yapma](../mfc/how-to-make-a-type-safe-collection.md)

- [Yığın ve Kuyruk Koleksiyonları Oluşturma](../mfc/creating-stack-and-queue-collections.md)

- [CArray::Ekle](../mfc/reference/carray-class.md#add)

#### <a name="template-based-collection-class-tasks"></a>Şablon Tabanlı Toplama-Sınıf Görevleri

- [Şablona Dayalı Sınıflar](../mfc/template-based-classes.md)

#### <a name="accessing-the-members-of-a-collection-template-based-or-not"></a>Koleksiyonun Üyelerine Erişim (Şablon Tabanlı veya Değil)

- [Bir Koleksiyonun Tüm Üyelerine Erişme](../mfc/accessing-all-members-of-a-collection.md)

- [CObject Koleksiyonundaki Tüm Nesneleri Silme](../mfc/deleting-all-objects-in-a-cobject-collection.md)

## <a name="see-also"></a>Ayrıca bkz.

[Kavramlar](../mfc/mfc-concepts.md)<br/>
[Genel MFC Konuları](../mfc/general-mfc-topics.md)
