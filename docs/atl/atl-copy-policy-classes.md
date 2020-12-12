---
description: 'Daha fazla bilgi edinin: ATL kopyalama Ilkesi sınıfları'
title: ATL kopyalama Ilkesi sınıfları
ms.date: 11/04/2016
helpviewer_keywords:
- data [C++], ATL
- classes [C++], copy policy
- copy policy classes [C++]
- _Copy class
- _CopyInterface class
ms.assetid: 06704b68-d318-4c5d-a65b-71457fe9d00d
ms.openlocfilehash: 502befadbd9317602c49d9a5815dee6ebc239d78
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165764"
---
# <a name="atl-copy-policy-classes"></a>ATL kopyalama Ilkesi sınıfları

İlke sınıflarını Kopyala, verileri başlatmak, kopyalamak ve silmek için kullanılan [yardımcı program sınıflarıdır](../atl/utility-classes.md) . İlke sınıflarını kopyalama, herhangi bir veri türü için kopyalama semantiğini tanımlamanızı ve farklı veri türleri arasında dönüştürmeler tanımlamanızı sağlar.

ATL, aşağıdaki şablonların uygulamalarında ilke sınıflarını Kopyala kullanır:

- [CComEnumImpl](../atl/reference/ccomenumimpl-class.md)

- [IEnumOnSTLImpl](../atl/reference/ienumonstlimpl-class.md)

- [ICollectionOnSTLImpl](../atl/reference/icollectiononstlimpl-class.md)

Bir şablon bağımsız değişkeni olarak geçirilebilecek bir kopyalama ilkesi sınıfındaki verileri kopyalamak veya dönüştürmek için gereken bilgileri kapsülleyerek, ATL geliştiricileri bu sınıfların çok fazla yeniden kullanılabilirliği için sağlanmış olur. Örneğin, herhangi bir rastgele veri türünü kullanarak bir koleksiyon uygulamanız gerekiyorsa, uygun kopyalama ilkesi sağlamanız gerekir; koleksiyonu uygulayan koda dokunmanız gerekmez.

## <a name="definition"></a>Tanım

Tanım olarak, aşağıdaki statik işlevleri sağlayan bir sınıf kopyalama ilkesi sınıfıdır:

`static void init(` `DestinationType` `* p);`

`static HRESULT copy(` `DestinationType` `* pTo, const`  `SourceType` `* pFrom);`

`static void destroy(` `DestinationType` `* p);`

Türleri `DestinationType` ve *SourceType* her kopyalama ilkesi için rastgele veri türleriyle değiştirebilirsiniz.

> [!NOTE]
> Herhangi bir rastgele veri türü için kopyalama ilkesi sınıfları tanımlayabilseniz de, ATL kodundaki sınıfların kullanımı, anlamlı olan türleri sınırlandırmalıdır. Örneğin, ATL koleksiyonu veya Numaralandırıcı uygulamalarıyla bir kopyalama ilkesi sınıfı kullanırken bir `DestinationType` com arabirimi yönteminde parametre olarak kullanılabilecek bir tür olmalıdır.

Verileri başlatmak için **Init** kullanın, verileri kopyalamak için **kopyalayın** ve **yok** edin. Başlatmanın, kopyalamanın ve yok edilmesiyle ilgili kesin anlamı, kopyalama ilkesi sınıfının etki alanıdır ve dahil edilen veri türlerine bağlı olarak değişir.

Bir kopyalama ilkesi sınıfının kullanımı ve uygulanması üzerinde iki gereksinim vardır:

- **Kopyalamanın** ilk parametresi yalnızca, **init** kullanarak daha önce oluşturduğunuz verilere yönelik bir işaretçi almalıdır.

- **yok etme** yalnızca daha önce **başlatılmış veya** **kopya** aracılığıyla kopyalanmış olan veriler için bir işaretçi almalıdır.

## <a name="standard-implementations"></a>Standart uygulamalar

ATL, `_Copy` ve şablon sınıfları biçiminde iki kopyalama ilkesi sınıfı sağlar `_CopyInterface` :

- `_Copy`Sınıfı yalnızca hem hem de SourceType belirtmek için tek bir şablon parametresi sağladığından, yalnızca homomojen (veri türleri arasında dönüştürme değil) kopyalama yapılmasına izin verir `DestinationType` .  Bu şablonun genel uygulanması, başlatma veya yok etme kodu içermez ve `memcpy` verileri kopyalamak için kullanır. ATL Ayrıca `_Copy` , VARIANT, LPOPASTR, OLEVERB ve CONNECTDATA veri türleri için de Uzmanlıklar sağlar.

- `_CopyInterface`Sınıfı, standart com kurallarından sonraki arabirim işaretçilerini kopyalamak için bir uygulama sağlar. Bu sınıf, bir kez daha yalnızca homojen olarak kopyalanmaya izin veriyorsa, bu nedenle basit atama ve `AddRef` kopyayı gerçekleştirmek için çağrısı kullanır.

## <a name="custom-implementations"></a>Özel uygulamalar

Genellikle, heterojen kopyalama için kendi kopyalama ilkesi sınıflarınızı tanımlamanız gerekir (diğer bir deyişle, veri türleri arasında dönüştürme). Özel kopyalama ilkesi sınıflarının bazı örnekleri için, [ATLCollections](../overview/visual-cpp-samples.md) örneğindeki VCUE_Copy. h ve VCUE_CopyString. h dosyalarına bakın. Bu dosyalar, iki şablon kopyalama ilkesi sınıfını `GenericCopy` ve `MapCopy` Ayrıca `GenericCopy` farklı veri türleri için bir dizi uzmanlığını içerir.

### <a name="genericcopy"></a>GenericCopy

`GenericCopy`*SourceType* ve `DestinationType` as şablon bağımsız değişkenlerini belirtmenize olanak tanır. Aşağıda `GenericCopy` VCUE_Copy. h sınıfının en genel formu verilmiştir:

[!code-cpp[NVC_ATL_COM#30](../atl/codesnippet/cpp/atl-copy-policy-classes_1.h)]

VCUE_Copy. h bu sınıfın şu özelleştirmelerini de içerir: `GenericCopy<BSTR>` , `GenericCopy<VARIANT, BSTR>` , `GenericCopy<BSTR, VARIANT>` . VCUE_CopyString. h, **std:: String** s:, ve ' den kopyalamaya yönelik uzmanlık özelliklerini içerir `GenericCopy<std::string>` `GenericCopy<VARIANT, std::string>` `GenericCopy<BSTR, std::string>` . `GenericCopy`Kendi uzmanlarınızı daha ayrıntılı olarak sunarak geliştirebilirsiniz.

### <a name="mapcopy"></a>MapCopy

`MapCopy` kopyalandığı verilerin bir C++ standart kitaplık stili haritasında depolandığını varsayar, bu nedenle verilerin depolandığı haritanın türünü ve hedef türünü belirtmenize olanak tanır. Sınıfının uygulanması, kaynak verilerin türünü ve uygun sınıfı çağırmak için yalnızca *MapType* sınıfı tarafından sağlanan tür tanımları öğesini kullanır `GenericCopy` . Bu sınıfın herhangi bir özelleştirilmiş olması gerekmez.

[!code-cpp[NVC_ATL_COM#31](../atl/codesnippet/cpp/atl-copy-policy-classes_2.h)]

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart Library-Based koleksiyonu uygulama](../atl/implementing-an-stl-based-collection.md)<br/>
[ATLCollections örneği](../overview/visual-cpp-samples.md)
