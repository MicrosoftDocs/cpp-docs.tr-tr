---
title: COM eşleme makroları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcom/ATL::BEGIN_COM_MAP
- atlcom/ATL::END_COM_MAP
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, COM map macros
ms.assetid: 0f33656d-321f-4996-90cc-9a7f21ab73c3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 69838a690fcdddc58194caf38e3666fef023222c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46028057"
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

ATL gelen [sesli İKAZ](../../visual-cpp-samples.md) örnek:

[!code-cpp[NVC_ATL_COM#1](../../atl/codesnippet/cpp/com-map-macros_1.h)]

##  <a name="end_com_map"></a>  END_COM_MAP

COM arabirim eşlemenize tanımını sonlandırır.

```
END_COM_MAP()
```

## <a name="see-also"></a>Ayrıca Bkz.

[Makroları](../../atl/reference/atl-macros.md)<br/>
[COM Eşlemesi Genel İşlevleri](../../atl/reference/com-map-global-functions.md)
