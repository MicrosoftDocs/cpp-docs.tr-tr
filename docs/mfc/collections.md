---
title: Koleksiyonları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: beae5370c86bf0142b29f029778083f3042ae931
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="collections"></a>Koleksiyonlar
Microsoft Foundation Class Kitaplığı nesnelerin grupları yönetmek için koleksiyon sınıfları sağlar. Bu sınıfların iki türleri şunlardır:  
  
-   [C++ şablonlardan oluşturulabilir koleksiyon sınıfları](#_core_the_template_based_collection_classes)  
  
-   [Şablonlardan oluşturulmamış koleksiyon sınıfları](#_core_the_collection_classes_not_based_on_templates)  
  
> [!NOTE]
>  Kodunuzu şablon Olmayandan koleksiyon sınıfları kullanıyorsa, bunları kullanmaya devam edebilirsiniz. Kendi veri türleri için yeni tür kullanımı uyumlu koleksiyon sınıfları yazarsanız, daha yeni şablona dayalı sınıflar kullanmanızı öneririz.  
  
##  <a name="_core_collection_shapes"></a> Koleksiyon şekiller  
 Koleksiyon sınıfı öğelerini türlerini ve "şeklini" tarafından belirlenir. Şekil nesneleri düzenlenir ve koleksiyon tarafından depolanan biçimini ifade eder. MFC üç temel koleksiyonu şekiller sağlar: listeler, dizi ve (sözlükleri olarak da bilinir) eşler. Belirli programlama sorununuz için en uygun olan koleksiyon şekli seçebilirsiniz.  
  
 Her üç sağlanan koleksiyon şekillerin bu konuda daha sonra kısaca açıklanmıştır. Program için en iyi olduğu karar vermenize yardımcı olacak şekilleri özelliklerini karşılaştırmak için bkz: [koleksiyon sınıfı seçme önerileri](../mfc/recommendations-for-choosing-a-collection-class.md).  
  
-   List  
  
     List sınıfı karakteriyle bağlı bir liste olarak uygulanan öğeler, sıralı, dizinlenmemiş bir listesini sağlar. Bir liste "head" ve "kuyruk" vardır ve ekleme veya head veya kuyruk, ekleme veya öğeleri ortada silme öğe kaldırma çok hızlı olur.  
  
-   Dizi  
  
     Array sınıfı nesneleri dinamik olarak boyutlu, sıralı ve tamsayı dizini oluşturulmuş bir dizi sağlar.  
  
-   Harita (sözlüğü olarak da bilinir)  
  
     Bir harita anahtar nesne bir değer nesnesi ile ilişkilendiren bir koleksiyondur.  
  
##  <a name="_core_the_template_based_collection_classes"></a> Şablona dayalı koleksiyon sınıfları  
 Herhangi bir türde nesneleri içeren bir tür kullanımı uyumlu koleksiyon uygulamak için en kolay yolu MFC şablona dayalı sınıflar birini kullanmaktır. Bu sınıfların örnekleri için bkz: MFC örnek [TOPLAMAK](../visual-cpp-samples.md).  
  
 Aşağıdaki tabloda MFC şablona dayalı koleksiyon sınıfları listeler.  
  
### <a name="collection-template-classes"></a>Koleksiyon şablon sınıfları  
  
|Koleksiyon içeriği|Diziler|Listeler|Eşlemeleri|  
|-------------------------|------------|-----------|----------|  
|Herhangi bir türde nesne koleksiyonları|`CArray`|`CList`|`CMap`|  
|Herhangi bir türde nesne işaretçileri koleksiyonları|`CTypedPtrArray`|`CTypedPtrList`|`CTypedPtrMap`|  
  
##  <a name="_core_the_collection_classes_not_based_on_templates"></a> Şablonlar temelinde değil koleksiyon sınıfları  
 Uygulama zaten MFC şablon Olmayandan sınıfları kullanıyorsa, bunları kullanmaya devam edebilirsiniz. Ancak, yeni koleksiyonlar için şablona dayalı sınıflar kullanmanızı öneririz. Aşağıdaki tabloda, şablonlar temelinde değil MFC koleksiyon sınıfları listeler.  
  
### <a name="nontemplate-collection-classes"></a>Şablon Olmayandan koleksiyon sınıfları  
  
|Diziler|Listeler|Eşlemeleri|  
|------------|-----------|----------|  
|`CObArray`|`CObList`|`CMapPtrToWord`|  
|`CByteArray`|`CPtrList`|`CMapPtrToPtr`|  
|`CDWordArray`|`CStringList`|`CMapStringToOb`|  
|`CPtrArray`||`CMapStringToPtr`|  
|`CStringArray`||`CMapStringToString`|  
|`CWordArray`||`CMapWordToOb`|  
|`CUIntArray`||`CMapWordToPtr`|  
  
 MFC koleksiyon sınıfları özellikleri Tablo [koleksiyon sınıfı seçme önerileri](../mfc/recommendations-for-choosing-a-collection-class.md) MFC koleksiyon sınıfları (dışında Şekil) şu özelliklere açısından açıklar:  
  
-   C++ şablonları sınıfı kullanıp kullanmadığını  
  
-   Bir koleksiyonda depolanan öğeleri seri hale getirilebilir  
  
-   Bir koleksiyonda depolanan öğeler için tanılama yazılan  
  
-   Koleksiyon tür kullanımı uyumlu olup  
  
### <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz  
  
#### <a name="general-collection-class-tasks"></a>Genel koleksiyon sınıfı görevleri  
  
-   [Koleksiyon Sınıfı Seçme Önerileri](../mfc/recommendations-for-choosing-a-collection-class.md)  
  
-   [Nasıl yapılır: Tür Kullanımı Uyumlu Koleksiyon Yapma](../mfc/how-to-make-a-type-safe-collection.md)  
  
-   [Yığın ve Kuyruk Koleksiyonları Oluşturma](../mfc/creating-stack-and-queue-collections.md)  
  
-   [CArray::Add](../mfc/reference/carray-class.md#add)  
  
#### <a name="template-based-collection-class-tasks"></a>Şablona dayalı koleksiyon sınıfı görevleri  
  
-   [Şablona Dayalı Sınıflar](../mfc/template-based-classes.md)  
  
#### <a name="accessing-the-members-of-a-collection-template-based-or-not"></a>Bir koleksiyonun üyelerine erişme (şablona dayalı veya değil)  
  
-   [Bir Koleksiyonun Tüm Üyelerine Erişme](../mfc/accessing-all-members-of-a-collection.md)  
  
-   [CObject Koleksiyonundaki Tüm Nesneleri Silme](../mfc/deleting-all-objects-in-a-cobject-collection.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kavramları](../mfc/mfc-concepts.md)   
 [Genel MFC Konuları](../mfc/general-mfc-topics.md)

