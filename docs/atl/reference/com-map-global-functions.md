---
title: COM eşlemesi genel Işlevleri
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlInternalQueryInterface
- atlbase/ATL::InlineIsEqualIUnknown
helpviewer_keywords:
- COM interfaces, COM map global functions
ms.assetid: b9612d30-eb23-46ef-8093-d56f237d3cf1
ms.openlocfilehash: adf4e06eb46aed74d08071dccce1db549ca31226
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833601"
---
# <a name="com-map-global-functions"></a>COM eşlemesi genel Işlevleri

Bu işlevler, COM harita uygulamaları için destek sağlar `IUnknown` .

|İşlev|Açıklama|
|-|-|
|[AtlInternalQueryInterface](#atlinternalqueryinterface)|`IUnknown`Toplanmayan bir nesnenin öğesine temsilciler.|
|[InlineIsEqualIUnknown](#inlineisequaliunknown)|Arabirimleri karşılaştırmak için verimli kod üretir `IUnknown` .|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="atlinternalqueryinterface"></a><a name="atlinternalqueryinterface"></a> AtlInternalQueryInterface

İstenen arabirim için bir işaretçi alır.

```
HRESULT AtlInternalQueryInterface(
    void* pThis,
    const _ATL_INTMAP_ENTRY* pEntries,
    REFIID iid,
    void** ppvObject);
```

### <a name="parameters"></a>Parametreler

*pThis*<br/>
'ndaki ' A sunulan arabirimlerin COM haritasını içeren nesneye yönelik bir işaretçi `QueryInterface` .

*pEntries*<br/>
'ndaki `_ATL_INTMAP_ENTRY` Kullanılabilir arabirimlerin haritasına erişen yapıların dizisi.

*'si*<br/>
'ndaki İstenen arabirimin GUID 'SI.

*ppvObject*<br/>
dışı Arabirim bulunamazsa, *IID*'de belirtilen arabirim işaretçisi IŞARETÇISI veya null.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

`AtlInternalQueryInterface` yalnızca COM Map tablosundaki arabirimleri işler. Nesneniz toplanırsa, `AtlInternalQueryInterface` Bilinmeyen dış öğesine temsilci eklemez. COM harita tablosuna, makro [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) veya türevlerinden biri ile arabirimler girebilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#94](../../atl/codesnippet/cpp/com-map-global-functions_1.cpp)]

## <a name="inlineisequaliunknown"></a><a name="inlineisequaliunknown"></a> InlineIsEqualIUnknown

Test için özel durum için bu işlevi çağırın `IUnknown` .

```
BOOL InlineIsEqualUnknown(REFGUID rguid1);
```

### <a name="parameters"></a>Parametreler

*rguid1*<br/>
'ndaki Karşılaştırılacak GUID `IID_IUnknown` .

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../../atl/reference/atl-functions.md)<br/>
[COM eşleme makroları](../../atl/reference/com-map-macros.md)
