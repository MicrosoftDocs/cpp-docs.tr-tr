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
ms.openlocfilehash: 53a4eb3e30048d9dc82722d912a026d63a87586d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371741"
---
# <a name="recommendations-for-choosing-a-collection-class"></a>Koleksiyon Sınıfı Seçme Önerileri

Bu makalede, belirli uygulama gereksinimleriniz için bir koleksiyon sınıfı seçmenize yardımcı olmak üzere tasarlanmış ayrıntılı bilgiler yer alır.

Bir koleksiyon sınıfı seçiminiz, aşağıdakiler de dahil olmak üzere bir dizi etkene bağlıdır:

- Sınıf şeklinin özellikleri: bu konuda daha sonra [Toplama Şekli Özellikleri](#_core_collection_shape_features) tablosunda gösterildiği gibi, sıra, dizin oluşturma ve performans

- Sınıfın C++ şablonlarını kullanıp kullanmadığı

- Koleksiyonda depolanan öğelerin serihale edilip edilemeyeceği

- Koleksiyonda depolanan öğelerin tanılama için atılıp atılamayacağı

- Koleksiyonun tür güvenli olup olmadığı

Aşağıdaki tablo, [Koleksiyon Şekli Özellikleri,](#_core_collection_shape_features)kullanılabilir koleksiyon şekillerinin özelliklerini özetler.

- 2 ve 3 sütunları her şeklin sıralama ve erişim özelliklerini açıklar. Tabloda, "sıralı" terimi, maddelerin eklendiği ve silindiği sıranın koleksiyondaki siparişlerini belirlediği anlamına gelir; öğelerin içerikleri üzerinde sıralanmış olduğu anlamına gelmez. "Dizinlenmiş" terimi, koleksiyondaki öğelerin tipik bir dizideki öğeler gibi bir tamsayı dizini tarafından alınabileceği anlamına gelir.

- 4 ve 5 sütunları her şeklin performansını açıklar. Koleksiyona çok sayıda ekleme gerektiren uygulamalarda ekleme hızı özellikle önemli olabilir; diğer uygulamalar için, arama hızı daha önemli olabilir.

- Sütun 6, her şeklin yinelenen öğelere izin verip vermediğini açıklar.

### <a name="collection-shape-features"></a><a name="_core_collection_shape_features"></a>Koleksiyon Şekli Özellikleri

|Şekil|Sipariş edildi|Dizine|Bir öğe ekleme|Belirtilen öğeyi arama|Yinelenen öğeler|
|-----------|--------------|--------------|-----------------------|----------------------------------|-------------------------|
|Liste|Evet|Hayır|Hızlı|Yavaş|Evet|
|Dizi|Evet|Yazar: int|Yavaş|Yavaş|Evet|
|Eşleme|Hayır|Anahtara göre|Hızlı|Hızlı|Hayır (tuşlar) Evet (değerler)|

Aşağıdaki tablo, [MFC Koleksiyon Sınıflarının Özellikleri,](#_core_characteristics_of_mfc_collection_classes)seçim kılavuzu olarak belirli MFC toplama sınıflarının diğer önemli özelliklerini özetler. Seçiminiz sınıfın C++ şablonlarına dayalı olup olmadığına, öğelerinin MFC'nin belge [serileştirme](../mfc/serialization-in-mfc.md) mekanizması aracılığıyla serihale edilip edilemeyeceğine, öğelerinin MFC'nin tanılama boşaltma mekanizması yla döşeyip atılamayacağına veya sınıfın tür açısından güvenli olup olmadığına , yani sınıfa dayalı bir koleksiyonda depolanan ve alınan öğelerin türünü garanti edip edemeyeceğinize bağlı olabilir.

### <a name="characteristics-of-mfc-collection-classes"></a><a name="_core_characteristics_of_mfc_collection_classes"></a>MFC Toplama Sınıflarının Özellikleri

|Sınıf|C++ kullanır<br /><br /> templates|Olabilir<br /><br /> Seri|Olabilir<br /><br /> Terk|Is<br /><br /> tip güvenli|
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
|`CTypedPtrArray`|Evet|Değişir 2|Evet|Evet|
|`CTypedPtrList`|Evet|Değişir 2|Evet|Evet|
|`CTypedPtrMap`|Evet|Değişir 2|Evet|Evet|
|`CUIntArray`|Hayır|Hayır|Evet|Evet 3|
|`CWordArray`|Hayır|Evet|Evet|Evet 3|

1. Seri hale getirmek için, koleksiyon nesnesinin `Serialize` işlevini açıkça aramanız gerekir; dökümü için, açıkça işlevini `Dump` aramanız gerekir. Formu `ar << collObj` serihale getirmek için veya `dmp` `<< collObj` dökümü yapmak için formu kullanamazsınız.

2. Serializability altta yatan toplama türüne bağlıdır. Örneğin, bir yazılı işaretçi dizisi `CObArray`temel alınabiliyorsa, serileştirilebilir; dayalı `CPtrArray`ise, serileştirilebilir değildir. Genel olarak, "Ptr" sınıfları seri hale getirilemez.

3. Bu sütunda Evet işaretliyse, şablonsuz bir koleksiyon sınıfı, istediğiniz gibi kullanmanız koşuluyla tür güvenlidir. Örneğin, baytları bir `CByteArray`dizide depolarsanız, dizi tür açısından güvenlidir. Ancak karakterleri depolamak için kullanırsanız, türü güvenliği daha az kesindir.

## <a name="see-also"></a>Ayrıca bkz.

[Koleksiyonlar](../mfc/collections.md)<br/>
[Şablona Dayalı Sınıflar](../mfc/template-based-classes.md)<br/>
[Nasıl yapılır: Tür Kullanımı Uyumlu Koleksiyon Yapma](../mfc/how-to-make-a-type-safe-collection.md)<br/>
[Bir Koleksiyonun Tüm Üyelerine Erişme](../mfc/accessing-all-members-of-a-collection.md)
