---
title: "Koleksiyon sınıfı seçme önerileri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 312e777d86d2fd24ae84fe05b4162e1470f77e3b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="recommendations-for-choosing-a-collection-class"></a>Koleksiyon Sınıfı Seçme Önerileri
Bu makalede, belirli bir uygulama gereksinimleriniz için koleksiyon sınıfı seçmenize yardımcı olmak amacıyla tasarlanmış ayrıntılı bilgiler içerir.  
  
 Koleksiyon sınıfı seçiminiz dahil çeşitli Etkenler sayısına bağlıdır:  
  
-   Sınıf şekli özelliklerini: sırası, dizin oluşturma ve gösterildiği gibi performans [koleksiyonu şekil özellikleri](#_core_collection_shape_features) bu konunun ilerleyen bölümlerinde tablo  
  
-   C++ şablonları sınıfı kullanıp kullanmadığını  
  
-   Bir koleksiyonda depolanan öğeleri seri hale getirilebilir  
  
-   Bir koleksiyonda depolanan öğeler için tanılama yazılan  
  
-   Koleksiyon tür kullanımı uyumlu olup  
  
 Aşağıdaki tabloda, [koleksiyonu şekil özellikleri](#_core_collection_shape_features), kullanılabilir koleksiyonu şekiller özelliklerini özetler.  
  
-   Sütun 2 ve 3 özelliklere erişmek ve her şeklin sıralama açıklanmıştır. Tabloda "sipariş" terimi öğeleri eklenen ve Silinen sırasını koleksiyondaki sıralarına belirler anlamına gelir; öğeler içerikleri üzerinde sıralanır anlamına gelmez. "Dizin" terimi, koleksiyondaki öğelerin tipik bir dizi öğeleri benzer bir tamsayı dizini tarafından alınabilir anlamına gelir.  
  
-   Sütunları 4 ve 5 her şeklin performans açıklanmaktadır. Koleksiyona birçok eklemeleri gerektiren uygulamalar içinde ekleme hızının özellikle önemli olabilir; diğer uygulamalar için arama hızı daha önemli olabilir.  
  
-   Sütun 6 her şekli yinelenen öğeler izin verip vermediğini açıklar.  
  
### <a name="_core_collection_shape_features"></a>Koleksiyonu şekli özellikleri  
  
|Şekil|sıralı|Dizin oluşturulmuş|Bir öğe ekleme|Belirtilen öğe arayın|Yinelenen öğeler|  
|-----------|--------------|--------------|-----------------------|----------------------------------|-------------------------|  
|List|Evet|Hayır|Hızlı|Yavaş|Evet|  
|Dizi|Evet|Tarafından int|Yavaş|Yavaş|Evet|  
|eşleme|Hayır|Anahtara göre|Hızlı|Hızlı|Yok (anahtarlar) Evet (değerler)|  
  
 Aşağıdaki tabloda, [MFC koleksiyon sınıfları özellikleri](#_core_characteristics_of_mfc_collection_classes), seçim bir kılavuz olarak belirli MFC koleksiyon sınıfları önemli diğer özelliklerini özetler. MFC'nin belge öğeleri seri hale getirilebilir olup olmadığını tercih ettiğiniz olup C++ şablonlar, sınıfı temelinde değişebilir [seri hale getirme](../mfc/serialization-in-mfc.md) mekanizması, MFC öğeleri yazılan olup olmadığını döküm alma mekanizması, tanılama veya sınıf tür kullanımı uyumlu olup — diğer bir deyişle, öğelerin türü garanti edebilir ve depolanan sınıfına dayalı bir koleksiyon alınır.  
  
### <a name="_core_characteristics_of_mfc_collection_classes"></a>MFC koleksiyon sınıfları özellikleri  
  
|örneği|C++ kullanır<br /><br /> templates|Olabilir<br /><br /> seri hale getirilmiş|Olabilir<br /><br /> yazılan|değil<br /><br /> tür kullanımı uyumlu|  
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
  
 1. Seri hale getirmek için açıkça koleksiyon nesnesinin çağırmalısınız `Serialize` işlev; dökümü için açıkça çağırmalısınız kendi `Dump` işlevi. Formun kullanamazsınız `ar << collObj` serileştirilecek veya formun `dmp` `<< collObj` dökümü.  
  
 2. Serializability temel alınan koleksiyon türüne göre değişir. Örneğin, yazılan işaretçi dizi dayanıyorsa `CObArray`, bunu temel seri hale getirilebilir; ise `CPtrArray`, seri hale getirilebilir değil. Genel olarak, "Ptr" sınıfları seri hale getirilemez.  
  
 3. Tasarlandığı gibi kullanın Bu sütunda Evet işaretliyse, şablon Olmayandan koleksiyon sınıfı tür kullanımı uyumlu bulunur. Örneğin, bayt cinsinden depolarsanız bir `CByteArray`, tür kullanımı uyumlu dizisidir. Ancak karakter depolamak için kullanmak, kendi tür güvenliği daha az belirli.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Koleksiyonları](../mfc/collections.md)   
 [Şablona dayalı sınıflar](../mfc/template-based-classes.md)   
 [Nasıl yapılır: tür kullanımı uyumlu koleksiyon yapma](../mfc/how-to-make-a-type-safe-collection.md)   
 [Bir koleksiyonun tüm üyelerine erişme](../mfc/accessing-all-members-of-a-collection.md)

