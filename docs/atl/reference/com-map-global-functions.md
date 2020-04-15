---
title: COM Eşlemesi Genel İşlevleri
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlInternalQueryInterface
- atlbase/ATL::InlineIsEqualIUnknown
helpviewer_keywords:
- COM interfaces, COM map global functions
ms.assetid: b9612d30-eb23-46ef-8093-d56f237d3cf1
ms.openlocfilehash: c4ce7c7a68c0744ad65ef4914088fa12d3340628
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326691"
---
# <a name="com-map-global-functions"></a>COM Eşlemesi Genel İşlevleri

Bu işlevler COM `IUnknown` Map uygulamaları için destek sağlar.

|||
|-|-|
|[AtlInternalQueryInterface](#atlinternalqueryinterface)|Birbirlemeyen `IUnknown` bir nesnenin temsilcileri.|
|[InlineIsEqualIUnknown](#inlineisequaliunknown)|Arayüzleri `IUnknown`' nle karşılaştırmak için verimli kod oluşturur.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="atlinternalqueryinterface"></a><a name="atlinternalqueryinterface"></a>AtlInternalQueryInterface

İstenen arabirim için bir işaretçi alır.

```
HRESULT AtlInternalQueryInterface(
    void* pThis,
    const _ATL_INTMAP_ENTRY* pEntries,
    REFIID iid,
    void** ppvObject);
```

### <a name="parameters"></a>Parametreler

*pBu*<br/>
[içinde] Açıkta kalan arabirimlerin COM eşlemi içeren `QueryInterface`nesneye bir işaretçi.

*pEntries*<br/>
[içinde] Kullanılabilir arabirimlerin haritasına erişen bir dizi `_ATL_INTMAP_ENTRY` yapı.

*ııd*<br/>
[içinde] İstenmekte olan arabirimin GUID'i.

*ppvNesne*<br/>
[çıkış] Arabirim bulunamazsa *iid*veya NULL'da belirtilen arabirim işaretçisine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

`AtlInternalQueryInterface`yalnızca COM harita tablosundaki arabirimleri işler. Nesneniz biraraya geliyorsa, `AtlInternalQueryInterface` dış bilinmeyene temsilci vermez. Makro [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) veya türevlerinden biriyle COM harita tablosuna arayüzler girebilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#94](../../atl/codesnippet/cpp/com-map-global-functions_1.cpp)]

## <a name="inlineisequaliunknown"></a><a name="inlineisequaliunknown"></a>InlineIsEqualIUnknown

Bu işlevi çağırın, için test `IUnknown`özel durumda.

```
BOOL InlineIsEqualUnknown(REFGUID rguid1);
```

### <a name="parameters"></a>Parametreler

*rguid1*<br/>
[içinde] Guid ile `IID_IUnknown`karşılaştırın.

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../../atl/reference/atl-functions.md)<br/>
[COM Eşleme Makroları](../../atl/reference/com-map-macros.md)
