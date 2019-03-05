---
title: Koleksiyon Sınıfı Seçme Önerileri
ms.date: 11/04/2016
helpviewer_keywords:
- type safety of collection classes [MFC]
- collection classes [MFC], serialization
- collection classes [MFC], speed
- collection classes [MFC], type safety
- collection classes [MFC], choosing
- collection classes [MFC], functionality
- shapes, collection
- collection classes [MFC], template-based
- MFC collection classes [MFC], characteristics
- collection classes [MFC], about collection classes [MFC]
- serialization [MFC], collection classes
- collection classes [MFC], duplicates allowed
- collection classes [MFC], shapes
ms.assetid: a82188cd-443f-40d8-a244-edf292a53db4
ms.openlocfilehash: c72a57385b0036d98629d1ee24111500b9d2f8ad
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57288044"
---
# <a name="recommendations-for-choosing-a-collection-class"></a>Koleksiyon Sınıfı Seçme Önerileri

Bu makalede, bir koleksiyon sınıfı için belirli uygulamanızın gereksinimlerine göre seçmenize yardımcı olmak için tasarlanan ayrıntılı bilgiler içerir.

Seçtiğiniz koleksiyon sınıfı dahil çeşitli Etkenler sayısına bağlıdır:

- Sınıf şeklinin özelliklerinin: sırası, dizin oluşturma ve performans gösterildiği gibi [koleksiyonu şekli özellikleri](#_core_collection_shape_features) tablo bu konunun devamındaki

- Sınıf C++ şablonları kullanıp kullanmadığını

- Bir koleksiyonda depolanan öğeleri seri hale getirilebilir

- Bir koleksiyonda depolanan öğeleri tanılama için yazılan

- Tür kullanımı uyumlu koleksiyon olup

Aşağıdaki tabloda, [koleksiyonu şekli özellikleri](#_core_collection_shape_features), kullanılabilir toplama şekillerinin özellikleri özetlenmektedir.

- Sütun 2 ve 3 her şeklin sıralama açıklamak ve özelliklere erişim. Tabloda, bunların sırası koleksiyondaki belirleyen öğeleri eklenen ve Silinen sırası "sıralı" terimi anlamına gelir; öğeler içeriklerine göre sıralanır gelmez. "Dizin" terimi, koleksiyondaki öğelerin tipik bir dizi öğelerinde gibi bir tamsayı dizini tarafından alınabilen anlamına gelir.

- 4. ve 5 sütunları her şeklin performans açıklanmaktadır. Koleksiyona birçok eklemeler gerektiren uygulamalarda ekleme hızının özellikle önemli olabilir; diğer uygulamalar için hızlı arama daha önemli olabilir.

- Her bir şeklin yinelenen öğeler izin verip vermediğini sütun 6 açıklar.

### <a name="_core_collection_shape_features"></a>  Koleksiyonu şekli özellikleri

|Şekil|Sıralı|Dizin|Öğe ekleme|Belirtilen öğeyi arayın|Yinelenen öğeler|
|-----------|--------------|--------------|-----------------------|----------------------------------|-------------------------|
|List|Evet|Hayır|Hızlı|Yavaş|Evet|
|Dizi|Evet|Tarafından int|Yavaş|Yavaş|Evet|
|Eşleme|Hayır|Anahtara göre|Hızlı|Hızlı|Evet (değerler) (anahtar)|

Aşağıdaki tabloda, [MFC koleksiyon sınıfları özellikleri](#_core_characteristics_of_mfc_collection_classes), seçim kılavuzu olarak belirli MFC koleksiyon sınıfları diğer önemli özelliklerini özetler. Öğeleri MFC'nin belge seri hale getirilebilir olup olmadığını seçtiğiniz olup C++ şablonları temel sınıf alan değişebilir [serileştirme](../mfc/serialization-in-mfc.md) mekanizması, öğeleri MFC yazılan olmadığını mekanizması dökme Tanılama veya sınıfı, tür kullanımı uyumlu olup — diğer bir deyişle, öğelerin türü garanti edebilir ve depolanan bir koleksiyon sınıfına göre alınır.

### <a name="_core_characteristics_of_mfc_collection_classes"></a>  MFC koleksiyon sınıfları, özellikleri

|örneği|C++ kullanır<br /><br /> templates|Olabilir<br /><br /> seri hale getirilmiş|Olabilir<br /><br /> yazılan|olduğu<br /><br /> tür kullanımı uyumlu|
|-----------|------------------------------|---------------------------|-----------------------|-----------------------|
|`CArray`|Evet|1 Evet|1 Evet|Hayır|
|`CByteArray`|Hayır|Evet|Evet|3 Evet|
|`CDWordArray`|Hayır|Evet|Evet|3 Evet|
|`CList`|Evet|1 Evet|1 Evet|Hayır|
|`CMap`|Evet|1 Evet|1 Evet|Hayır|
|`CMapPtrToPtr`|Hayır|Hayır|Evet|Hayır|
|`CMapPtrToWord`|Hayır|Hayır|Evet|Hayır|
|`CMapStringToOb`|Hayır|Evet|Evet|Hayır|
|`CMapStringToPtr`|Hayır|Hayır|Evet|Hayır|
|`CMapStringToString`|Hayır|Evet|Evet|3 Evet|
|`CMapWordToOb`|Hayır|Evet|Evet|Hayır|
|`CMapWordToPtr`|Hayır|Hayır|Evet|Hayır|
|`CObArray`|Hayır|Evet|Evet|Hayır|
|`CObList`|Hayır|Evet|Evet|Hayır|
|`CPtrArray`|Hayır|Hayır|Evet|Hayır|
|`CPtrList`|Hayır|Hayır|Evet|Hayır|
|`CStringArray`|Hayır|Evet|Evet|3 Evet|
|`CStringList`|Hayır|Evet|Evet|3 Evet|
|`CTypedPtrArray`|Evet|2 bağlıdır|Evet|Evet|
|`CTypedPtrList`|Evet|2 bağlıdır|Evet|Evet|
|`CTypedPtrMap`|Evet|2 bağlıdır|Evet|Evet|
|`CUIntArray`|Hayır|Hayır|Evet|3 Evet|
|`CWordArray`|Hayır|Evet|Evet|3 Evet|

1. Seri hale getirmek için açıkça koleksiyon nesnesinin çağırmalıdır `Serialize` işlev; dökümünü almak için açıkça çağırmanız gerekir, `Dump` işlevi. Form kullanamazsınız `ar << collObj` serileştirilecek veya formun `dmp` `<< collObj` dökümünü almak için.

2. Serializability temel alınan koleksiyon türüne bağlıdır. Örneğin, bir işaretçi türü belirlenmiş dizi temel alıyorsa `CObArray`, bu temel seri hale getirilebilir; `CPtrArray`, serileştirilebilir değil. Genel olarak, "Ptr" sınıfları seri hale getirilemiyor.

3. Sağlanan beklendiği gibi kullanın Bu sütunda Evet işaretliyse, şablon Olmayandan koleksiyon sınıfı tür bakımından güvenlidir. Örneğin, bayt cinsinden depoladığınızda bir `CByteArray`, dizi tür bakımından güvenlidir. Ancak karakter depolamak için kullanmak, kendi tür güvenliği belirli daha az.

## <a name="see-also"></a>Ayrıca bkz.

[Koleksiyonlar](../mfc/collections.md)<br/>
[Şablona Dayalı Sınıflar](../mfc/template-based-classes.md)<br/>
[Nasıl yapılır: Tür kullanımı uyumlu koleksiyon yapma](../mfc/how-to-make-a-type-safe-collection.md)<br/>
[Bir Koleksiyonun Tüm Üyelerine Erişme](../mfc/accessing-all-members-of-a-collection.md)
