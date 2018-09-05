---
title: ATL koleksiyon sınıfları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DestructElements function
- collection classes, choosing
- ConstructElements function
- SerializeElements function
- traits classes
- collection classes, about collection classes
- CTraits classes
- collection classes
ms.assetid: 4d619d46-5b4e-41dd-b9fd-e86b1fbc00b5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c40303e0353e9f7ef3740e55381306507878b72b
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43752638"
---
# <a name="atl-collection-classes"></a>ATL Koleksiyon Sınıfları

ATL depolamak ve verilere erişmek için birçok sınıflar sağlar. Kullanmaya karar hangi sınıfı dahil olmak üzere çeşitli etkenlere bağlıdır:

- Depolanacak veri miktarını

- Kıyasla performans verilerine erişme

- Dizine göre veya anahtara göre veri erişim olanağı

- Verilerin nasıl düzenlenir

- Kişisel tercihi

## <a name="small-collection-classes"></a>Küçük koleksiyon sınıfları

ATL, küçük sayılar nesnelerin başa çıkmak için aşağıdaki dizi sınıfları sağlar. Bu sınıfların ancak sınırlı ve ATL tarafından dahili olarak kullanmak üzere tasarlanan Bunlar programlarınızda kullanmayı önerilmez.

|örneği|Veri depolama türü|
|-----------|--------------------------|
|[CSimpleArray](../atl/reference/csimplearray-class.md)|Küçük sayıda nesne içeren başa çıkmak için bir dizi sınıf uygular.|
|[CSimpleMap](../atl/reference/csimplemap-class.md)|Küçük sayıda nesne içeren başa çıkmak için bir eşleme sınıf uygular.|

## <a name="general-purpose-collection-classes"></a>Genel amaçlı koleksiyon sınıfları

Aşağıdaki sınıflar, diziler, listeler ve eşlemeler uygulamak ve genel amaçlı koleksiyon sınıfları sağlanır:

|örneği|Veri depolama türü|
|-----------|--------------------------|
|[CAtlArray](../atl/reference/catlarray-class.md)|Bir dizi uygular.|
|[CAtlList](../atl/reference/catllist-class.md)|Listesini uygular.|
|[CAtlMap](../atl/reference/catlmap-class.md)|Anahtar veya değer tarafından veri yapabildiği başvurulabilen bir eşleme yapısı uygular.|
|[CRBMap](../atl/reference/crbmap-class.md)|Kırmızı-siyah algoritmasını kullanarak bir eşleme yapısı uygular.|
|[CRBMultiMap](../atl/reference/crbmultimap-class.md)|Kırmızı-siyah multimapping yapısı uygular.|

Bu sınıfların hata ayıklama yapılarında kullanılan pek çok programlama hatalarını yakalar, ancak performans for sake of perakende sürümlerde bu denetimleri gerçekleştirilmez.

## <a name="specialized-collection-classes"></a>Özel koleksiyon sınıfları

Daha özel koleksiyon sınıfları, bellek işaretçiler ve arabirim işaretçilerini yönetmek için de sağlanır:

|örneği|Amaç|
|-----------|-------------|
|[CAutoPtrArray](../atl/reference/cautoptrarray-class.md)|Akıllı işaretçiler dizisi oluştururken kullanışlı yöntemler sağlar.|
|[CAutoPtrList](../atl/reference/cautoptrlist-class.md)|Akıllı işaretçiler listesini oluştururken kullanışlı yöntemler sağlar.|
|[CComUnkArray](../atl/reference/ccomunkarray-class.md)|Depoları `IUnknown` işaretçileri ve parametre olarak kullanılmak üzere tasarlanmış [Iconnectionpointımpl](../atl/reference/iconnectionpointimpl-class.md) Şablon sınıfı.|
|[CHeapPtrList](../atl/reference/cheapptrlist-class.md)|Yığın işaretçileri listesini oluştururken kullanışlı yöntemler sağlar.|
|[Cınterfacearray](../atl/reference/cinterfacearray-class.md)|Bir COM arabirimi işaretçiler dizisi oluştururken kullanışlı yöntemler sağlar.|
|[Cınterfacelist](../atl/reference/cinterfacelist-class.md)|COM arabirim işaretçilerini listesini oluştururken kullanışlı yöntemler sağlar.|

## <a name="choosing-a-collection-class"></a>Koleksiyon sınıfı seçme

Aşağıdaki tabloda gösterildiği gibi mevcut koleksiyon sınıflarının her biri farklı performans özellikleri sunar.

- Sütun 2 ve 3 her sınıfın sıralama açıklamak ve özelliklere erişim. Tabloda, bunların sırası koleksiyondaki belirleyen öğeleri eklenen ve Silinen sırası "sıralı" terimi anlamına gelir; öğeler içeriklerine göre sıralanır gelmez. "Dizin" terimi, koleksiyondaki öğelerin tipik bir dizi öğelerinde gibi bir tamsayı dizini tarafından alınabilen anlamına gelir.

- 4. ve 5 sütunları her sınıfın performans açıklanmaktadır. Koleksiyona birçok eklemeler gerektiren uygulamalarda ekleme hızının özellikle önemli olabilir; diğer uygulamalar için hızlı arama daha önemli olabilir.

- Her bir şeklin yinelenen öğeler izin verip vermediğini sütun 6 açıklar.

- Bir koleksiyon sınıfı işleminin performansı bakımından işlemi ve koleksiyondaki öğe sayısını tamamlamak için gereken süreyi arasındaki ilişki gösterilir. Zaman alan bir işlem sayısı arttıkça öğeleri O(n) algoritma açıklandığı gibi doğrusal olarak artırır. Daha sayısı arttıkça öğeleri olarak artıran bir süre alma işleminin aksine, bir O (log n) algoritması açıklanmaktadır. Bu nedenle, performans açısından, O (log n) algoritmaları O(n) algoritmaları daha sayısı arttıkça öğeleri olarak daha iyi performans gösterir.

### <a name="collection-shape-features"></a>Koleksiyonu şekli özellikleri

|Şekil|Sıralı|Dizin|INSERT bir<br /><br /> öğesi|Aranan:<br /><br /> Belirtilen öğe|Yinelenen<br /><br /> öğeler|
|-----------|--------------|--------------|---------------------------|--------------------------------------|-----------------------------|
|List|Evet|Hayır|Hızlı (sabit zaman)|Yavaş O(n)|Evet|
|Dizi|Evet|İnt tarafından (sabit zaman)|Sonunda, büyük/küçük harf hangi Sabit sürede ekleme, dışında O(n) yavaş|Yavaş O(n)|Evet|
|Harita|Hayır|Anahtara göre (sabit zaman)|Hızlı (sabit zaman)|Hızlı (sabit zaman)|Evet (değerler) (anahtar)|
|Kırmızı-siyah eşleme|Evet (anahtar)|Anahtara göre O (log n)|Hızlı O (log n)|Hızlı O (log n)|Hayır|
|Kırmızı-siyah Multimap|Evet (anahtar)|Anahtara göre O(log n) (birden çok değer anahtarı başına)|Hızlı O (log n)|Hızlı O (log n)|Evet (birden çok değer anahtarı başına)|

## <a name="using-ctraits-objects"></a>CTraits nesnelerini kullanma

ATL koleksiyon sınıfları çeşitli kullanıcı tanımlı veri türleri depolamak için kullanılan karşılaştırma gibi önemli işlevleri geçersiz kılma yararlı olabilir. CTraits sınıfları kullanılarak elde edilir.

CTraits sınıfları benzer, ancak daha esnektir, MFC koleksiyon sınıfı yardımcı işlevleri; bkz: [koleksiyon sınıfı Yardımcıları](../mfc/reference/collection-class-helpers.md) daha fazla bilgi için.

Koleksiyon sınıfınıza oluştururken CTraits sınıf belirtme seçeneğiniz vardır. Bu sınıf koleksiyon sınıfı oluşturan diğer yöntemlerle çağrıldığında karşılaştırmalar gibi işlemleri gerçekleştiren kod içerir. Örneğin, liste nesnesi kendi kullanıcı tarafından tanımlanan yapıları içeriyorsa, yalnızca belirli üye değişkenleri karşılaştırmak için eşitlik testi yeniden tanımlamak isteyebilirsiniz. Liste nesne bulma yöntemi, bu şekilde, daha kullanışlı bir şekilde çalışır.

## <a name="example"></a>Örnek

### <a name="code"></a>Kod

[!code-cpp[NVC_ATL_Utilities#112](../atl/codesnippet/cpp/atl-collection-classes_1.cpp)]

## <a name="comments"></a>Açıklamalar

CTraits sınıfları listesi için bkz. [koleksiyon sınıfları](../atl/collection-classes.md).

Aşağıdaki diyagramda CTraits sınıfları için sınıf hiyerarşisini gösterir.

![Koleksiyon sınıfları için karakter hiyerarşisi](../atl/media/vctraitscollectionclasseshierarchy.gif "vctraitscollectionclasseshierarchy")

## <a name="collection-classes-samples"></a>Örnekleri koleksiyon sınıfları

Aşağıdaki örnekler, koleksiyon sınıfları göstermektedir:

- [MMXSwarm örnek](../visual-cpp-samples.md)

- [DynamicConsumer örnek](../visual-cpp-samples.md)

- [Oluşturma](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV)

- [Kayan örnek](../visual-cpp-samples.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Kavramları](../atl/active-template-library-atl-concepts.md)   
[Koleksiyon Sınıfları](../atl/collection-classes.md)

