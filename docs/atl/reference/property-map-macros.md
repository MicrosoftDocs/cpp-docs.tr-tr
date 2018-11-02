---
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
ms.openlocfilehash: 7422c38bd21a458dccafa6d34fd4d6522f96132a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50513828"
---
# <a name="property-map-macros"></a>Özellik eşleme makroları

Bu makrolar özellik eşlemeleri ve girişleri tanımlayın.

|||
|-|-|
|[BEGIN_PROP_MAP](#begin_prop_map)|ATL özellik eşlemesi başlangıcını işaretler.|
|[PROP_DATA_ENTRY](#prop_data_entry)|Kapsamı veya bir ActiveX denetimi boyutlarını belirtir.|
|[PROP_ENTRY_TYPE](#prop_entry_type)|Özellik açıklaması, özellik DISPID ve özellik sayfası CLSID özellik eşlemesi girer.|
|[PROP_ENTRY_TYPE_EX](#prop_entry_type_ex)|Özellik açıklaması, özellik DISPID, CLSID, özellik sayfası girer ve `IDispatch` IID özellik eşlemesi içinde.|
|[PROP_PAGE](#prop_page)|Bir özellik sayfası CLSID özellik eşlemesi girer.|
|[END_PROP_MAP](#end_prop_map)|ATL özellik eşlemesi sonunu işaretler.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

##  <a name="begin_prop_map"></a>  BEGIN_PROP_MAP

Nesnenin özellik eşlemesi başlangıcını işaretler.

```
BEGIN_PROP_MAP(theClass)
```

### <a name="parameters"></a>Parametreler

*Sınıfın*<br/>
[in] Özellik eşlemesini içeren sınıfın belirtir.

### <a name="remarks"></a>Açıklamalar

Özellik açıklamaları, özellik DISPID değeri, özellik sayfası CLSID, özellik eşlemesi depolar ve `IDispatch` IID'leri. Sınıflar [Iperpropertybrowsingımpl](../../atl/reference/iperpropertybrowsingimpl-class.md), [Ipersistpropertybagımpl](../../atl/reference/ipersistpropertybagimpl-class.md), [Ipersiststreamınitımpl](../../atl/reference/ipersiststreaminitimpl-class.md), ve [Ispecifypropertypagesımpl](../../atl/reference/ispecifypropertypagesimpl-class.md)özellik eşlemesini almak ve bu bilgileri ayarlamak için kullanın.

ATL projesi Sihirbazı'yla bir nesne oluşturduğunuzda, sihirbaz bir boş özellik eşlemesi ardından BEGIN_PROP_MAP belirterek oluşturacak [END_PROP_MAP](#end_prop_map).

Hiçbir uzantı sahip olabileceği için özellik eşlemesi kullanarak nesneyi bir kullanıcı arabirimi olmayabilir çünkü bir özellik eşlemesi uzantı (boyutlar) BEGIN_PROP_MAP kaydetmez. Nesnesi bir kullanıcı arabirimi ile bir ActiveX denetimi, bir uzantı var. Bu durumda, belirtmelisiniz [PROP_DATA_ENTRY](#prop_data_entry) ölçüde sağlamak için özellik eşlemesindeki.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#103](../../atl/codesnippet/cpp/property-map-macros_1.h)]

##  <a name="prop_data_entry"></a>  PROP_DATA_ENTRY

Kapsamı veya bir ActiveX denetimi boyutlarını belirtir.

```
PROP_DATA_ENTRY( szDesc, member, vt)
```

### <a name="parameters"></a>Parametreler

*szDesc*<br/>
[in] Özellik açıklaması.

*Üyesi*<br/>
[in] Uzantı içeren veri üyesi; Örneğin, `m_sizeExtent`.

*vt*<br/>
[in] Özelliğin değişken türünü belirtir.

### <a name="remarks"></a>Açıklamalar

Bu makro, kalıcı için belirtilen veri üyesi neden olur.

ActiveX denetimi oluşturduğunuzda, sihirbaz bu makroyu sonra özellik eşlemesi makrosu ekler. [BEGIN_PROP_MAP](#begin_prop_map) ve özellik eşlemesi makrosu önce [END_PROP_MAP](#end_prop_map).

### <a name="example"></a>Örnek

Aşağıdaki örnekte, nesne kapsamını (`m_sizeExtent`) sürdürüldüğü.

[!code-cpp[NVC_ATL_Windowing#131](../../atl/codesnippet/cpp/property-map-macros_2.h)]

[!code-cpp[NVC_ATL_Windowing#132](../../atl/codesnippet/cpp/property-map-macros_3.h)]

##  <a name="prop_entry_type"></a>  PROP_ENTRY_TYPE

Özellik açıklaması, özellik DISPID ve özellik sayfası CLSID nesnenin özellik eşlemesi girmek için bu makroyu kullanın.

```
PROP_ENTRY_TYPE( szDesc, dispid, clsid, vt)
```

### <a name="parameters"></a>Parametreler

*szDesc*<br/>
[in] Özellik açıklaması.

*DISPID*<br/>
[in] Özelliğin DISPID.

*CLSID*<br/>
[in] İlişkili özelliğin sayfanın CLSID değeri. Özel değer CLSID_NULL ilişkili özellik sayfası yok. bir özellik için kullanın.

*vt*<br/>
[in] Özelliğin türü.

### <a name="remarks"></a>Açıklamalar

PROP_ENTRY makrosu güvenli değildir ve kullanım dışı. PROP_ENTRY_TYPE ile değiştirilmiştir.

[BEGIN_PROP_MAP](#begin_prop_map) makrosu özellik eşlemesi başlangıcını işaretler; [END_PROP_MAP](#end_prop_map) makrosu sonunu işaretler.

### <a name="example"></a>Örnek

Örneğin bakın [BEGIN_PROP_MAP](#begin_prop_map).

##  <a name="prop_entry_type_ex"></a>  PROP_ENTRY_TYPE_EX

Benzer şekilde [PROP_ENTRY_TYPE](#prop_entry_type), ancak birden çok çift arabirim nesnenizin destekliyorsa, belirli bir IID belirtmeniz verir.

```
PROP_ENTRY_TYPE_EX( szDesc, dispid, clsid, iidDispatch, vt)
```

### <a name="parameters"></a>Parametreler

*szDesc*<br/>
[in] Özellik açıklaması.

*DISPID*<br/>
[in] Özelliğin DISPID.

*CLSID*<br/>
[in] İlişkili özelliğin sayfanın CLSID değeri. Özel değer CLSID_NULL ilişkili özellik sayfası yok. bir özellik için kullanın.

*iidDispatch*<br/>
[in] Özellik tanımlama çift arabirim Laboratuvardaki.

*vt*<br/>
[in] Özelliğin türü.

### <a name="remarks"></a>Açıklamalar

PROP_ENTRY_EX makrosu güvenli değildir ve kullanım dışı. PROP_ENTRY_TYPE_EX ile değiştirilmiştir.

[BEGIN_PROP_MAP](#begin_prop_map) makrosu özellik eşlemesi başlangıcını işaretler; [END_PROP_MAP](#end_prop_map) makrosu sonunu işaretler.

### <a name="example"></a>Örnek

Aşağıdaki örnek girişleri için gruplar `IMyDual1` için bir giriş ardından `IMyDual2`. Çift arabirim gruplandırarak performansı iyileştirir.

[!code-cpp[NVC_ATL_Windowing#133](../../atl/codesnippet/cpp/property-map-macros_4.h)]

##  <a name="prop_page"></a>  PROP_PAGE

Bir özellik sayfası CLSID nesnenin özellik eşlemesi girmek için bu makroyu kullanın.

```
PROP_PAGE(clsid)
```

### <a name="parameters"></a>Parametreler

*CLSID*<br/>
[in] Özellik sayfası CLSID değeri.

### <a name="remarks"></a>Açıklamalar

PROP_PAGE benzer [PROP_ENTRY_TYPE](#prop_entry_type), ancak bir özellik tanımı veya DISPID gerektirmez.

> [!NOTE]
>  PROP_ENTRY_TYPE CLSID girdiyseniz veya [PROP_ENTRY_TYPE_EX](#prop_entry_type_ex), PROP_PAGE ile ek bir giriş yapmak gerekmez.

[BEGIN_PROP_MAP](#begin_prop_map) makrosu özellik eşlemesi başlangıcını işaretler; [END_PROP_MAP](#end_prop_map) makrosu sonunu işaretler.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#134](../../atl/codesnippet/cpp/property-map-macros_5.h)]

##  <a name="end_prop_map"></a>  END_PROP_MAP

Nesnenin özellik eşlemesi sonunu işaretler.

```
END_PROP_MAP()
```

### <a name="remarks"></a>Açıklamalar

ATL projesi Sihirbazı'yla bir nesne oluşturduğunuzda, sihirbaz bir boş özellik eşlemesini belirterek oluşturacak [BEGIN_PROP_MAP](#begin_prop_map) END_PROP_MAP tarafından izlenen.

### <a name="example"></a>Örnek

Örneğin bakın [BEGIN_PROP_MAP](#begin_prop_map).

## <a name="see-also"></a>Ayrıca Bkz.

[Makroları](../../atl/reference/atl-macros.md)
