---
title: Nesne eşleme makroları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcom/ATL::DECLARE_OBJECT_DESCRIPTION
- atlcom/ATL::OBJECT_ENTRY_AUTO
- atlcom/ATL::OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO
dev_langs:
- C++
ms.assetid: 680087f4-9894-41dd-a79c-6f337e1f13c1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3b85d157cd6124bb0ef6e6167a415c018e14b046
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46040446"
---
# <a name="object-map-macros"></a>Nesne işleme makroları

Bu makrolar, nesne eşlemeleri ve girişleri tanımlayın.

|||
|-|-|
|[DECLARE_OBJECT_DESCRIPTION](#declare_object_description)|Nesne eşlemesine girilen bir sınıf nesnesinin metin açıklama belirtmenizi sağlar.|
|[OBJECT_ENTRY_AUTO](#object_entry_auto)|ATL nesnesi nesne eşlemesine girer, kayıt defterini güncelleştirir ve nesne örneği oluşturur.|
|[OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](#object_entry_non_createable_ex_auto)|Nesne kayıtlı ve başlatılmış olduğunu belirlemenizi sağlar, ancak harici olarak oluşturulabilir aracılığıyla olmamalıdır `CoCreateInstance`.|  

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

##  <a name="declare_object_description"></a>  DECLARE_OBJECT_DESCRIPTION

Sınıf nesneniz için bir metin açıklama belirtmenizi sağlar.

```
DECLARE_OBJECT_DESCRIPTION( x )
```

### <a name="parameters"></a>Parametreler

*x*<br/>
[in] Sınıfı nesne açıklaması.

### <a name="remarks"></a>Açıklamalar

ATL bu açıklama nesne eşlemesi üzerinden girer [OBJECT_ENTRY_AUTO](#object_entry_auto) makrosu.

DECLARE_OBJECT_DESCRIPTION uygulayan bir `GetObjectDescription` geçersiz kılmak için kullanabileceğiniz işlevi [CComCoClass::GetObjectDescription](ccomcoclass-class.md#getobjectdescription) yöntemi.  

`GetObjectDescription` İşlevi çağrıldığında `IComponentRegistrar::GetComponents`. `IComponentRegistrar` kaydolun ve bileşenleri tek tek bir DLL kaydını olanak tanıyan bir Otomasyon arabirimidir. ATL projesi Sihirbazı'yla bir bileşeni kayıt şirketi nesnesi oluşturduğunuzda, sihirbaz otomatik olarak Uygula `IComponentRegistrar` arabirimi. `IComponentRegistrar` genellikle Microsoft işlem sunucusu tarafından kullanılır.

ATL projesi Sihirbazı hakkında daha fazla bilgi için bkz [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#123](../../atl/codesnippet/cpp/object-map-macros_1.h)]

##  <a name="object_entry_auto"></a>  OBJECT_ENTRY_AUTO

ATL nesnesi nesne eşlemesine girer, kayıt defterini güncelleştirir ve nesne örneği oluşturur.

```
OBJECT_ENTRY_AUTO( clsid, class )
```

### <a name="parameters"></a>Parametreler

*CLSID*<br/>
[in] Adlı bir C++ sınıfı tarafından uygulanan bir COM sınıfı CLSID'si *sınıfı*.

*class*<br/>
[in] COM sınıfı tarafından temsil edilen C++ sınıfı adı *CLSID*.

### <a name="remarks"></a>Açıklamalar

Nesne giriş makroları, kayıt, başlatma ve bir sınıf oluşturulmasını desteklemek için projedeki genel kapsamda yerleştirilir.

Sınıf üreteci oluşturan sınıf ve oluşturucu sınıf işlev işaretçileri OBJECT_ENTRY_AUTO girer `CreateInstance` işlevleri için bu nesnede ATL nesne otomatik üretilmiş eşlemesi. Zaman [CAtlComModule::RegisterServer](catlcommodule-class.md#registerserver) olan çağrılır, nesne eşlemesindeki her nesnenin sistem kayıt defterini güncelleştirir.  

Aşağıdaki tabloda, bu makroya ikinci parametre olarak belirtilen sınıftan nesne haritaya eklenen bilgilerin nasıl elde açıklar.

|Bilgi için|Alınan|
|---------------------|-------------------|
|COM kayıt|[Kayıt Defteri Makroları](../../atl/reference/registry-macros.md)|
|Sınıf fabrikası oluşturma|[Sınıf üreticisi makroları](../../atl/reference/aggregation-and-class-factory-macros.md)|
|Örnek oluşturma|[Toplama makroları](../../atl/reference/aggregation-and-class-factory-macros.md)|
|Bileşen kategori kaydı|[Kategori Makroları](../../atl/reference/category-macros.md)|
|Sınıf düzeyi başlatma ve temizleme|[ObjectMain](ccomobjectrootex-class.md#objectmain)|  

##  <a name="object_entry_non_createable_ex_auto"></a>  OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO

Nesne kayıtlı ve başlatılmış olduğunu belirlemenizi sağlar, ancak harici olarak oluşturulabilir aracılığıyla olmamalıdır `CoCreateInstance`.

```
OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO( clsid, class )
```

### <a name="parameters"></a>Parametreler

*CLSID*<br/>
[in] Adlı bir C++ sınıfı tarafından uygulanan bir COM sınıfı CLSID'si *sınıfı*.

*class*<br/>
[in] COM sınıfı tarafından temsil edilen C++ sınıfı adı *CLSID*.

### <a name="remarks"></a>Açıklamalar

Nesne giriş makroları, kayıt, başlatma ve bir sınıf oluşturulmasını desteklemek için projedeki genel kapsamda yerleştirilir.

OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO, bir nesne kayıtlı ve başlatılmış olduğunu belirtmenize olanak sağlar (bkz [OBJECT_ENTRY_AUTO](#object_entry_auto) daha fazla bilgi için), ancak aracılığıyla oluşturulabilir olmamalıdır `CoCreateInstance`.

## <a name="see-also"></a>Ayrıca Bkz.

[Makroları](../../atl/reference/atl-macros.md)
