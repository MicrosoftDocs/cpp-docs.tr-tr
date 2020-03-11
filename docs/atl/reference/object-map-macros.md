---
title: Nesne Haritası makroları
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::DECLARE_OBJECT_DESCRIPTION
- atlcom/ATL::OBJECT_ENTRY_AUTO
- atlcom/ATL::OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO
ms.assetid: 680087f4-9894-41dd-a79c-6f337e1f13c1
ms.openlocfilehash: 73dc924527bac8499adefab3d0d6b51afa500a5a
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78863248"
---
# <a name="object-map-macros"></a>Nesne Haritası makroları

Bu makrolar nesne haritaları ve girdilerini tanımlar.

|||
|-|-|
|[DECLARE_OBJECT_DESCRIPTION](#declare_object_description)|Nesne haritasına girilecek bir sınıf nesnesinin metin açıklamasını belirtmenize olanak tanır.|
|[OBJECT_ENTRY_AUTO](#object_entry_auto)|Nesne haritasına bir ATL nesnesi girer, kayıt defterini güncelleştirir ve nesnesinin bir örneğini oluşturur.|
|[OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](#object_entry_non_createable_ex_auto)|Nesnenin kaydedilip başlatılmış olması gerektiğini belirtmenize izin verir, ancak `CoCreateInstance`aracılığıyla dışarıdan oluşturulabilmelidir.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

##  <a name="declare_object_description"></a>DECLARE_OBJECT_DESCRIPTION

Sınıf nesneniz için bir metin açıklaması belirtmenize olanak tanır.

```
DECLARE_OBJECT_DESCRIPTION( x )
```

### <a name="parameters"></a>Parametreler

*sayı*<br/>
'ndaki Sınıf nesnesinin açıklaması.

### <a name="remarks"></a>Açıklamalar

ATL, [OBJECT_ENTRY_AUTO](#object_entry_auto) makrosu aracılığıyla nesne haritasına bu açıklamayı girer.

DECLARE_OBJECT_DESCRIPTION, [CComCoClass:: GetObjectDescription](ccomcoclass-class.md#getobjectdescription) metodunu geçersiz kılmak için kullanabileceğiniz bir `GetObjectDescription` işlevi uygular.

`GetObjectDescription` işlevi `IComponentRegistrar::GetComponents`tarafından çağrılır. `IComponentRegistrar`, bir DLL 'deki tek tek bileşenleri kaydetmenize ve kaydını kaldırmanıza olanak tanıyan bir Otomasyon arabirimidir. ATL Proje sihirbazıyla bir bileşen kaydedici nesnesi oluşturduğunuzda, sihirbaz `IComponentRegistrar` arabirimini otomatik olarak uygular. `IComponentRegistrar` genellikle Microsoft Transaction Server tarafından kullanılır.

ATL Proje Sihirbazı hakkında daha fazla bilgi için, [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)makalesine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#123](../../atl/codesnippet/cpp/object-map-macros_1.h)]

##  <a name="object_entry_auto"></a>OBJECT_ENTRY_AUTO

Nesne haritasına bir ATL nesnesi girer, kayıt defterini güncelleştirir ve nesnesinin bir örneğini oluşturur.

```
OBJECT_ENTRY_AUTO( clsid, class )
```

### <a name="parameters"></a>Parametreler

*in*<br/>
'ndaki C++ *Sınıf adlı sınıf*tarafından uygulanan com sınıfının CLSID değeri.

*class*<br/>
'ndaki *CLSID*tarafından temsıl edilen C++ com sınıfını uygulayan sınıfın adı.

### <a name="remarks"></a>Açıklamalar

Nesne girişi makroları, bir sınıfın kaydı, başlatılması ve oluşturulması için destek sağlamak üzere projedeki genel kapsama yerleştirilir.

OBJECT_ENTRY_AUTO, otomatik olarak oluşturulan ATL nesne haritasına bu nesne için oluşturan sınıf ve sınıf fabrikası Oluşturucu sınıfı `CreateInstance` işlevlerinin işlev işaretçilerini girer. [CAtlComModule:: RegisterServer](catlcommodule-class.md#registerserver) çağrıldığında, nesne eşlemesindeki her bir nesne için sistem kayıt defterini güncelleştirir.

Aşağıdaki tabloda, nesne haritasına eklenen bilgilerin, bu makroya ikinci parametre olarak verilen sınıftan elde edilen bilgileri açıklanmaktadır.

|İçin bilgiler|Alındığı yer|
|---------------------|-------------------|
|COM kaydı|[Kayıt Defteri Makroları](../../atl/reference/registry-macros.md)|
|Sınıf fabrikası oluşturma|[Sınıf fabrikası makroları](../../atl/reference/aggregation-and-class-factory-macros.md)|
|Örnek oluşturma|[Toplama makroları](../../atl/reference/aggregation-and-class-factory-macros.md)|
|Bileşen kategorisi kaydı|[Kategori Makroları](../../atl/reference/category-macros.md)|
|Sınıf düzeyinde başlatma ve Temizleme|[ObjectMain](ccomobjectrootex-class.md#objectmain)|

##  <a name="object_entry_non_createable_ex_auto"></a>OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO

Nesnenin kaydedilip başlatılmış olması gerektiğini belirtmenize izin verir, ancak `CoCreateInstance`aracılığıyla dışarıdan oluşturulabilmelidir.

```
OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO( clsid, class )
```

### <a name="parameters"></a>Parametreler

*in*<br/>
'ndaki C++ *Sınıf adlı sınıf*tarafından uygulanan com sınıfının CLSID değeri.

*class*<br/>
'ndaki *CLSID*tarafından temsıl edilen C++ com sınıfını uygulayan sınıfın adı.

### <a name="remarks"></a>Açıklamalar

Nesne girişi makroları, bir sınıfın kaydı, başlatılması ve oluşturulması için destek sağlamak üzere projedeki genel kapsama yerleştirilir.

OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO, bir nesnenin kaydedilip başlatılması gerektiğini belirtmenize olanak tanır (daha fazla bilgi için bkz. [OBJECT_ENTRY_AUTO](#object_entry_auto) ), ancak `CoCreateInstance`aracılığıyla oluşturulabilir olmamalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Larının](../../atl/reference/atl-macros.md)
