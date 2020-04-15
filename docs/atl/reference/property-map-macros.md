---
title: Özellik Eşleme Makroları
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_PROP_MAP
- atlcom/ATL::PROP_DATA_ENTRY
- atlcom/ATL::PROP_ENTRY_TYPE
- atlcom/ATL::PROP_ENTRY_TYPE_EX
- atlcom/ATL::PROP_PAGE
- atlcom/ATL::END_PROP_MAP
helpviewer_keywords:
- property maps
ms.assetid: 128bc742-2b98-4b97-a243-684dbb83db77
ms.openlocfilehash: 56fdb02939a99e396b9000705753e2475b80f6dc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326100"
---
# <a name="property-map-macros"></a>Özellik Eşleme Makroları

Bu makrolar özellik eşlemlerini ve girişleri tanımlar.

|||
|-|-|
|[BEGIN_PROP_MAP](#begin_prop_map)|ATL özellik haritasının başlangıcını işaretler.|
|[PROP_DATA_ENTRY](#prop_data_entry)|ActiveX denetiminin kapsamını veya boyutlarını gösterir.|
|[PROP_ENTRY_TYPE](#prop_entry_type)|Özellik eşlemine bir özellik açıklaması, özellik DISPID ve özellik sayfası CLSID girer.|
|[PROP_ENTRY_TYPE_EX](#prop_entry_type_ex)|Özellik açıklamasına, özellik DISPID'e, özellik `IDispatch` sayfası CLSID'ye ve IID'yi özellik haritasına girer.|
|[PROP_PAGE](#prop_page)|Özellik haritasına bir özellik sayfası CLSID girer.|
|[END_PROP_MAP](#end_prop_map)|ATL özellik haritasının sonunu işaretler.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="begin_prop_map"></a><a name="begin_prop_map"></a>BEGIN_PROP_MAP

Nesnenin özellik haritasının başlangıcını işaretler.

```
BEGIN_PROP_MAP(theClass)
```

### <a name="parameters"></a>Parametreler

*theClass*<br/>
[içinde] Özellik eşlemi içeren sınıfı belirtir.

### <a name="remarks"></a>Açıklamalar

Özellik haritası, özellik tanımlarını, özellik DISPID'lerini, özellik sayfası `IDispatch` CLSID'leri ve IID'leri depolar. Sınıflar [IPerPropertyBrowsingImpl](../../atl/reference/iperpropertybrowsingimpl-class.md), [IPersistPropertyBagImpl](../../atl/reference/ipersistpropertybagimpl-class.md), [IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md), ve [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md) almak ve bu bilgileri ayarlamak için özellik haritası kullanın.

ATL Project Sihirbazı ile bir nesne oluşturduğunuzda, sihirbaz [END_PROP_MAP](#end_prop_map)tarafından izlenen BEGIN_PROP_MAP belirterek boş bir özellik eşlemi oluşturur.

BEGIN_PROP_MAP özellik eşlemi kullanan bir nesnenin kullanıcı arabirimi olmayabilir, bu nedenle hiçbir ölçüde olurdu, çünkü bir özellik haritası (yani, boyutları) ölçüde kaydetmez. Nesne kullanıcı arabirimi ile activex denetimi ise, bir ölçüde vardır. Bu durumda, kapsamı sağlamak için mülkiyet haritanızda [PROP_DATA_ENTRY](#prop_data_entry) belirtmeniz gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#103](../../atl/codesnippet/cpp/property-map-macros_1.h)]

## <a name="prop_data_entry"></a><a name="prop_data_entry"></a>PROP_DATA_ENTRY

ActiveX denetiminin kapsamını veya boyutlarını gösterir.

```
PROP_DATA_ENTRY( szDesc, member, vt)
```

### <a name="parameters"></a>Parametreler

*szDesc*<br/>
[içinde] Mülk tanımı.

*Üye*<br/>
[içinde] Kapsamını içeren veri üyesi; örneğin, `m_sizeExtent`.

*Vt*<br/>
[içinde] Özelliğin VARYANT türünü belirtir.

### <a name="remarks"></a>Açıklamalar

Bu makro, belirtilen veri üyesinin kalıcı olarak süreverilmesine neden olur.

ActiveX denetimi oluşturduğunuzda, sihirbaz bu makroyu özellik haritası makro [BEGIN_PROP_MAP](#begin_prop_map) sonra ve özellik haritası makro [END_PROP_MAP](#end_prop_map)önce ekler.

### <a name="example"></a>Örnek

Aşağıdaki örnekte, nesnenin kapsamı`m_sizeExtent`( ) devam ediyor.

[!code-cpp[NVC_ATL_Windowing#131](../../atl/codesnippet/cpp/property-map-macros_2.h)]

[!code-cpp[NVC_ATL_Windowing#132](../../atl/codesnippet/cpp/property-map-macros_3.h)]

## <a name="prop_entry_type"></a><a name="prop_entry_type"></a>PROP_ENTRY_TYPE

Nesnenin özellik haritasına özellik açıklaması, özellik DISPID ve özellik sayfası CLSID girmek için bu makroyu kullanın.

```
PROP_ENTRY_TYPE( szDesc, dispid, clsid, vt)
```

### <a name="parameters"></a>Parametreler

*szDesc*<br/>
[içinde] Mülk tanımı.

*Dıspıd*<br/>
[içinde] Tesis DISPID.

*Clsıd*<br/>
[içinde] İlişkili özellik sayfasının CLSID'si. İlişkili bir özellik sayfası olmayan bir özellik için özel değeri CLSID_NULL kullanın.

*Vt*<br/>
[içinde] Mülkün türü.

### <a name="remarks"></a>Açıklamalar

PROP_ENTRY makro güvensiz ve amortismana uğradı. PROP_ENTRY_TYPE ile değiştirildi.

[BEGIN_PROP_MAP](#begin_prop_map) makrosu özellik haritasının başlangıcını işaretler; [END_PROP_MAP](#end_prop_map) makro sonunu işaretler.

### <a name="example"></a>Örnek

[BEGIN_PROP_MAP](#begin_prop_map)için örneğe bakın.

## <a name="prop_entry_type_ex"></a><a name="prop_entry_type_ex"></a>PROP_ENTRY_TYPE_EX

[PROP_ENTRY_TYPE](#prop_entry_type)benzer, ancak nesneniz birden çok çift arabirimi destekliyorsa belirli bir IID belirtmenizi sağlar.

```
PROP_ENTRY_TYPE_EX( szDesc, dispid, clsid, iidDispatch, vt)
```

### <a name="parameters"></a>Parametreler

*szDesc*<br/>
[içinde] Mülk tanımı.

*Dıspıd*<br/>
[içinde] Tesis DISPID.

*Clsıd*<br/>
[içinde] İlişkili özellik sayfasının CLSID'si. İlişkili bir özellik sayfası olmayan bir özellik için özel değeri CLSID_NULL kullanın.

*iidDispatch*<br/>
[içinde] Özelliği tanımlayan çift arabirimin IID'si.

*Vt*<br/>
[içinde] Mülkün türü.

### <a name="remarks"></a>Açıklamalar

PROP_ENTRY_EX makrosu güvensiz ve amortismana lıydı. PROP_ENTRY_TYPE_EX ile değiştirildi.

[BEGIN_PROP_MAP](#begin_prop_map) makrosu özellik haritasının başlangıcını işaretler; [END_PROP_MAP](#end_prop_map) makro sonunu işaretler.

### <a name="example"></a>Örnek

Aşağıdaki örnek gruplar `IMyDual1` girişleri için bir `IMyDual2`giriş takip . Çift arabirime göre gruplandırma performansı artırır.

[!code-cpp[NVC_ATL_Windowing#133](../../atl/codesnippet/cpp/property-map-macros_4.h)]

## <a name="prop_page"></a><a name="prop_page"></a>PROP_PAGE

Nesnenin özellik haritasına bir özellik sayfası CLSID girmek için bu makroyu kullanın.

```
PROP_PAGE(clsid)
```

### <a name="parameters"></a>Parametreler

*Clsıd*<br/>
[içinde] Özellik sayfasının CLSID'si.

### <a name="remarks"></a>Açıklamalar

PROP_PAGE [PROP_ENTRY_TYPE](#prop_entry_type)benzer, ancak bir özellik açıklaması veya DISPID gerektirmez.

> [!NOTE]
> zaten PROP_ENTRY_TYPE veya [PROP_ENTRY_TYPE_EX](#prop_entry_type_ex)ile bir CLSID girdiyseniz, PROP_PAGE ile ek bir giriş yapmanız gerekmez.

[BEGIN_PROP_MAP](#begin_prop_map) makrosu özellik haritasının başlangıcını işaretler; [END_PROP_MAP](#end_prop_map) makro sonunu işaretler.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#134](../../atl/codesnippet/cpp/property-map-macros_5.h)]

## <a name="end_prop_map"></a><a name="end_prop_map"></a>END_PROP_MAP

Nesnenin özellik haritasının sonunu işaretler.

```
END_PROP_MAP()
```

### <a name="remarks"></a>Açıklamalar

ATL Project Sihirbazı ile bir nesne oluşturduğunuzda, sihirbaz END_PROP_MAP ardından [BEGIN_PROP_MAP](#begin_prop_map) belirterek boş bir özellik eşlemi oluşturur.

### <a name="example"></a>Örnek

[BEGIN_PROP_MAP](#begin_prop_map)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar](../../atl/reference/atl-macros.md)
