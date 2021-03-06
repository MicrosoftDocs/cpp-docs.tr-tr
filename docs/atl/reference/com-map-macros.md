---
description: 'Daha fazla bilgi edinin: COM Map makroları'
title: COM eşleme makroları
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_COM_MAP
- atlcom/ATL::END_COM_MAP
helpviewer_keywords:
- COM interfaces, COM map macros
ms.assetid: 0f33656d-321f-4996-90cc-9a7f21ab73c3
ms.openlocfilehash: 076a13418a48147654862c2b5a26688b195d5252
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141329"
---
# <a name="com-map-macros"></a>COM eşleme makroları

Bu makrolar COM arabirim eşlemelerini tanımlar.

|Makroya|Açıklama|
|-|-|
|[BEGIN_COM_MAP](#begin_com_map)|COM arabirimi eşleme girdilerinin başlangıcını işaretler.|
|[END_COM_MAP](#end_com_map)|COM arabirimi eşleme girdilerinin sonunu işaretler.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

## <a name="begin_com_map"></a><a name="begin_com_map"></a> BEGIN_COM_MAP

COM eşlemesi, bir nesnesinde bir istemciye arabirim sunan bir mekanizmadır `QueryInterface` .

```
BEGIN_COM_MAP(x)
```

### <a name="parameters"></a>Parametreler

*x*<br/>
'ndaki Arabirimleri üzerinde kullanıma sunuyoruz sınıf nesnesinin adı.

### <a name="remarks"></a>Açıklamalar

[CComObjectRootEx:: InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface) yalnızca com eşlemesindeki arabirimlerin işaretçilerini döndürür. BEGIN_COM_MAP makrosu ile arabirim eşlemenizi başlatın, [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) makroünden veya türevlerinden birine sahip arabirimlerinizin her biri için girişler ekleyin ve [END_COM_MAP](#end_com_map) makroyla Haritayı doldurun.

### <a name="example"></a>Örnek

ATL [BEEPER](../../overview/visual-cpp-samples.md) örneğinden:

[!code-cpp[NVC_ATL_COM#1](../../atl/codesnippet/cpp/com-map-macros_1.h)]

## <a name="end_com_map"></a><a name="end_com_map"></a> END_COM_MAP

COM arabirimi haritaınızın tanımını sonlandırır.

```
END_COM_MAP()
```

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar](../../atl/reference/atl-macros.md)<br/>
[COM eşlemesi genel Işlevleri](../../atl/reference/com-map-global-functions.md)
