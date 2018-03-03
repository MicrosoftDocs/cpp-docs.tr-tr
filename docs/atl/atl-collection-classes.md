---
title: "ATL koleksiyon sınıfları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 24b0fbdc5ab68319704fb59746862384198f232b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="atl-collection-classes"></a>ATL Koleksiyon Sınıfları
ATL depolamak ve verilere erişmek için birçok sınıflar sağlar. Kullanmaya karar hangi sınıfı gibi birkaç etkene bağlıdır:  
  
-   Depolanacak veri miktarını  
  
-   Verimlilik verilere erişilirken performans karşılaştırması  
  
-   Dizin veya anahtar veri erişim olanağı  
  
-   Verileri nasıl sıralı  
  
-   Kişisel tercihi  
  
## <a name="small-collection-classes"></a>Küçük koleksiyon sınıfları  
 ATL nesnelerinin küçük numaralarını postalarla aşağıdaki dizi sınıfları sağlar. Ancak, bu sınıfları sınırlı ve ATL tarafından dahili olarak kullanılmak üzere tasarlanmış Bunları, programlarda kullanmak önerilmez.  
  
|örneği|Veri depolama türü|  
|-----------|--------------------------|  
|[CSimpleArray](../atl/reference/csimplearray-class.md)|Küçük sayıda nesnelerin ilgilenmek için bir dizi sınıf uygular.|  
|[CSimpleMap](../atl/reference/csimplemap-class.md)|Küçük sayıda nesnelerin ilgilenmek için bir eşleme sınıf uygular.|  
  
## <a name="general-purpose-collection-classes"></a>Genel amaçlı koleksiyon sınıfları  
 İzleme sınıflarını diziler, listeler ve eşlemeler uygulamak ve genel amaçlı koleksiyon sınıfları sağlanır:  
  
|örneği|Veri depolama türü|  
|-----------|--------------------------|  
|[CAtlArray](../atl/reference/catlarray-class.md)|Bir dizi uygular.|  
|[CAtlList](../atl/reference/catllist-class.md)|Listesini uygular.|  
|[CAtlMap](../atl/reference/catlmap-class.md)|Anahtar veya değer tarafından veri yapabildiği başvurulabilir bir eşleme yapısı uygular.|  
|[CRBMap](../atl/reference/crbmap-class.md)|Kırmızı siyah algoritmasını kullanarak bir eşleme yapısı uygular.|  
|[CRBMultiMap](../atl/reference/crbmultimap-class.md)|Kırmızı siyah multimapping yapısı uygular.|  
  
 Bu sınıfların hata ayıklama derlemelerinde kullanıldığında pek çok programlama hataları yakalar, ancak performans for sake of perakende yapılarında bu denetimleri gerçekleştirilmez.  
  
## <a name="specialized-collection-classes"></a>Özel koleksiyon sınıfları  
 Daha fazla özel koleksiyon sınıfları bellek işaretçiler ve arabirim işaretçileri yönetmek için de sağlanır:  
  
|örneği|Amaç|  
|-----------|-------------|  
|[CAutoPtrArray](../atl/reference/cautoptrarray-class.md)|Akıllı işaretçiler bir dizi oluşturulurken kullanışlı yöntemler sağlar.|  
|[CAutoPtrList](../atl/reference/cautoptrlist-class.md)|Akıllı işaretçiler listesi oluşturulurken, kullanışlı yöntemler sağlar.|  
|[CComUnkArray](../atl/reference/ccomunkarray-class.md)|Depoları `IUnknown` işaretçiler ve parametre olarak kullanılmak üzere tasarlanmış [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) Şablon sınıfı.|  
|[CHeapPtrList](../atl/reference/cheapptrlist-class.md)|Yığın işaretçileri listesi oluşturulurken, kullanışlı yöntemler sağlar.|  
|[CInterfaceArray](../atl/reference/cinterfacearray-class.md)|Yöntemleri yararlı bir dizi COM arabirim işaretçileri oluşturulurken sağlar.|  
|[CInterfaceList](../atl/reference/cinterfacelist-class.md)|COM arabirim işaretçileri listesi oluşturulurken, kullanışlı yöntemler sağlar.|  
  
## <a name="choosing-a-collection-class"></a>Koleksiyon sınıfı seçme  
 Aşağıdaki tabloda gösterildiği gibi kullanılabilir koleksiyonu sınıfların her biri farklı performans özellikleri sunar.  
  
-   Sütun 2 ve 3 özelliklere erişmek ve her sınıfın sıralama açıklanmıştır. Tabloda "sipariş" terimi öğeleri eklenen ve Silinen sırasını koleksiyondaki sıralarına belirler anlamına gelir; öğeler içerikleri üzerinde sıralanır anlamına gelmez. "Dizin" terimi, koleksiyondaki öğelerin tipik bir dizi öğeleri benzer bir tamsayı dizini tarafından alınabilir anlamına gelir.  
  
-   Sütunları 4 ve 5 her sınıfın performans açıklanmaktadır. Koleksiyona birçok eklemeleri gerektiren uygulamalar içinde ekleme hızının özellikle önemli olabilir; diğer uygulamalar için arama hızı daha önemli olabilir.  
  
-   Sütun 6 her şekli yinelenen öğeler izin verip vermediğini açıklar.  
  
-   Verilen koleksiyon sınıfı işleminin performansı işlemi ve koleksiyondaki öğe sayısını tamamlamak için gereken süreyi arasındaki ilişkiyi cinsinden ifade edilir. Öğeleri artar sayısı O(n) algoritması olarak açıklandığı gibi bir zaman miktarı alma işlemi, doğrusal olarak artırır. Bunun aksine, daha az ve daha az öğeleri artar sayısı olarak artan bir süre alma işlemi O (günlük n) algoritması olarak tanımlanır. Bu nedenle, performans açısından, O (günlük n) algoritmaları O(n) algoritmaları öğeleri artar sayısı arttıkça daha da fazla daha iyi performans gösterir.  
  
### <a name="collection-shape-features"></a>Koleksiyonu şekli özellikleri  
  
|Şekil|sıralı|Dizin oluşturulmuş|INSERT bir<br /><br /> öğesi|Aranan:<br /><br /> Belirtilen öğe|Yinelenen<br /><br /> öğeler|  
|-----------|--------------|--------------|---------------------------|--------------------------------------|-----------------------------|  
|List|Evet|Hayır|Hızlı (sabit saati)|Yavaş O(n)|Evet|  
|Dizi|Evet|İnt tarafından (sabit saati)|Sonunda, büyük/küçük harfe hangi sabit zamanında ekleme varsa dışında yavaş O(n)|Yavaş O(n)|Evet|  
|eşleme|Hayır|Anahtarının (sabit saati)|Hızlı (sabit saati)|Hızlı (sabit saati)|Yok (anahtarlar) Evet (değerler)|  
|Kırmızı siyah eşleme|Evet (anahtar tarafından)|Anahtarının O (günlük n)|Hızlı O (günlük n)|Hızlı O (günlük n)|Hayır|  
|Kırmızı siyah Multimap|Evet (anahtar tarafından)|Anahtarının O(log n) (anahtar başına birden çok değer)|Hızlı O (günlük n)|Hızlı O (günlük n)|Evet (anahtar başına birden çok değer)|  
  
## <a name="using-ctraits-objects"></a>CTraits nesnelerini kullanma  
 ATL koleksiyon sınıfları çok çeşitli kullanıcı tanımlı veri türleri depolamak için kullanılan karşılaştırmaları gibi önemli işlevleri geçersiz kılma yapabilmek yararlı olabilir. Bu, CTraits sınıfları kullanılarak gerçekleştirilir.  
  
 CTraits sınıfları benzer, ancak daha esnektir, MFC koleksiyon sınıfı yardımcı işlevleri; bkz: [koleksiyon sınıfı Yardımcıları](../mfc/reference/collection-class-helpers.md) daha fazla bilgi için.  
  
 Koleksiyon sınıfı oluşturulurken CTraits sınıfı belirtme seçeneğiniz vardır. Bu sınıf koleksiyonu sınıfınızı diğer yöntemlerle çağrıldığında karşılaştırmaları gibi işlemleri yapar kodu içerir. Örneğin, kendi kullanıcı tanımlı yapıları listesi nesnenizin içeriyorsa, yalnızca belirli üye değişkenleri karşılaştırmak için eşitlik test yeniden tanımlamak isteyebilirsiniz. Bu şekilde, liste nesnesinin bulma yöntemini daha kullanışlı bir şekilde çalışır.  
  
## <a name="example"></a>Örnek  
  
### <a name="code"></a>Kod  
 [!code-cpp[NVC_ATL_Utilities#112](../atl/codesnippet/cpp/atl-collection-classes_1.cpp)]  
  
## <a name="comments"></a>Açıklamalar  
 CTraits sınıfları listesi için bkz: [koleksiyon sınıfları](../atl/collection-classes.md).  
  
 Aşağıdaki diyagramda CTraits sınıfları için sınıf hiyerarşisi gösterir.  
  
 ![Koleksiyon sınıfları karakter hiyerarşisi](../atl/media/vctraitscollectionclasseshierarchy.gif "vctraitscollectionclasseshierarchy")  
  
## <a name="collection-classes-samples"></a>Örnekleri koleksiyon sınıfları  
 Aşağıdaki örnekler, koleksiyon sınıfları göstermektedir:  
  
-   [MMXSwarm örnek](../visual-cpp-samples.md)  
  
-   [DynamicConsumer örnek](../visual-cpp-samples.md)  
  
-   [Oluşturma](../visual-cpp-samples.md)  
  
-   [Kayan örnek](../visual-cpp-samples.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kavramları](../atl/active-template-library-atl-concepts.md)   
 [Koleksiyon Sınıfları](../atl/collection-classes.md)

