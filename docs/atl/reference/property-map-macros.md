---
description: 'Daha fazla bilgi edinin: Özellik Haritası makroları'
title: Özellik eşleme makroları
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
ms.openlocfilehash: b2fc7f96c42d7f9d3f116f13c9864ce857e32743
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157808"
---
# <a name="property-map-macros"></a>Özellik eşleme makroları

Bu makrolar Özellik haritaları ve girdileri tanımlar.

|Ad|Açıklama|
|-|-|
|[BEGIN_PROP_MAP](#begin_prop_map)|ATL Özellik eşlemesinin başlangıcını işaretler.|
|[PROP_DATA_ENTRY](#prop_data_entry)|Bir ActiveX denetiminin kapsamını veya boyutlarını gösterir.|
|[PROP_ENTRY_TYPE](#prop_entry_type)|Özellik eşlemesine Özellik açıklaması, özellik DISPID ve özellik sayfası CLSID 'SI girer.|
|[PROP_ENTRY_TYPE_EX](#prop_entry_type_ex)|Özellik eşlemesine Özellik açıklaması, özellik DISPID, özellik sayfası CLSID ve `IDispatch` IID 'yi girer.|
|[PROP_PAGE](#prop_page)|Özellik eşlemesine bir özellik sayfası CLSID 'SI girer.|
|[END_PROP_MAP](#end_prop_map)|ATL Özellik eşlemesinin sonunu işaretler.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

## <a name="begin_prop_map"></a><a name="begin_prop_map"></a> BEGIN_PROP_MAP

Nesnenin özellik eşlemesinin başlangıcını işaretler.

```
BEGIN_PROP_MAP(theClass)
```

### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
'ndaki Özellik eşlemesini içeren sınıfı belirtir.

### <a name="remarks"></a>Açıklamalar

Özellik eşlemesi, özellik açıklamalarını, özellik dispID 'leri, özellik sayfası CLSID 'Lerini ve `IDispatch` IIDS 'yi depolar. [Iperpropertybrowsingimpl](../../atl/reference/iperpropertybrowsingimpl-class.md), [ıpersistpropertybagimpl](../../atl/reference/ipersistpropertybagimpl-class.md), [ıpersiststreaminimpl](../../atl/reference/ipersiststreaminitimpl-class.md)ve [ıdiifyıpropertypagesimpl](../../atl/reference/ispecifypropertypagesimpl-class.md) sınıfları bu bilgileri almak ve ayarlamak için özellik eşlemesini kullanır.

ATL Proje sihirbazıyla bir nesne oluşturduğunuzda, sihirbaz BEGIN_PROP_MAP ve ardından [END_PROP_MAP](#end_prop_map)' i belirterek boş bir özellik eşlemesi oluşturacaktır.

BEGIN_PROP_MAP, özellik eşlemesi kullanan bir nesne Kullanıcı arabirimine sahip olmadığından, bir özellik eşlemesinin kapsamını (yani, boyutlar) kaydetmez. Nesne bir kullanıcı arabirimine sahip bir ActiveX denetimi ise, bir uzantısı vardır. Bu durumda, kapsamı sağlamak için özellik haritanızda [PROP_DATA_ENTRY](#prop_data_entry) belirtmeniz gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#103](../../atl/codesnippet/cpp/property-map-macros_1.h)]

## <a name="prop_data_entry"></a><a name="prop_data_entry"></a> PROP_DATA_ENTRY

Bir ActiveX denetiminin kapsamını veya boyutlarını gösterir.

```
PROP_DATA_ENTRY( szDesc, member, vt)
```

### <a name="parameters"></a>Parametreler

*szDesc*<br/>
'ndaki Özellik açıklaması.

*üyesidir*<br/>
'ndaki Kapsamı içeren veri üyesi; Örneğin, `m_sizeExtent` .

*z*<br/>
'ndaki Özelliğin DEĞIŞKEN türünü belirtir.

### <a name="remarks"></a>Açıklamalar

Bu makro, belirtilen veri üyesinin kalıcı hale gelmesine neden olur.

Bir ActiveX denetimi oluşturduğunuzda, sihirbaz bu makroyu, özellik Haritası makrosu [BEGIN_PROP_MAP](#begin_prop_map) sonra ve özellik haritası makrosu [END_PROP_MAP](#end_prop_map)önce ekler.

### <a name="example"></a>Örnek

Aşağıdaki örnekte, nesnesinin () kapsamı kalıcı hale getirildi `m_sizeExtent` .

[!code-cpp[NVC_ATL_Windowing#131](../../atl/codesnippet/cpp/property-map-macros_2.h)]

[!code-cpp[NVC_ATL_Windowing#132](../../atl/codesnippet/cpp/property-map-macros_3.h)]

## <a name="prop_entry_type"></a><a name="prop_entry_type"></a> PROP_ENTRY_TYPE

Nesnenin özellik eşlemesine bir özellik açıklaması, özellik DISPID ve özellik sayfası CLSID 'SI girmek için bu makroyu kullanın.

```
PROP_ENTRY_TYPE( szDesc, dispid, clsid, vt)
```

### <a name="parameters"></a>Parametreler

*szDesc*<br/>
'ndaki Özellik açıklaması.

*dı*<br/>
'ndaki Özelliğin DISPID 'i.

*in*<br/>
'ndaki İlişkili özellik sayfasının CLSID 'SI. İlişkili özellik sayfasına sahip olmayan bir özellik için CLSID_NULL özel değeri kullanın.

*z*<br/>
'ndaki Özelliğin türü.

### <a name="remarks"></a>Açıklamalar

PROP_ENTRY makrosu güvensiz ve kullanım dışı bırakıldı. PROP_ENTRY_TYPE ile değiştirilmiştir.

[BEGIN_PROP_MAP](#begin_prop_map) makro, özellik eşlemesinin başlangıcını işaretler; [END_PROP_MAP](#end_prop_map) makro bitişi işaretler.

### <a name="example"></a>Örnek

[BEGIN_PROP_MAP](#begin_prop_map)için örneğe bakın.

## <a name="prop_entry_type_ex"></a><a name="prop_entry_type_ex"></a> PROP_ENTRY_TYPE_EX

[Prop_entry_type](#prop_entry_type)benzer, ancak nesneniz birden çok çift arabirimi destekliyorsa belırlı bir IID belirtmenize olanak tanır.

```
PROP_ENTRY_TYPE_EX( szDesc, dispid, clsid, iidDispatch, vt)
```

### <a name="parameters"></a>Parametreler

*szDesc*<br/>
'ndaki Özellik açıklaması.

*dı*<br/>
'ndaki Özelliğin DISPID 'i.

*in*<br/>
'ndaki İlişkili özellik sayfasının CLSID 'SI. İlişkili özellik sayfasına sahip olmayan bir özellik için CLSID_NULL özel değeri kullanın.

*ııddispatch*<br/>
'ndaki Özelliği tanımlayan çift arabirimin IID 'si.

*z*<br/>
'ndaki Özelliğin türü.

### <a name="remarks"></a>Açıklamalar

PROP_ENTRY_EX makrosu güvensiz ve kullanım dışı bırakıldı. PROP_ENTRY_TYPE_EX ile değiştirilmiştir.

[BEGIN_PROP_MAP](#begin_prop_map) makro, özellik eşlemesinin başlangıcını işaretler; [END_PROP_MAP](#end_prop_map) makro bitişi işaretler.

### <a name="example"></a>Örnek

Aşağıdaki örnek, için `IMyDual1` bir girişi tarafından izlenen girdilerini gruplandırır `IMyDual2` . Dual Interface 'e göre gruplandırma performansı iyileştirir.

[!code-cpp[NVC_ATL_Windowing#133](../../atl/codesnippet/cpp/property-map-macros_4.h)]

## <a name="prop_page"></a><a name="prop_page"></a> PROP_PAGE

Nesnenin özellik eşlemesine bir özellik sayfası CLSID 'SI girmek için bu makroyu kullanın.

```
PROP_PAGE(clsid)
```

### <a name="parameters"></a>Parametreler

*in*<br/>
'ndaki Özellik sayfasının CLSID 'SI.

### <a name="remarks"></a>Açıklamalar

PROP_PAGE, [prop_entry_type](#prop_entry_type)benzerdir, ancak bir özellik açıklaması ya da DISPID gerektirmez.

> [!NOTE]
> PROP_ENTRY_TYPE veya [PROP_ENTRY_TYPE_EX](#prop_entry_type_ex)sahıp bir CLSID zaten girdiyseniz PROP_PAGE ile ek bir giriş yapmanız gerekmez.

[BEGIN_PROP_MAP](#begin_prop_map) makro, özellik eşlemesinin başlangıcını işaretler; [END_PROP_MAP](#end_prop_map) makro bitişi işaretler.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#134](../../atl/codesnippet/cpp/property-map-macros_5.h)]

## <a name="end_prop_map"></a><a name="end_prop_map"></a> END_PROP_MAP

Nesnenin özellik eşlemesinin sonunu işaretler.

```
END_PROP_MAP()
```

### <a name="remarks"></a>Açıklamalar

ATL Proje sihirbazıyla bir nesne oluşturduğunuzda, sihirbaz [BEGIN_PROP_MAP](#begin_prop_map) ve ardından END_PROP_MAP ' i belirterek boş bir özellik eşlemesi oluşturacaktır.

### <a name="example"></a>Örnek

[BEGIN_PROP_MAP](#begin_prop_map)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar](../../atl/reference/atl-macros.md)
