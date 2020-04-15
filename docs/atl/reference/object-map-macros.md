---
title: Nesne İşleme Makroları
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::DECLARE_OBJECT_DESCRIPTION
- atlcom/ATL::OBJECT_ENTRY_AUTO
- atlcom/ATL::OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO
ms.assetid: 680087f4-9894-41dd-a79c-6f337e1f13c1
ms.openlocfilehash: 66a418019ba506a5832c8e3ad86a3764c1186df0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326210"
---
# <a name="object-map-macros"></a>Nesne İşleme Makroları

Bu makrolar nesne eşlemlerini ve girişleri tanımlar.

|||
|-|-|
|[DECLARE_OBJECT_DESCRIPTION](#declare_object_description)|Nesne eşlemasına girilecek bir sınıf nesnesinin metin açıklamasını belirtmenizi sağlar.|
|[OBJECT_ENTRY_AUTO](#object_entry_auto)|Nesne eşlenine bir ATL nesnesi girer, kayıt defterini güncelleştirir ve nesnenin bir örneğini oluşturur.|
|[OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](#object_entry_non_createable_ex_auto)|Nesnenin kaydedilmesi ve başlatılması gerektiğini belirtmenizi sağlar, ancak `CoCreateInstance`'dan dışa gıcırdatırılmamalıdır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="declare_object_description"></a><a name="declare_object_description"></a>DECLARE_OBJECT_DESCRIPTION

Sınıf nesneniz için metin açıklaması belirtmenizi sağlar.

```
DECLARE_OBJECT_DESCRIPTION( x )
```

### <a name="parameters"></a>Parametreler

*X*<br/>
[içinde] Sınıf nesnesinin açıklaması.

### <a name="remarks"></a>Açıklamalar

ATL bu açıklamayı [OBJECT_ENTRY_AUTO](#object_entry_auto) makro su yla nesne haritasına girer.

DECLARE_OBJECT_DESCRIPTION CComCoClass geçersiz kılmak için kullanabileceğiniz bir `GetObjectDescription` işlev [uygular::GetObjectDescription](ccomcoclass-class.md#getobjectdescription) yöntemi.

İşlev `GetObjectDescription` tarafından `IComponentRegistrar::GetComponents`çağrılır. `IComponentRegistrar`bir DLL'de tek tek bileşenleri kaydetmenize ve kaydetmenize olanak tanıyan bir Otomasyon arabirimidir. ATL Project Sihirbazı ile bir Bileşen Kayıt Defteri nesnesi `IComponentRegistrar` oluşturduğunuzda, sihirbaz arabirimi otomatik olarak uygular. `IComponentRegistrar`genellikle Microsoft Transaction Server tarafından kullanılır.

ATL Proje Sihirbazı hakkında daha fazla bilgi için, [ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)makalesine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#123](../../atl/codesnippet/cpp/object-map-macros_1.h)]

## <a name="object_entry_auto"></a><a name="object_entry_auto"></a>OBJECT_ENTRY_AUTO

Nesne eşlenine bir ATL nesnesi girer, kayıt defterini güncelleştirir ve nesnenin bir örneğini oluşturur.

```
OBJECT_ENTRY_AUTO( clsid, class )
```

### <a name="parameters"></a>Parametreler

*Clsıd*<br/>
[içinde] C++ sınıfı tarafından uygulanan bir COM sınıfının *CLSID'si.*

*sınıf*<br/>
[içinde] *Clsid*tarafından temsil edilen COM sınıfını uygulayan C++ sınıfının adı.

### <a name="remarks"></a>Açıklamalar

Nesne giriş makroları, bir sınıfın kaydı, başlatılması ve oluşturulması için destek sağlamak için projede genel kapsama yerleştirilir.

OBJECT_ENTRY_AUTO, bu nesne için oluşturucu sınıfının ve `CreateInstance` sınıf-fabrika oluşturucu sınıfıişlevlerinin işlev işaretçilerini otomatik olarak oluşturulan ATL nesne eşlemi'ne girer. [CAtlComModule::RegisterServer](catlcommodule-class.md#registerserver) çağrıldığında, nesne haritasındaki her nesne için sistem kayıt defterini güncelleştirir.

Aşağıdaki tabloda, nesne eşlemi'ne eklenen bilgilerin bu makronun ikinci parametresi olarak verilen sınıftan nasıl elde edildiği açıklanmaktadır.

|Bilgi için|Elde edilen|
|---------------------|-------------------|
|COM kaydı|[Kayıt Defteri Makroları](../../atl/reference/registry-macros.md)|
|Sınıf fabrika oluşturma|[Sınıf Fabrika Makroları](../../atl/reference/aggregation-and-class-factory-macros.md)|
|Örnek oluşturma|[Toplama Makroları](../../atl/reference/aggregation-and-class-factory-macros.md)|
|Bileşen kategori kaydı|[Kategori Makroları](../../atl/reference/category-macros.md)|
|Sınıf düzeyinde başlatma ve temizleme|[ObjectMain](ccomobjectrootex-class.md#objectmain)|

## <a name="object_entry_non_createable_ex_auto"></a><a name="object_entry_non_createable_ex_auto"></a>OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO

Nesnenin kaydedilmesi ve başlatılması gerektiğini belirtmenizi sağlar, ancak `CoCreateInstance`'dan dışa gıcırdatırılmamalıdır.

```
OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO( clsid, class )
```

### <a name="parameters"></a>Parametreler

*Clsıd*<br/>
[içinde] C++ sınıfı tarafından uygulanan bir COM sınıfının *CLSID'si.*

*sınıf*<br/>
[içinde] *Clsid*tarafından temsil edilen COM sınıfını uygulayan C++ sınıfının adı.

### <a name="remarks"></a>Açıklamalar

Nesne giriş makroları, bir sınıfın kaydı, başlatılması ve oluşturulması için destek sağlamak için projede genel kapsama yerleştirilir.

OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO bir nesnenin kaydedilmesi ve başlatılması gerektiğini [OBJECT_ENTRY_AUTO](#object_entry_auto) belirtmenizi sağlar (daha fazla bilgi için `CoCreateInstance`OBJECT_ENTRY_AUTO bakın), ancak 'dan gArtılanmamalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar](../../atl/reference/atl-macros.md)
