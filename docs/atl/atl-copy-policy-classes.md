---
title: ATL kopyalama İlkesi sınıfları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- data [C++], ATL
- classes [C++], copy policy
- copy policy classes [C++]
- _Copy class
- _CopyInterface class
ms.assetid: 06704b68-d318-4c5d-a65b-71457fe9d00d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 34b9ed5dca45633a5ab980d38b8a7cda151f5dc7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="atl-copy-policy-classes"></a>ATL kopyalama İlkesi sınıfları
Kopya İlkesi sınıflardır [yardımcı sınıflar](../atl/utility-classes.md) başlatmak için kullanılan, kopyalamak ve verileri silme. Kopya İlkesi sınıflar, herhangi bir veri türü için Kopyalama Semantiğini tanımlayın ve farklı veri türleri arasında dönüştürmeler tanımlamak için izin verir.  
  
 ATL kullanır kopyalama İlkesi sınıfları aşağıdaki şablonlardan birini kendi uygulamalarında:  
  
-   [CComEnumImpl](../atl/reference/ccomenumimpl-class.md)  
  
-   [IEnumOnSTLImpl](../atl/reference/ienumonstlimpl-class.md)  
  
-   [ICollectionOnSTLImpl](../atl/reference/icollectiononstlimpl-class.md)  
  
 Kopyalama veya kopya İlkesi sınıfında şablon bağımsız değişken geçirilen verileri dönüştürmek için gereken bilgileri kapsülleyerek ATL geliştiriciler için bu sınıfların aşırı yeniden kullanılırlığı sağlıyordu. Örneğin, herhangi bir rastgele veri türü kullanan bir koleksiyon uygulamanız gerekiyorsa, sağlamanız gereken tek şey uygun kopyalama İlkesi; hiçbir zaman koleksiyon uygulayan kod touch gerek yoktur.  
  
## <a name="definition"></a>Tanım  
 Tanımı gereği, aşağıdaki statik işlevler sağlayan bir sınıf bir kopya İlkesi sınıfıdır:  
  
 `static void init(` `DestinationType` `* p);`  
  
 `static HRESULT copy(` `DestinationType` `* pTo, const`  `SourceType` `* pFrom);`  
  
 `static void destroy(` `DestinationType` `* p);`  
  
 Türlerini değiştirecek `DestinationType` ve *kaynak türü* her kopya ilkesi için rasgele veri türlerine sahip.  
  
> [!NOTE]
>  Kopyalama İlkesi sınıfları herhangi rastgele veri türleri için tanımlayabilirsiniz rağmen ATL kodu sınıflarda kullanımını anlamlı türleri sınırlamanız gerekir. Örneğin, ne zaman bir kopya İlkesi'ni kullanarak sınıfı ATL'ın koleksiyonu veya numaralandırıcı uygulamaları ile `DestinationType` COM arabirimi yöntemi bir parametresi olarak kullanılan bir türü olmalıdır.  
  
 Kullanım **init** veri başlatmak için **kopya** veri kopyalamak için ve **destroy** verileri boşaltmak için. Başlatma kesin anlamını, kopyalama ve yok etme kopyalama İlkesi sınıfının etki alanı ve söz konusu veri türlerine bağlı olarak değişir.  
  
 Kullanım ve bir kopya İlkesi sınıf uyarlamasını iki gereksinimleri şunlardır:  
  
-   İlk parametre olarak **kopya** kullanarak daha önce başlatılmış veri için bir işaretçi yalnızca almalıdır **init**.  
  
-   **Destroy** kullanarak daha önce başlatılmış veri için bir işaretçi her zaman sadece almalıdır **init** veya aracılığıyla kopyalanan **kopya**.  
  
## <a name="standard-implementations"></a>Standart uygulamalar  
 ATL şeklinde iki kopya İlkesi sınıflar sağlar **_Copy** ve **_CopyInterface** şablon sınıfları:  
  
-   **_Copy** sınıfı yalnızca kopyalama homojen verir (değil veri türleri arasında dönüştürme) hem de belirtmek için tek bir şablon parametresi yalnızca sunar beri `DestinationType` ve *kaynak türü*. Bu şablon genel uygulamasını hiçbir başlatılması veya yok etme kodunu içerir ve kullanır `memcpy` verileri kopyalamak için. ATL de sağlar, özelleştirmeleri **_Copy** için **değişken**, `LPOLESTR`, **OLEVERB**, ve **CONNECTDATA** veri türleri.  
  
-   **_CopyInterface** sınıfı, standart COM kurallar aşağıdaki arabirim işaretçileri kopyalamak için bir uygulama sağlar. Basit atama ve yapılan bir çağrı kullanan bir kez daha bu sınıf yalnızca homojen kopyalama, sağladığından `AddRef` kopyalama işlemini gerçekleştirmek için.  
  
## <a name="custom-implementations"></a>Özel uygulamalar  
 Genellikle, heterojen (diğer bir deyişle, veri türleri arasında dönüştürme) kopyalamak için kendi kopya İlkesi sınıflarının tanımlanması gerekir. VCUE_Copy.h ve VCUE_CopyString.h içindeki dosyaları için bazı örnekler özel kopyalama İlkesi sınıfların bakmak [ATLCollections](../visual-cpp-samples.md) örnek. İki şablon kopyalama İlkesi sınıfları, bu dosyaları içeren `GenericCopy` ve `MapCopy`, özelleştirmeleri sayısı artı `GenericCopy` farklı veri türleri için.  
  
### <a name="genericcopy"></a>GenericCopy  
 `GenericCopy` belirtmenize olanak tanır *kaynak türü* ve `DestinationType` şablon bağımsız değişken. En genel biçiminde işte `GenericCopy` VCUE_Copy.h sınıfından:  
  
 [!code-cpp[NVC_ATL_COM#30](../atl/codesnippet/cpp/atl-copy-policy-classes_1.h)]  
  
 VCUE_Copy.h Ayrıca, bu sınıfın aşağıdaki özelleştirmeleri içerir: `GenericCopy<BSTR>`, `GenericCopy<VARIANT, BSTR>`, `GenericCopy<BSTR, VARIANT>`. VCUE_CopyString.h kopyalama için özelleştirmeleri içeren **std::string**s: `GenericCopy<std::string>`, `GenericCopy<VARIANT, std::string>`, ve `GenericCopy<BSTR, std::string>`. Artırabilecek `GenericCopy` kendi özelleştirmeleri başka sağlayarak.  
  
### <a name="mapcopy"></a>MapCopy  
 `MapCopy` veriler depolanır ve hedef türü harita türünü belirtmenize olanak tanır şekilde kopyalanan verileri bir C++ Standart Kitaplığı stili eşlemeye saklandığı varsayılır. Sınıfının uygulama tarafından sağlanan tür tanımları yalnızca kullanır *MapType* sınıfı kaynak veri türünü belirlemek ve uygun çağırmak için `GenericCopy` sınıfı. Bu sınıfın hiçbir özelleştirmeleri gereklidir.  
  
 [!code-cpp[NVC_ATL_COM#31](../atl/codesnippet/cpp/atl-copy-policy-classes_2.h)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart Kitaplığı tabanlı bir koleksiyon uygulama](../atl/implementing-an-stl-based-collection.md)   
 [ATLCollections örnek](../visual-cpp-samples.md)

