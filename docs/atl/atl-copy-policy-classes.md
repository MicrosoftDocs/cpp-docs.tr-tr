---
title: ATL kopyalama İlkesi sınıfları
ms.date: 11/04/2016
helpviewer_keywords:
- data [C++], ATL
- classes [C++], copy policy
- copy policy classes [C++]
- _Copy class
- _CopyInterface class
ms.assetid: 06704b68-d318-4c5d-a65b-71457fe9d00d
ms.openlocfilehash: 535bd1a3129bab15f546f6a82d77cf4e152fc605
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50452760"
---
# <a name="atl-copy-policy-classes"></a>ATL kopyalama İlkesi sınıfları

Kopyalama İlkesi sınıfları [yardımcı sınıflar](../atl/utility-classes.md) başlatmak için kullanılan, kopyalayın ve verileri silin. Kopyalama İlkesi sınıfları herhangi bir veri türü için kopyalama semantiği tanımlamak için ve farklı veri türleri arasında dönüştürmeler tanımlamanızı sağlar.

Aşağıdaki şablonlar, kendi uygulamalarında ATL kullanan kopyalama İlkesi sınıfları:

- [CComEnumImpl](../atl/reference/ccomenumimpl-class.md)

- [Ienumonstlımpl](../atl/reference/ienumonstlimpl-class.md)

- [Icollectiononstlımpl](../atl/reference/icollectiononstlimpl-class.md)

Kopyalayın veya şablon bağımsız değişken geçirilebilen kopyalama İlkesi sınıfında verileri dönüştürmek için gereken bilgileri kapsülleyerek ATL geliştiriciler bu sınıfların aşırı ölçeklendirilebileceği için sağlanmıştır. Örneğin, herhangi bir rastgele veri türü kullanan bir koleksiyon uygulamanız gerekiyorsa, sağlamak için ihtiyacınız olan uygun kopyalama İlkesi; hiçbir zaman koleksiyon uygulayan kod touch gerekir.

## <a name="definition"></a>Tanım

Tanımı gereği, aşağıdaki statik işlevler sağlayan bir sınıf bir kopya ilke sınıfıdır:

`static void init(` `DestinationType` `* p);`

`static HRESULT copy(` `DestinationType` `* pTo, const`  `SourceType` `* pFrom);`

`static void destroy(` `DestinationType` `* p);`

Türlerini değiştirebilirsiniz `DestinationType` ve *SourceType* her kopya ilke için rastgele veri türleriyle.

> [!NOTE]
>  Herhangi bir rastgele veri türleri için kopyalama İlkesi sınıfları tanımlayabilirsiniz, ATL kodu kullanıldığında artık sınıflarda kullanımını mantıklı türleri sınırlamanız gerekir. Örneğin, ne zaman bir kopyalama İlkesi'ni kullanarak sınıf ATL'nin koleksiyonu veya numaralandırıcı uygulamaları ile `DestinationType` bir COM arabirimi yöntemini bir parametre olarak kullanılan bir tür olmalıdır.

Kullanım **init** verilerini başlatmak için **kopyalama** veri kopyalamak ve **yok** verileri boşaltmak için. Başlatma tam anlamı, kopyalama ve yok etme kopyalama İlkesi sınıfın etki ve söz konusu veri türlerine bağlı olarak farklılık gösterir.

Kullanım ve kopyalama İlkesi sınıfı uygulaması iki gereksinim bulunur:

- İlk parametre olarak **kopyalama** yalnızca bir işaretçi kullanarak daha önce başlatılmış veri alması gerekir **init**.

- **Destroy** her zaman sadece bir işaretçi kullanarak daha önce başlatılmış veri alması gerekir **init** veya aracılığıyla kopyalanan **kopyalama**.

## <a name="standard-implementations"></a>Standart uygulamalar

ATL şeklinde iki kopyalama İlkesi sınıfları sağlar `_Copy` ve `_CopyInterface` şablon sınıfları:

- `_Copy` Sınıfı yalnızca kopyalama homojen sağlar (değil veri türleri arasında dönüştürme) hem de belirtmek için tek bir şablon parametresi yalnızca sunduğu bu yana `DestinationType` ve *SourceType*. Bu şablon, genel uygulama, başlatma veya yok etme hiçbir kod içermiyor ve kullanır `memcpy` verileri kopyalamak için. ATL ayrıca uzmanlıkları sağlar `_Copy` değişken, LPOLESTR OLEVERB ve CONNECTDATA veri türleri için.

- `_CopyInterface` Sınıf, arabirim işaretçilerini standart COM kuralları aşağıdaki kopyalama uygulanmasını sağlar. Basit atama ve çağrı kullanması için yine bu sınıf sadece homojen kopyalama, sağlar `AddRef` kopyalama işlemini gerçekleştirmek için.

## <a name="custom-implementations"></a>Özel uygulamalar

Genellikle, heterojen (diğer bir deyişle, veri türleri arasında dönüştürme) kopyalamak için kendi kopyalama İlkesi sınıfları tanımlamanız gerekir. Özel kopyalama İlkesi sınıfları bazı örnekler için VCUE_Copy.h ve VCUE_CopyString.h içinde dosyaları bakın [ATLCollections](../visual-cpp-samples.md) örnek. İki şablon kopyalama İlkesi sınıfları, bu dosyaları içeren `GenericCopy` ve `MapCopy`, uzmanlıkları sayısı artı `GenericCopy` farklı veri türleri için.

### <a name="genericcopy"></a>GenericCopy

`GenericCopy` belirtmenize olanak tanır *SourceType* ve `DestinationType` şablon bağımsız değişkenleri olarak. En genel formu şöyledir `GenericCopy` VCUE_Copy.h sınıfı:

[!code-cpp[NVC_ATL_COM#30](../atl/codesnippet/cpp/atl-copy-policy-classes_1.h)]

VCUE_Copy.h Ayrıca bu sınıf aşağıdaki uzmanlıklarını içerir: `GenericCopy<BSTR>`, `GenericCopy<VARIANT, BSTR>`, `GenericCopy<BSTR, VARIANT>`. VCUE_CopyString.h içeren kopyalama için uzmanlıkları **std::string**s: `GenericCopy<std::string>`, `GenericCopy<VARIANT, std::string>`, ve `GenericCopy<BSTR, std::string>`. Artırabilecek `GenericCopy` kendi uzmanlıkları daha sağlayarak.

### <a name="mapcopy"></a>MapCopy

`MapCopy` Kopyalanan verileri böylece veriler depolanır ve hedef türü eşleme türü belirtmenizi sağlar bir C++ Standart Kitaplığı stili eşlemeye depolandığını varsayar. Sınıfın uygulaması tarafından sağlanan tür tanımları yalnızca kullandığı *MapType* sınıf kaynak verilerin türünü belirlemeye ve uygun çağrılacak `GenericCopy` sınıfı. Bu sınıfın yok uzmanlıkları gereklidir.

[!code-cpp[NVC_ATL_COM#31](../atl/codesnippet/cpp/atl-copy-policy-classes_2.h)]

## <a name="see-also"></a>Ayrıca Bkz.

[C++ Standart Kitaplığı Temelli Koleksiyon Uygulama](../atl/implementing-an-stl-based-collection.md)<br/>
[ATLCollections örnek](../visual-cpp-samples.md)

