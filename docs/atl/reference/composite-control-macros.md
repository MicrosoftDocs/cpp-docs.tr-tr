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
ms.openlocfilehash: 352f3e5ebd9606cc355ea9af65739c3e17894298
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46136302"
---
# <a name="composite-control-macros"></a>Bileşik Denetim makroları

Olay iç havuz eşlemeleri ve girişleri bu makroları tanımlar.

|||
|-|-|
|[BEGIN_SINK_MAP](#begin_sink_map)|Bileşik denetim için olay havuzu eşlemesi başlangıcını işaretler.|
|[END_SINK_MAP](#end_sink_map)|Bileşik denetim için olay havuzu eşlemesi sonunu işaretler.|
|[SINK_ENTRY](#sink_entry)|Olay havuzu eşleme girişi.|
|[SINK_ENTRY_EX](#sink_entry_ex)|Ek bir parametre ile olay havuzu eşleme girişi.|
|[SINK_ENTRY_EX_P](#sink_entry_ex)| (Visual Studio 2017) IID için bir işaretçi alır dışında SINK_ENTRY_EX için benzer.|
|[SINK_ENTRY_INFO](#sink_entry_info)|Olay havuzu eşlemesi ile kullanmak için el ile sağlanan tür bilgileriyle girişe [Idispeventsimpleımpl](../../atl/reference/idispeventsimpleimpl-class.md).|
|[SINK_ENTRY_INFO_P](#sink_entry_info)| (Visual Studio 2017) IID için bir işaretçi alır dışında SINK_ENTRY_INFO için benzer.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h  

##  <a name="begin_sink_map"></a>  BEGIN_SINK_MAP

Bileşik denetim için olay havuzu eşleme başına bildirir.

```
BEGIN_SINK_MAP(_class)
```

### <a name="parameters"></a>Parametreler

*_sınıfı*<br/>
[in] Denetimi belirtir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]

### <a name="remarks"></a>Açıklamalar

ActiveX olayı havuzlarını yalnızca destekler dönüş türü değerlerinin HRESULT ya da geçersiz kılma, olay işleyicisi yöntemleri gelen CE ATL uygulaması; herhangi bir dönüş değeri desteklenmiyor ve davranışı tanımlanmamış olur.

##  <a name="end_sink_map"></a>  END_SINK_MAP

Bileşik denetim için olay havuzu eşlemesi sonuna bildirir.

```
END_SINK_MAP()
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]

### <a name="remarks"></a>Açıklamalar

ActiveX olayı havuzlarını yalnızca destekler dönüş türü değerlerinin HRESULT ya da geçersiz kılma, olay işleyicisi yöntemleri gelen CE ATL uygulaması; herhangi bir dönüş değeri desteklenmiyor ve davranışı tanımlanmamış olur.

##  <a name="sink_entry"></a>  SINK_ENTRY

İşleyici işlev bildirir (*fn*) belirtilen olayın (*DISPID*), denetimi tarafından tanımlanan *kimliği*.

```
SINK_ENTRY( id, dispid, fn )
```

### <a name="parameters"></a>Parametreler

*id*<br/>
[in] Denetimi tanımlar.

*DISPID*<br/>
[in] Belirtilen olay tanımlar.

*fn*<br/>
[in] Olay işleyici işlevinin adı. Bu işlev kullanmalısınız `_stdcall` çağırma kuralı ve uygun dispinterface stili imzaya sahip.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]

### <a name="remarks"></a>Açıklamalar

ActiveX olayı havuzlarını yalnızca destekler dönüş türü değerlerinin HRESULT ya da geçersiz kılma, olay işleyicisi yöntemleri gelen CE ATL uygulaması; herhangi bir dönüş değeri desteklenmiyor ve davranışı tanımlanmamış olur.

##  <a name="sink_entry_ex"></a>  SINK_ENTRY_EX ve SINK_ENTRY_EX_P

İşleyici işlev bildirir (*fn*) belirtilen olayın (*DISPID*), gönderme arabirimi (*IID*), tarafından tanımlanan denetimi için *kimliği*.

```
SINK_ENTRY_EX( id, iid, dispid, fn )
SINK_ENTRY_EX_P( id, piid, dispid, fn ) // (Visual Studio 2017)
```

### <a name="parameters"></a>Parametreler

*id*<br/>
[in] Denetimi tanımlar.

*IID*<br/>
[in] Dağıtım arabirimi tanımlar.  

*piid*<br/>
[in] Gönderme arabirim işaretçisi.

*DISPID*<br/>
[in] Belirtilen olay tanımlar.

*fn*<br/>
[in] Olay işleyici işlevinin adı. Bu işlev kullanmalısınız `_stdcall` çağırma kuralı ve uygun dispinterface stili imzaya sahip.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#136](../../atl/codesnippet/cpp/composite-control-macros_2.h)]

### <a name="remarks"></a>Açıklamalar

ActiveX olayı havuzlarını yalnızca destekler dönüş türü değerlerinin HRESULT ya da geçersiz kılma, olay işleyicisi yöntemleri gelen CE ATL uygulaması; herhangi bir dönüş değeri desteklenmiyor ve davranışı tanımlanmamış olur.

##  <a name="sink_entry_info"></a>  SINK_ENTRY_INFO ve SINK_ENTRY_INFO_P

Gerekli bilgileri sağlamak için bir olay havuzu eşlemesi içinde SINK_ENTRY_INFO makrosu kullanma [Idispeventsimpleımpl](../../atl/reference/idispeventsimpleimpl-class.md) ilgili işleyici işlevi için rota olayları.

```
SINK_ENTRY_INFO( id, iid, dispid, fn, info )
SINK_ENTRY_INFO_P( id, piid, dispid, fn, info ) // (Visual Studio 2017)
```

### <a name="parameters"></a>Parametreler

*id*<br/>
[in] Olay kaynağını belirleme işaretsiz tamsayı. Bu değer eşleşmelidir *nID* şablon parametresi ilgili kullanılan [Idispeventsimpleımpl](../../atl/reference/idispeventsimpleimpl-class.md) temel sınıfı.

*IID*<br/>
[in] Bu IID gönderme arabirimi tanımlar.  

*piid*<br/>
[in] Gönderme arabirim tanımlayan IID işaretçisi.

*DISPID*<br/>
[in] DISPID belirtilen olay tanımlama.

*fn*<br/>
[in] Olay işleyici işlevinin adı. Bu işlev kullanmalısınız `_stdcall` çağırma kuralı ve uygun dispinterface stili imzaya sahip.

*Bilgileri*<br/>
[in] Olay işleyici işlevi bilgilerini yazın. Bu tür bilgiler için bir işaretçi biçiminde sağlanan bir `_ATL_FUNC_INFO` yapısı. Windows CE sahip alanın için desteklenen tek seçenek CC_CDECL olduğu `_ATL_FUNC_INFO` yapısı. Başka bir değer desteklenmiyor bu nedenle, davranışı tanımsız.

### <a name="remarks"></a>Açıklamalar

İlk dört makro parametrelerini için aynıdır [SINK_ENTRY_EX](#sink_entry_ex) makrosu. Son parametresi, olay için tür bilgisini sağlar. ActiveX olayı havuzlarını yalnızca destekler dönüş türü değerlerinin HRESULT ya da geçersiz kılma, olay işleyicisi yöntemleri gelen CE ATL uygulaması; herhangi bir dönüş değeri desteklenmiyor ve davranışı tanımlanmamış olur.

## <a name="see-also"></a>Ayrıca Bkz.

[Makroları](../../atl/reference/atl-macros.md)<br/>
[Bileşik Denetim Genel İşlevleri](../../atl/reference/composite-control-global-functions.md)
