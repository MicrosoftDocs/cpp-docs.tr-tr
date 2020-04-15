---
title: ATL Kopyalama İlkesi Sınıfları
ms.date: 11/04/2016
helpviewer_keywords:
- data [C++], ATL
- classes [C++], copy policy
- copy policy classes [C++]
- _Copy class
- _CopyInterface class
ms.assetid: 06704b68-d318-4c5d-a65b-71457fe9d00d
ms.openlocfilehash: f40f31124d4547076249a7459ac4b63cc25305d1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317387"
---
# <a name="atl-copy-policy-classes"></a>ATL Kopyalama İlkesi Sınıfları

Kopyalama ilkesi sınıfları, verileri başlatma, kopyalama ve silme için kullanılan [yardımcı program sınıflarıdır.](../atl/utility-classes.md) İlke kopyalama sınıfları, herhangi bir veri türü için kopya semantiklerini tanımlamanıza ve farklı veri türleri arasındaki dönüşümleri tanımlamanıza olanak sağlar.

ATL, aşağıdaki şablonların uygulamalarında kopyalama ilkesi sınıflarını kullanır:

- [CComEnumImpl](../atl/reference/ccomenumimpl-class.md)

- [IEnumOnSTLImpl](../atl/reference/ienumonstlimpl-class.md)

- [ıcollectiononstlımpl](../atl/reference/icollectiononstlimpl-class.md)

ATL geliştiricileri, şablon bağımsız değişkeni olarak geçirilebilen bir kopya ilkesi sınıfında verileri kopyalamak veya dönüştürmek için gereken bilgileri kapsülleyerek, bu sınıfların aşırı yeniden kullanılabilirliği sağlar. Örneğin, herhangi bir rasgele veri türünü kullanarak bir koleksiyon uygulamanız gerekiyorsa, sağlamanız gereken tek şey uygun kopyalama ilkesidir; koleksiyonu uygulayan koda dokunmak zorunda kalmamak gerekir.

## <a name="definition"></a>Tanım

Tanım olarak, aşağıdaki statik işlevleri sağlayan bir sınıf bir kopya ilkesi sınıfıdır:

`static void init(` `DestinationType` `* p);`

`static HRESULT copy(` `DestinationType` `* pTo, const`  `SourceType` `* pFrom);`

`static void destroy(` `DestinationType` `* p);`

Türleri `DestinationType` ve *SourceType'ı* her kopyalama ilkesi için rasgele veri türleri ile değiştirebilirsiniz.

> [!NOTE]
> Herhangi bir rasgele veri türleri için kopya ilkesi sınıfları tanımlayabilirsiniz rağmen, ATL kodunda sınıfların kullanımı anlamlı türleri sınırlamak gerekir. Örneğin, ATL'nin koleksiyonu veya numaralandırıcı uygulamaları olan bir kopya ilkesi `DestinationType` sınıfı kullanırken, COM arabirimi yönteminde parametre olarak kullanılabilecek bir tür olmalıdır.

Verileri **başlatma,** verileri kopyalamak ve verileri serbest leştirmek için **yok** etmek için **init'i** kullanın. Başlatma, kopyalama ve imhanın kesin anlamı kopyalama ilkesi sınıfının etki alanıdır ve ilgili veri türlerine bağlı olarak değişir.

Kopyalama ilkesi sınıfının kullanımı ve uygulanması yla ilgili iki gereksinim vardır:

- Kopyalanması gereken **copy** ilk parametre yalnızca **init'i**kullanarak daha önce başharfe başlattığınız verilere işaretçi saolmalıdır.

- **yok etme** yalnızca daha önce **init** kullanarak veya **kopya**yoluyla kopyalanmış verileri için bir işaretçi almak gerekir.

## <a name="standard-implementations"></a>Standart Uygulamalar

`_Copy` ATL, şablon `_CopyInterface` sınıfları biçiminde iki kopya ilkesi sınıfı sağlar:

- Sınıf `_Copy` homojen kopyalamaya izin verir (veri türleri arasında dönüştürme değil) çünkü yalnızca `DestinationType` hem de *SourceType'ı*belirtmek için tek bir şablon parametresi sunar. Bu şablonun genel uygulaması hiçbir başlatma veya `memcpy` imha kodu içerir ve verileri kopyalamak için kullanır. ATL ayrıca VARIANT, `_Copy` LPOLESTR, OLEVERB ve CONNECTDATA veri türleri için uzmanlık sağlar.

- Sınıf, `_CopyInterface` arabirim işaretçilerini standart COM kurallarına göre kopyalamak için bir uygulama sağlar. Bir kez daha bu sınıf sadece homojen kopyalama sağlar, bu `AddRef` yüzden basit atama ve kopya gerçekleştirmek için bir çağrı kullanır.

## <a name="custom-implementations"></a>Özel Uygulamalar

Tipik olarak, heterojen kopyalama (diğer bir süre önce veri türleri arasında dönüştürme) için kendi kopya ilkesi sınıflarınızı tanımlamanız gerekir. Özel kopyalama ilkesi sınıflarına örnek olarak, [ATLCollections](../overview/visual-cpp-samples.md) örneğindeki VCUE_Copy.h ve VCUE_CopyString.h dosyalarına bakın. Bu dosyalar iki şablon kopyalama `GenericCopy` `MapCopy`ilkesi sınıfı ve farklı veri `GenericCopy` türleri için uzmanlık lar içerir.

### <a name="genericcopy"></a>Genericcopy

`GenericCopy`*SourceType* ve `DestinationType` şablon bağımsız değişkenleri olarak belirtmenizi sağlar. İşte VCUE_Copy.h sınıfının `GenericCopy` en genel şekli:

[!code-cpp[NVC_ATL_COM#30](../atl/codesnippet/cpp/atl-copy-policy-classes_1.h)]

VCUE_Copy.h ayrıca bu sınıfın aşağıdaki uzmanlıklarını `GenericCopy<BSTR>` `GenericCopy<VARIANT, BSTR>`içerir: , , `GenericCopy<BSTR, VARIANT>`. VCUE_CopyString.h std kopyalama için uzmanlıklar **içerir::string** `GenericCopy<std::string>` `GenericCopy<VARIANT, std::string>`s: `GenericCopy<BSTR, std::string>`, , ve . Kendi uzmanlıkdaha sağlayarak artırabilir. `GenericCopy`

### <a name="mapcopy"></a>Harita fotokopisi

`MapCopy`kopyalanan verilerin C++ Standart Kitaplık stili nde bir haritada depolandığını varsayar, bu nedenle verilerin depolandığı harita türünü ve hedef türünü belirtmenize olanak tanır. Sınıfın uygulanması, kaynak verilerin türünü belirlemek ve uygun `GenericCopy` sınıfı aramak için *MapType* sınıfı tarafından sağlanan typedefs kullanır. Bu sınıfın uzmanlıklarına gerek yoktur.

[!code-cpp[NVC_ATL_COM#31](../atl/codesnippet/cpp/atl-copy-policy-classes_2.h)]

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplık Tabanlı Koleksiyonu Uygulama](../atl/implementing-an-stl-based-collection.md)<br/>
[ATLCollections Örnek](../overview/visual-cpp-samples.md)
