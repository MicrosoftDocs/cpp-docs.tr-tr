---
title: COM Eşleme Makroları
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_COM_MAP
- atlcom/ATL::END_COM_MAP
helpviewer_keywords:
- COM interfaces, COM map macros
ms.assetid: 0f33656d-321f-4996-90cc-9a7f21ab73c3
ms.openlocfilehash: 191a0ba0aeda6ad18cdac7ba14f7ab5f3b2282f7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326597"
---
# <a name="com-map-macros"></a>COM Eşleme Makroları

Bu makrolar COM arabirim eşlemlerini tanımlar.

|||
|-|-|
|[BEGIN_COM_MAP](#begin_com_map)|COM arabirim eşlemi girişlerinin başlangıcını işaretler.|
|[END_COM_MAP](#end_com_map)|COM arabirim eşlemi girişlerinin sonunu işaretler.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="begin_com_map"></a><a name="begin_com_map"></a>BEGIN_COM_MAP

COM eşlemi, bir nesneüzerindeki arabirimleri bir istemciye ileten `QueryInterface`mekanizmadır.

```
BEGIN_COM_MAP(x)
```

### <a name="parameters"></a>Parametreler

*X*<br/>
[içinde] Arayüzleri açığa çıkardığınız sınıf nesnesinin adı.

### <a name="remarks"></a>Açıklamalar

[CComObjectRootEx::InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface) yalnızca COM haritasındaki arabirimler için işaretçileri döndürür. Arayüz haritanızı BEGIN_COM_MAP makrosuyla başlatın, [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) makrosu veya türevlerinden biriyle arabirimlerinizin her biri için girişler ekleyin ve [END_COM_MAP](#end_com_map) makrosuyla haritayı tamamlayın.

### <a name="example"></a>Örnek

ATL [BEEPER](../../overview/visual-cpp-samples.md) örneğinden:

[!code-cpp[NVC_ATL_COM#1](../../atl/codesnippet/cpp/com-map-macros_1.h)]

## <a name="end_com_map"></a><a name="end_com_map"></a>END_COM_MAP

COM arayüz haritanızın tanımını sona erdirer.

```
END_COM_MAP()
```

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar](../../atl/reference/atl-macros.md)<br/>
[COM Eşlemesi Genel İşlevleri](../../atl/reference/com-map-global-functions.md)
