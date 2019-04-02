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
ms.openlocfilehash: f3dea68deaae73313fe389be49e8bbed7da3c93a
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58767190"
---
# <a name="collections"></a>Koleksiyonlar

Microsoft Foundation Class Kitaplığı nesnelerinin grupları yönetmek için koleksiyon sınıfları sağlar. Bu sınıfların iki türleri şunlardır:

- [C++ şablonlarından oluşturulan koleksiyon sınıfları](#_core_the_template_based_collection_classes)

- [Şablonlardan oluşturulmamış koleksiyon sınıfları](#_core_the_collection_classes_not_based_on_templates)

> [!NOTE]
>  Kodunuzu sınıflarındaki koleksiyon sınıfları kullanıyorsa, bunları kullanmaya devam edebilirsiniz. Yeni tür kullanımı uyumlu koleksiyon sınıfları kendi veri türleri için yazarsanız, daha yeni bir şablona dayalı sınıflar kullanmanızı öneririz.

##  <a name="_core_collection_shapes"></a> Koleksiyon şekiller

Koleksiyon sınıfı öğelerini türlerini ve "şeklini" tarafından belirlenir. Şekil nesneleri düzenlenir ve koleksiyonda depolanan biçimini ifade eder. MFC üç temel koleksiyonu şekil sağlar: listeler, diziler ve (sözlükleri olarak da bilinir) eşler. Belirli programlama sorununuz için en uygun koleksiyon şekli seçebilirsiniz.

Her üç sağlanan koleksiyon şekillerinin daha kısa bir süre sonra bu konuda açıklanmıştır. Programınız için en iyi olduğu karar vermenize yardımcı olacak şekillerinin özellikleri karşılaştırmak için bkz [koleksiyon sınıfı seçme önerileri](../mfc/recommendations-for-choosing-a-collection-class.md).

- List

   List sınıfı karakteriyle bağlı bir liste uygulanan öğe sıralı, dizinlenmemiş bir listesini sağlar. Bir liste "head" ve "tail" ve ekleme veya baş veya kuyruk, ekleme veya öğeleri ortada silme öğelerin kaldırılması çok hızlı olması.

- Dizi

   Array sınıfı nesnelerini dinamik olarak ölçekli, sıralı ve tamsayı dizini oluşturulmuş bir dizi sağlar.

- Harita (sözlük olarak da bilinir)

   Harita anahtar nesneye bir değer nesnesi ile ilişkilendiren bir koleksiyondur.

##  <a name="_core_the_template_based_collection_classes"></a> Şablona dayalı koleksiyon sınıfları

Herhangi bir türde nesneleri içeren bir tür kullanımı uyumlu koleksiyon uygulamak için en kolay yolu MFC şablona dayalı sınıflar birini kullanmaktır. Bu sınıfların örnekleri için bkz. MFC örnek [TOPLAMAK](../overview/visual-cpp-samples.md).

MFC şablona dayalı koleksiyon sınıfları aşağıdaki tabloda listelenmektedir.

### <a name="collection-template-classes"></a>Koleksiyon şablon sınıfları

|Koleksiyon içeriği|Diziler|Listeler|Haritalar|
|-------------------------|------------|-----------|----------|
|Herhangi bir türde nesne koleksiyonları|`CArray`|`CList`|`CMap`|
|Herhangi bir türde nesne işaretçileri koleksiyonları|`CTypedPtrArray`|`CTypedPtrList`|`CTypedPtrMap`|

##  <a name="_core_the_collection_classes_not_based_on_templates"></a> Şablonlarına dayalı koleksiyon sınıfları

Uygulamanız zaten MFC sınıflarındaki sınıfları kullanıyorsa, bunları kullanmaya devam edebilirsiniz. Ancak, yeni koleksiyonlar için şablona dayalı sınıflar kullanmanızı öneririz. Şablonlarına dayalı olmayan MFC koleksiyon sınıfları aşağıdaki tabloda listelenmektedir.

### <a name="nontemplate-collection-classes"></a>Şablon Olmayandan koleksiyon sınıfları

|Diziler|Listeler|Haritalar|
|------------|-----------|----------|
|`CObArray`|`CObList`|`CMapPtrToWord`|
|`CByteArray`|`CPtrList`|`CMapPtrToPtr`|
|`CDWordArray`|`CStringList`|`CMapStringToOb`|
|`CPtrArray`||`CMapStringToPtr`|
|`CStringArray`||`CMapStringToString`|
|`CWordArray`||`CMapWordToOb`|
|`CUIntArray`||`CMapWordToPtr`|

MFC koleksiyon sınıfları özellikleri tablosu içinde [koleksiyon sınıfı seçme önerileri](../mfc/recommendations-for-choosing-a-collection-class.md) bu özelliklerini (dışında Şekil) açısından MFC koleksiyon sınıfları açıklar:

- Sınıf C++ şablonları kullanıp kullanmadığını

- Bir koleksiyonda depolanan öğeleri seri hale getirilebilir

- Bir koleksiyonda depolanan öğeleri tanılama için yazılan

- Tür kullanımı uyumlu koleksiyon olup

### <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz

#### <a name="general-collection-class-tasks"></a>Koleksiyon sınıfı genel görevler

- [Koleksiyon Sınıfı Seçme Önerileri](../mfc/recommendations-for-choosing-a-collection-class.md)

- [Nasıl yapılır: Tür kullanımı uyumlu koleksiyon yapma](../mfc/how-to-make-a-type-safe-collection.md)

- [Yığın ve Kuyruk Koleksiyonları Oluşturma](../mfc/creating-stack-and-queue-collections.md)

- [CArray::Add](../mfc/reference/carray-class.md#add)

#### <a name="template-based-collection-class-tasks"></a>Şablona dayalı koleksiyon sınıfı görevleri

- [Şablona Dayalı Sınıflar](../mfc/template-based-classes.md)

#### <a name="accessing-the-members-of-a-collection-template-based-or-not"></a>Bir koleksiyonun üyelerine erişme (şablon tabanlı veya değil)

- [Bir Koleksiyonun Tüm Üyelerine Erişme](../mfc/accessing-all-members-of-a-collection.md)

- [CObject Koleksiyonundaki Tüm Nesneleri Silme](../mfc/deleting-all-objects-in-a-cobject-collection.md)

## <a name="see-also"></a>Ayrıca bkz.

[Kavramları](../mfc/mfc-concepts.md)<br/>
[Genel MFC Konuları](../mfc/general-mfc-topics.md)
