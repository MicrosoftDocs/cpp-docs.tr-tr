---
title: COM eşleme makroları
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_COM_MAP
- atlcom/ATL::END_COM_MAP
helpviewer_keywords:
- COM interfaces, COM map macros
ms.assetid: 0f33656d-321f-4996-90cc-9a7f21ab73c3
ms.openlocfilehash: 3159a53b5a500aa61b85cf2bc5a97d321ed6ebb5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62245627"
---
# <a name="com-map-macros"></a>COM eşleme makroları

Bu makrolar COM arabirim eşlemeleri tanımlayın.

|||
|-|-|
|[BEGIN_COM_MAP](#begin_com_map)|COM arabirim eşleme girişleri başlangıcını işaretler.|
|[END_COM_MAP](#end_com_map)|COM arabirim eşleme girişleri sonunu işaretler.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

##  <a name="begin_com_map"></a>  BEGIN_COM_MAP

COM eşlemesi üzerinden bir istemciye bir nesne üzerinde arabirimleri kullanıma açıp mekanizmadır `QueryInterface`.

```
BEGIN_COM_MAP(x)
```

### <a name="parameters"></a>Parametreler

*x*<br/>
[in] Üzerinde arabirimleri kullanıma sunma sınıfı nesnesinin adı.

### <a name="remarks"></a>Açıklamalar

[CComObjectRootEx::InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface) yalnızca arabirim işaretçilerini içindeki COM eşlemesine döndürür. Arabirim eşlemenize BEGIN_COM_MAP makrosu ile Başlat, ile arabirimlerinizin her biri için girişler ekleyin [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) makrosu veya türevleri, biri ve haritayla tamamlamak [END_COM_MAP](#end_com_map) Makro.

### <a name="example"></a>Örnek

ATL gelen [sesli İKAZ](../../overview/visual-cpp-samples.md) örnek:

[!code-cpp[NVC_ATL_COM#1](../../atl/codesnippet/cpp/com-map-macros_1.h)]

##  <a name="end_com_map"></a>  END_COM_MAP

COM arabirim eşlemenize tanımını sonlandırır.

```
END_COM_MAP()
```

## <a name="see-also"></a>Ayrıca bkz.

[Makroları](../../atl/reference/atl-macros.md)<br/>
[COM Eşlemesi Genel İşlevleri](../../atl/reference/com-map-global-functions.md)
