---
description: 'Daha fazla bilgi edinin: ATL koleksiyon sınıfları'
title: ATL koleksiyon sınıfına genel bakış
ms.date: 11/19/2018
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
ms.openlocfilehash: 32d9fe928024d82af7031fbbb8d88aba5e3eae31
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166089"
---
# <a name="atl-collection-classes"></a>ATL Koleksiyon Sınıfları

ATL, verileri depolamak ve bunlara erişmek için birçok sınıf sağlar. Kullanmaya karar vereceğiniz sınıf, aşağıdakiler dahil olmak üzere çeşitli faktörlere bağlıdır:

- Depolanacak veri miktarı

- Verilere erişirken verimlilik ve performans karşılaştırması

- Dizine veya anahtara göre verilere erişme özelliği

- Verilerin sıralanma biçimi

- Kişisel tercih

## <a name="small-collection-classes"></a>Küçük koleksiyon sınıfları

ATL, az sayıda nesne ile uğraşmakta aşağıdaki dizi sınıflarını sağlar. Ancak, bu sınıflar sınırlı ve ATL tarafından dahili olarak kullanılmak üzere tasarlanmıştır. Bunları programlarınızda kullanmanız önerilmez.

|Sınıf|Veri depolama türü|
|-----------|--------------------------|
|[CSimpleArray](../atl/reference/csimplearray-class.md)|Az sayıda nesne ile ilgilenirken bir dizi sınıfı uygular.|
|[CSimpleMap](../atl/reference/csimplemap-class.md)|Az sayıda nesne ile ilgilenirken bir eşleme sınıfı uygular.|

## <a name="general-purpose-collection-classes"></a>Genel Amaçlı koleksiyonu sınıfları

Takip sınıfları diziler, listeler ve haritalar uygular ve genel amaçlı toplama sınıfları olarak sağlanır:

|Sınıf|Veri depolama türü|
|-----------|--------------------------|
|[CAtlArray](../atl/reference/catlarray-class.md)|Bir dizi uygular.|
|[CAtlList](../atl/reference/catllist-class.md)|Bir liste uygular.|
|[CAtlMap](../atl/reference/catlmap-class.md)|Veriye anahtar veya değer tarafından başvurulabilen bir eşleme yapısı uygular.|
|[CRBMap](../atl/reference/crbmap-class.md)|Red-Black algoritmasını kullanarak bir eşleme yapısı uygular.|
|[CRBMultiMap](../atl/reference/crbmultimap-class.md)|Red-Black multimapping yapısı uygular.|

Bu sınıflar hata ayıklama yapılarında kullanıldığında birçok programlama hatasını yakalar, ancak performans için bu denetimler, perakende yapılarında gerçekleştirilmeyecektir.

## <a name="specialized-collection-classes"></a>Özel koleksiyon sınıfları

Bellek işaretçilerini ve arabirim işaretçilerini yönetmek için de daha özelleştirilmiş koleksiyon sınıfları sağlanır:

|Sınıf|Amaç|
|-----------|-------------|
|[CAutoPtrArray](../atl/reference/cautoptrarray-class.md)|Akıllı işaretçiler dizisi oluştururken yararlı yöntemler sağlar.|
|[CAutoPtrList](../atl/reference/cautoptrlist-class.md)|Akıllı işaretçiler listesi oluştururken yararlı yöntemler sağlar.|
|[CComUnkArray](../atl/reference/ccomunkarray-class.md)|`IUnknown`İşaretçileri depolar ve [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) şablon sınıfına parametre olarak kullanılmak üzere tasarlanmıştır.|
|[CHeapPtrList](../atl/reference/cheapptrlist-class.md)|Yığın işaretçileri listesi oluştururken yararlı yöntemler sağlar.|
|[CInterfaceArray](../atl/reference/cinterfacearray-class.md)|Bir COM arabirim işaretçileri dizisi oluştururken yararlı yöntemler sağlar.|
|[CInterfaceList](../atl/reference/cinterfacelist-class.md)|COM arabirim işaretçilerinin listesini oluştururken yararlı yöntemler sağlar.|

## <a name="choosing-a-collection-class"></a>Koleksiyon sınıfı seçme

Kullanılabilir koleksiyon sınıflarının her biri, aşağıdaki tabloda gösterildiği gibi farklı performans özellikleri sağlar.

- 2 ve 3. sütunlar her sınıfın sıralama ve erişim özelliklerini anlatmaktadır. Tabloda, "siparişli" terimi, öğelerin eklendiği ve silineceği sıranın koleksiyondaki sıralarını belirler; öğelerin içeriklerinin sıralandığı anlamına gelmez. "Dizinli" terimi, koleksiyondaki öğelerin tipik bir dizideki öğeler gibi bir tamsayı dizin tarafından alınamayacağını gösterir.

- 4 ve 5. sütunlar her sınıfın performansını anlatmaktadır. Koleksiyonda çok sayıda eklemeler gerektiren uygulamalarda, ekleme hızı özellikle önemli olabilir; diğer uygulamalar için, arama hızı daha önemli olabilir.

- Sütun 6 her şeklin yinelenen öğelere izin verip içermediğini açıklar.

- Belirli bir koleksiyon sınıfı işleminin performansı, işlemi tamamlaması için gereken süre ve koleksiyondaki öğe sayısı arasındaki ilişki açısından ifade edilir. Öğe sayısı arttıkça, bir O (n) algoritması olarak açıklanarak doğrusal bir süre artan bir işlem. Bunun aksine, öğe sayısı arttıkça daha az ve daha az bir zaman alan bir işlem, O (log n) algoritması olarak açıklanmaktadır. Bu nedenle, performans, O (log n) algoritmalarının, öğe sayısı arttıkça O (n) algoritmaların daha fazla ve daha fazlasını gerçekleştirmesini.

### <a name="collection-shape-features"></a>Koleksiyon şekli özellikleri

|Şekil|Sipariş edildi|Oluşturulmayacak|Ekle<br /><br /> öğesi|Aranan:<br /><br /> Belirtilen öğe|Yinele<br /><br /> öğeler|
|-----------|--------------|--------------|---------------------------|--------------------------------------|-----------------------------|
|Liste|Evet|Hayır|Hızlı (sabit zaman)|Yavaş O (n)|Evet|
|Dizi|Evet|By int (sabit zaman)|Son olarak, bu durumda sabit zaman ekleme haricinde yavaş O (n)|Yavaş O (n)|Evet|
|Harita|Hayır|Anahtara göre (sabit zaman)|Hızlı (sabit zaman)|Hızlı (sabit zaman)|Hayır (anahtar) Evet (değerler)|
|Red-Black eşleme|Evet (anahtara göre)|Anahtar O 'a göre (log n)|Hızlı O (log n)|Hızlı O (log n)|Hayır|
|Red-Black multimap|Evet (anahtara göre)|Anahtara (log n) göre (anahtar başına birden çok değer)|Hızlı O (log n)|Hızlı O (log n)|Evet (anahtar başına birden çok değer)|

## <a name="using-ctraits-objects"></a>Cnitelikler nesnelerini kullanma

ATL koleksiyon sınıfları çok çeşitli Kullanıcı tanımlı veri türlerini depolamak için kullanılabilir, karşılaştırmalar gibi önemli işlevleri geçersiz kılabilmek yararlı olabilir. Bu, Cnitelikler sınıfları kullanılarak elde edilir.

Cnitelikler sınıfları, MFC koleksiyon sınıfı yardımcı işlevleri ile benzerdir, ancak daha esnektir. daha fazla bilgi için bkz. [koleksiyon sınıfı Yardımcıları](../mfc/reference/collection-class-helpers.md) .

Koleksiyon sınıfınızı oluştururken, Cnitelikler sınıfı belirtme seçeneğiniz vardır. Bu sınıf, koleksiyon sınıfını oluşturan diğer yöntemler tarafından çağrıldığında karşılaştırmalar gibi işlemleri gerçekleştirecek kodu içerir. Örneğin, liste nesneniz kendi Kullanıcı tanımlı yapılarınızı içeriyorsa, yalnızca belirli üye değişkenlerini karşılaştırmak için eşitlik testini yeniden tanımlamak isteyebilirsiniz. Bu şekilde, list nesnesinin Find yöntemi daha kullanışlı bir şekilde çalışır.

## <a name="example"></a>Örnek

### <a name="code"></a>Kod

[!code-cpp[NVC_ATL_Utilities#112](../atl/codesnippet/cpp/atl-collection-classes_1.cpp)]

## <a name="comments"></a>Yorumlar

Cnitelikler sınıflarının bir listesi için bkz. [koleksiyon sınıfları](../atl/collection-classes.md).

Aşağıdaki diyagramda Cnitelikler sınıfları için sınıf hiyerarşisi gösterilmektedir.

![Koleksiyon sınıfları için nitelikler hiyerarşisi](../atl/media/vctraitscollectionclasseshierarchy.gif "Koleksiyon sınıfları için nitelikler hiyerarşisi")

## <a name="collection-classes-samples"></a>Koleksiyon sınıfları örnekleri

Aşağıdaki örnekler koleksiyon sınıflarını gösterir:

- [Mmxsısınma örneği](../overview/visual-cpp-samples.md)

- [DynamicConsumer örneği](../overview/visual-cpp-samples.md)

- [UpdatePV örneği](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV)

- [Kayan yazı örneği](../overview/visual-cpp-samples.md)

## <a name="see-also"></a>Ayrıca bkz.

[Kavramlar](../atl/active-template-library-atl-concepts.md)<br/>
[Koleksiyon sınıfları](../atl/collection-classes.md)
