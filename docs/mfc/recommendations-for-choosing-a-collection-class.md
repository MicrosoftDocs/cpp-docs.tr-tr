---
description: 'Daha fazla bilgi için: koleksiyon sınıfı seçme önerileri'
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
ms.openlocfilehash: 47cf0cc1f52a10d641dba9eecbd49190d9820f41
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248540"
---
# <a name="recommendations-for-choosing-a-collection-class"></a>Koleksiyon Sınıfı Seçme Önerileri

Bu makale, belirli uygulama gereksinimleriniz için bir koleksiyon sınıfı seçmenize yardımcı olmak üzere tasarlanan ayrıntılı bilgiler içerir.

Koleksiyon sınıfı seçiminiz, aşağıdakiler dahil olmak üzere çeşitli etkenlere bağlıdır:

- Bu konunun ilerleyen kısımlarında [koleksiyon şekli özellikleri](#_core_collection_shape_features) tablosunda gösterildiği gibi, sınıf şeklinin özellikleri: Order, Indexing ve Performance

- Sınıfın C++ şablonları kullanıp kullanmadığını belirtir

- Koleksiyonda depolanan öğelerin seri hale getirilebilir olup olmadığı

- Koleksiyonda depolanan öğelerin Tanılama için dökülebilir olup olmadığı

- Koleksiyonun tür açısından güvenli olup olmadığı

Aşağıdaki tablo olan [koleksiyon şekli özellikleri](#_core_collection_shape_features), kullanılabilir koleksiyon şekillerinin özelliklerini özetler.

- 2 ve 3. sütunlar her şeklin sıralama ve erişim özelliklerini anlatmaktadır. Tabloda, "siparişli" terimi, öğelerin eklendiği ve silineceği sıranın koleksiyondaki sıralarını belirler; öğelerin içeriklerinin sıralandığı anlamına gelmez. "Dizinli" terimi, koleksiyondaki öğelerin tipik bir dizideki öğeler gibi bir tamsayı dizin tarafından alınamayacağını gösterir.

- 4. ve 5. sütunlar her bir şeklin performansını anlatmaktadır. Koleksiyonda çok sayıda eklemeler gerektiren uygulamalarda, ekleme hızı özellikle önemli olabilir; diğer uygulamalar için, arama hızı daha önemli olabilir.

- Sütun 6 her şeklin yinelenen öğelere izin verip içermediğini açıklar.

### <a name="collection-shape-features"></a><a name="_core_collection_shape_features"></a> Koleksiyon şekli özellikleri

|Şekil|Sipariş edildi|Oluşturulmayacak|Öğe Ekle|Belirtilen öğe için ara|Yinelenen öğeler|
|-----------|--------------|--------------|-----------------------|----------------------------------|-------------------------|
|Liste|Evet|Hayır|Hızlı|Yavaş|Evet|
|Dizi|Evet|İnt 'e göre|Yavaş|Yavaş|Evet|
|Harita|Hayır|Anahtara göre|Hızlı|Hızlı|Hayır (anahtar) Evet (değerler)|

Aşağıdaki tablo, [MFC koleksiyon sınıflarının özellikleri](#_core_characteristics_of_mfc_collection_classes), belirli mfc koleksiyon sınıflarının diğer önemli özelliklerini seçime yönelik bir kılavuz olarak özetler. Tercih ettiğiniz sınıf C++ şablonlarına dayanmasına bağlı olarak, kendi öğelerinin MFC 'nin tanılama [döküm mekanizması aracılığıyla](../mfc/serialization-in-mfc.md) oluşturulup oluşturulmayacağını veya sınıfın tür kullanımı güvenli olup olmadığını, yani içinde depolanan ve sınıfı temel alan bir koleksiyondan alınan öğelerin türünü garanti yapıp gerçekleştiremeyeceğinizi belirtir.

### <a name="characteristics-of-mfc-collection-classes"></a><a name="_core_characteristics_of_mfc_collection_classes"></a> MFC koleksiyon sınıflarının özellikleri

|Sınıf|C++ kullanır<br /><br /> templates|Olabilir<br /><br /> metodu|Olabilir<br /><br /> yazılan|Is<br /><br /> tür kullanımı uyumlu|
|-----------|------------------------------|---------------------------|-----------------------|-----------------------|
|`CArray`|Evet|Evet 1|Evet 1|Hayır|
|`CByteArray`|Hayır|Evet|Evet|Evet 3|
|`CDWordArray`|Hayır|Evet|Evet|Evet 3|
|`CList`|Evet|Evet 1|Evet 1|Hayır|
|`CMap`|Evet|Evet 1|Evet 1|Hayır|
|`CMapPtrToPtr`|Hayır|Hayır|Evet|Hayır|
|`CMapPtrToWord`|Hayır|Hayır|Evet|Hayır|
|`CMapStringToOb`|Hayır|Evet|Evet|Hayır|
|`CMapStringToPtr`|Hayır|Hayır|Evet|Hayır|
|`CMapStringToString`|Hayır|Evet|Evet|Evet 3|
|`CMapWordToOb`|Hayır|Evet|Evet|Hayır|
|`CMapWordToPtr`|Hayır|Hayır|Evet|Hayır|
|`CObArray`|Hayır|Evet|Evet|Hayır|
|`CObList`|Hayır|Evet|Evet|Hayır|
|`CPtrArray`|Hayır|Hayır|Evet|Hayır|
|`CPtrList`|Hayır|Hayır|Evet|Hayır|
|`CStringArray`|Hayır|Evet|Evet|Evet 3|
|`CStringList`|Hayır|Evet|Evet|Evet 3|
|`CTypedPtrArray`|Evet|Bağımlı 2|Evet|Evet|
|`CTypedPtrList`|Evet|Bağımlı 2|Evet|Evet|
|`CTypedPtrMap`|Evet|Bağımlı 2|Evet|Evet|
|`CUIntArray`|Hayır|Hayır|Evet|Evet 3|
|`CWordArray`|Hayır|Evet|Evet|Evet 3|

1. Seri hale getirmek için, koleksiyon nesnesinin işlevini açık bir şekilde çağırmanız gerekir `Serialize` ; böylece, kendi işlevini açıkça çağırmanız gerekir `Dump` . `ar << collObj`Seri hale getirmek için formunu veya `dmp` `<< collObj` dökümünü almak için kullanamazsınız.

2. Serializbilme, temeldeki koleksiyon türüne bağlıdır. Örneğin, türü belirlenmiş bir işaretçi dizisi temel alıyorsa `CObArray` , seri hale getirilebilir olur; temel alıyorsa `CPtrArray` , seri hale getirilebilir değildir. Genel olarak, "PTR" sınıfları serileştirilemiyor.

3. Bu sütunda Evet olarak işaretlenmişse, şablon olmayan koleksiyon sınıfı tür açısından güvenlidir ve bunu amaçlanan olarak kullanırsınız. Örneğin, bir içinde bayt depolarsanız `CByteArray` , dizi tür açısından güvenlidir. Ancak, karakterleri depolamak için kullanıyorsanız, tür güvenliği daha az önemlidir.

## <a name="see-also"></a>Ayrıca bkz.

[Koleksiyonlar](../mfc/collections.md)<br/>
[Şablon tabanlı sınıflar](../mfc/template-based-classes.md)<br/>
[Nasıl yapılır: Type-Safe koleksiyonu oluşturma](../mfc/how-to-make-a-type-safe-collection.md)<br/>
[Bir koleksiyonun tüm üyelerine erişme](../mfc/accessing-all-members-of-a-collection.md)
