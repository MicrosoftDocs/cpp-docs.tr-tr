---
title: Bileşik Denetim makroları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcom/ATL::BEGIN_SINK_MAP
- atlcom/ATL::END_SINK_MAP
- atlcom/ATL::SINK_ENTRY
dev_langs:
- C++
helpviewer_keywords:
- composite controls, macros
ms.assetid: 17f2dd5e-07e6-4aa6-b965-7a361c78c45e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 61335d25b0d9b97fe1c7e9915aa9c3d8583eb854
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="composite-control-macros"></a>Bileşik Denetim makroları
Olay iç havuz eşlemeleri ve girişleri bu makroları tanımlayın.  
  
|||  
|-|-|  
|[BEGIN_SINK_MAP](#begin_sink_map)|Bileşik denetim için olay havuz eşlemesi başlangıcını işaretler.|  
|[END_SINK_MAP](#end_sink_map)|Bileşik denetim için olay havuz eşlemesi sonunu işaretler.|  
|[SINK_ENTRY](#sink_entry)|Olay iç havuz eşlemesi girdi.|  
|[SINK_ENTRY_EX](#sink_entry_ex)|Olay iç havuz eşlemesi ek bir parametre ile bir girdi.| 
|[SINK_ENTRY_EX_P](#sink_entry_ex)| (Visual Studio 2017) Benzer şekilde SINK_ENTRY_EX IID gösteren bir işaretçi sürdüğünü dışında.|  
|[SINK_ENTRY_INFO](#sink_entry_info)|Olay havuz eşlemesi ile kullanılmak üzere el ile sağlanan tür bilgilerle girişe [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md).|  
|[SINK_ENTRY_INFO_P](#sink_entry_info)| (Visual Studio 2017) Benzer şekilde SINK_ENTRY_INFO IID gösteren bir işaretçi sürdüğünü dışında.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  

##  <a name="begin_sink_map"></a>  BEGIN_SINK_MAP  
 Bileşik denetim için olay havuz eşlemesi başlangıcını bildirir.  
  
```
BEGIN_SINK_MAP(_class)
```  
  
### <a name="parameters"></a>Parametreler  
 `_class`  
 [in] Denetim belirtir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]  
  
### <a name="remarks"></a>Açıklamalar  
 ActiveX olay havuzlarını yalnızca destekler dönüş türü değerleri HRESULT ya da olay işleyicisi yöntemlerden void uyarlamasını CE ATL; herhangi bir dönüş değeri desteklenmez ve davranışını tanımlanmadı.  
  
##  <a name="end_sink_map"></a>  END_SINK_MAP  
 Bileşik denetim için olay havuz eşlemesi sonuna bildirir.  
  
```
END_SINK_MAP()
```  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]  
  
### <a name="remarks"></a>Açıklamalar  
 ActiveX olay havuzlarını yalnızca destekler dönüş türü değerleri HRESULT ya da olay işleyicisi yöntemlerden void uyarlamasını CE ATL; herhangi bir dönüş değeri desteklenmez ve davranışını tanımlanmadı.  
  
##  <a name="sink_entry"></a>  SINK_ENTRY  
 İşleyici işlevi bildirir ( `fn`) belirtilen olay için ( `dispid`), tarafından tanımlanan denetiminin `id`.  
  
```
SINK_ENTRY( id, dispid, fn )
```  
  
### <a name="parameters"></a>Parametreler  
 `id`  
 [in] Denetim tanımlar.  
  
 `dispid`  
 [in] Belirtilen olay tanımlar.  
  
 `fn`  
 [in] Olay işleyici işlevinin adı. Bu işlev kullanmalısınız **_stdcall** çağırma ve uygun görüntüleme arabirimi stili imzaya sahip.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]  
  
### <a name="remarks"></a>Açıklamalar  
 ActiveX olay havuzlarını yalnızca destekler dönüş türü değerleri HRESULT ya da olay işleyicisi yöntemlerden void uyarlamasını CE ATL; herhangi bir dönüş değeri desteklenmez ve davranışını tanımlanmadı.  
  
##  <a name="sink_entry_ex"></a>  SINK_ENTRY_EX ve SINK_ENTRY_EX_P
 İşleyici işlevi bildirir ( `fn`) belirtilen olay için ( `dispid`), gönderme arabiriminin ( *IID)*, tarafından tanımlanan denetimi için `id`.  
  
```
SINK_ENTRY_EX( id, iid, dispid, fn )
SINK_ENTRY_EX_P( id, piid, dispid, fn ) // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>Parametreler  
 `id`  
 [in] Denetim tanımlar.  
  
 `iid`  
 [in] Gönderme arabirimi tanımlar.  

 `piid`  
 [in] Gönderme arabirimi işaretçisi.  
  
 `dispid`  
 [in] Belirtilen olay tanımlar.  
  
 `fn`  
 [in] Olay işleyici işlevinin adı. Bu işlev kullanmalısınız **_stdcall** çağırma ve uygun görüntüleme arabirimi stili imzaya sahip.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#136](../../atl/codesnippet/cpp/composite-control-macros_2.h)]  
  
### <a name="remarks"></a>Açıklamalar  
 ActiveX olay havuzlarını yalnızca destekler dönüş türü değerleri HRESULT ya da olay işleyicisi yöntemlerden void uyarlamasını CE ATL; herhangi bir dönüş değeri desteklenmez ve davranışını tanımlanmadı.  
  
##  <a name="sink_entry_info"></a>  SINK_ENTRY_INFO ve SINK_ENTRY_INFO_P  
 Kullanım `SINK_ENTRY_INFO` makrosu için gerekli bilgileri sağlamak için bir olay havuz eşlemesi içinde [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) rota olaylarla ilgili işleyici işlevi.  
  
```
SINK_ENTRY_INFO( id, iid, dispid, fn, info )
SINK_ENTRY_INFO_P( id, piid, dispid, fn, info ) // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>Parametreler  
 `id`  
 [in] Olay kaynağı tanımlayan imzasız tam sayı. Bu değer eşleşmelidir `nID` ilgili kullanılan şablon parametresi [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) temel sınıfı.  
  
 `iid`  
 [in] Gönderme arabirimi tanımlayan IID.  

 `piid`  
 [in] Gönderme arabirimi tanımlayan IID işaretçi.
  
 `dispid`  
 [in] Belirtilen olay tanımlama DISPID.  
  
 `fn`  
 [in] Olay işleyici işlevinin adı. Bu işlev kullanmalısınız **_stdcall** çağırma ve uygun görüntüleme arabirimi stili imzaya sahip.  
  
 `info`  
 [in] Olay işleyici işlevi bilgilerini yazın. Bu tür bilgiler gösteren bir işaretçi biçiminde sağlanır bir `_ATL_FUNC_INFO` yapısı. `CC_CDECL` Windows CE için desteklenen tek seçenek `CALLCONV` alanını `_ATL_FUNC_INFO` yapısı. Başka bir değer desteklenmiyor böylece davranışını tanımlanmamış.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk dört makrosu parametreleri için aynıdır [SINK_ENTRY_EX](#sink_entry_ex) makrosu. Son parametre olayı için tür bilgiler sağlar. ActiveX olay havuzlarını yalnızca destekler dönüş türü değerleri HRESULT ya da olay işleyicisi yöntemlerden void uyarlamasını CE ATL; herhangi bir dönüş değeri desteklenmez ve davranışını tanımlanmadı.  
  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları](../../atl/reference/atl-macros.md)   
 [Bileşik Denetim Genel İşlevleri](../../atl/reference/composite-control-global-functions.md)
