---
title: COM eşlemesi genel işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlInternalQueryInterface
- atlbase/ATL::InlineIsEqualIUnknown
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, COM map global functions
ms.assetid: b9612d30-eb23-46ef-8093-d56f237d3cf1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c9185a71cc77cadb1ad7cdf577654730819147d2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46113142"
---
# <a name="com-map-global-functions"></a>COM eşlemesi genel işlevleri

Bu işlevler için COM eşleme desteği `IUnknown` uygulamaları.

|||
|-|-|
|[AtlInternalQueryInterface](#atlinternalqueryinterface)|Devreder `IUnknown` toplanmayan bir nesne.|
|[InlineIsEqualIUnknown](#inlineisequaliunknown)|Arabirimleri karşı karşılaştırma verimli kod oluşturur `IUnknown`.|  

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h  

##  <a name="atlinternalqueryinterface"></a>  AtlInternalQueryInterface

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
[in] Açık arabirimler COM haritasını içeren nesneye bir işaretçi `QueryInterface`.

*pEntries*<br/>
[in] Bir dizi `_ATL_INTMAP_ENTRY` kullanılabilir arabirim haritasını erişim yapılar.

*IID*<br/>
[in] İstenen arabiriminin GUID'si.

*ppvObject*<br/>
[out] Belirtilen arabirim işaretçisini bir işaretçi *IID*, veya arabirim bulunamazsa NULL.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

`AtlInternalQueryInterface` yalnızca COM eşleme tablosunda arabirimleri işler. Nesne toplanırsa, `AtlInternalQueryInterface` için dış bilinmeyen temsilci değil. COM eşlemesi tablosuna makro arabirimleri girebilirsiniz [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) veya türevleri biri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#94](../../atl/codesnippet/cpp/com-map-global-functions_1.cpp)]

##  <a name="inlineisequaliunknown"></a>  InlineIsEqualIUnknown

Sınama özel durum için bu işlevi çağırın `IUnknown`.

```
BOOL InlineIsEqualUnknown(REFGUID rguid1);
```

### <a name="parameters"></a>Parametreler

*rguid1*<br/>
[in] Karşılaştırma yapılacak GUID `IID_IUnknown`.

## <a name="see-also"></a>Ayrıca Bkz.

[İşlevler](../../atl/reference/atl-functions.md)<br/>
[COM Eşleme Makroları](../../atl/reference/com-map-macros.md)
