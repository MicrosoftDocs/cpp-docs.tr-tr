---
title: Bileşik Denetim Makroları
ms.date: 05/06/2019
f1_keywords:
- atlcom/ATL::BEGIN_SINK_MAP
- atlcom/ATL::END_SINK_MAP
- atlcom/ATL::SINK_ENTRY
helpviewer_keywords:
- composite controls, macros
ms.assetid: 17f2dd5e-07e6-4aa6-b965-7a361c78c45e
ms.openlocfilehash: 67ad18c07a92cfecca44667908a8488e8c2da234
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331512"
---
# <a name="composite-control-macros"></a>Bileşik Denetim Makroları

Bu makrolar olay lavabo haritaları ve girişleri tanımlar.

|||
|-|-|
|[BEGIN_SINK_MAP](#begin_sink_map)|Bileşik denetim için olay lavabo haritasının başlangıcını işaretler.|
|[END_SINK_MAP](#end_sink_map)|Bileşik denetim için olay lavabo haritasının sonunu işaretler.|
|[SINK_ENTRY](#sink_entry)|Olay lavabo haritasına giriş.|
|[SINK_ENTRY_EX](#sink_entry_ex)|Ek bir parametre ile olay lavabo haritasına giriş.|
|[SINK_ENTRY_EX_P](#sink_entry_ex)| (Visual Studio 2017) Iid için bir işaretçi alır dışında SINK_ENTRY_EX benzer.|
|[SINK_ENTRY_INFO](#sink_entry_info)|[IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)ile kullanılmak üzere manuel olarak verilen tip bilgileri ile olay lavabo haritasına giriş .|
|[SINK_ENTRY_INFO_P](#sink_entry_info)| (Visual Studio 2017) Iid için bir işaretçi alır dışında SINK_ENTRY_INFO benzer.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="begin_sink_map"></a><a name="begin_sink_map"></a>BEGIN_SINK_MAP

Bileşik denetim için olay lavabo haritasının başlangıcını bildirir.

```
BEGIN_SINK_MAP(_class)
```

### <a name="parameters"></a>Parametreler

*_class*<br/>
[içinde] Denetimi belirtir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]

### <a name="remarks"></a>Açıklamalar

ActiveX olay lavabolarının CE ATL uygulaması yalnızca HRESULT türü veya olay işleyicisi yöntemlerinizden geçersiz olan iade değerlerini destekler; başka bir iade değeri desteklenmez ve davranışı tanımsızdır.

## <a name="end_sink_map"></a><a name="end_sink_map"></a>END_SINK_MAP

Bileşik denetim için olay lavabo haritasının sonunu bildirir.

```
END_SINK_MAP()
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]

### <a name="remarks"></a>Açıklamalar

ActiveX olay lavabolarının CE ATL uygulaması yalnızca HRESULT türü veya olay işleyicisi yöntemlerinizden geçersiz olan iade değerlerini destekler; başka bir iade değeri desteklenmez ve davranışı tanımsızdır.

## <a name="sink_entry"></a><a name="sink_entry"></a>SINK_ENTRY

Id *tarafından*tanımlanan denetimin belirtilen olay *(dispid),* için işleyici işlevini (*fn*) bildirir.

```
SINK_ENTRY( id, dispid, fn )
```

### <a name="parameters"></a>Parametreler

*Kimliği*<br/>
[içinde] Denetimi tanımlar.

*Dıspıd*<br/>
[içinde] Belirtilen olayı tanımlar.

*Fn*<br/>
[içinde] Olay işleyicisi işlevinin adı. Bu işlev, `_stdcall` çağrı kuralını kullanmalı ve uygun dispinterface tarzı imzaya sahip olmalıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]

### <a name="remarks"></a>Açıklamalar

ActiveX olay lavabolarının CE ATL uygulaması yalnızca HRESULT türü veya olay işleyicisi yöntemlerinizden geçersiz olan iade değerlerini destekler; başka bir iade değeri desteklenmez ve davranışı tanımsızdır.

## <a name="sink_entry_ex-and-sink_entry_ex_p"></a><a name="sink_entry_ex"></a>SINK_ENTRY_EX ve SINK_ENTRY_EX_P

Id *tarafından*tanımlanan denetim için, sevk arabiriminin *(iid)* belirtilen olay *(dispid),* için işleyici işlevini (*fn*) bildirir.

```
SINK_ENTRY_EX( id, iid, dispid, fn )
SINK_ENTRY_EX_P( id, piid, dispid, fn ) // (Visual Studio 2017)
```

### <a name="parameters"></a>Parametreler

*Kimliği*<br/>
[içinde] Denetimi tanımlar.

*ııd*<br/>
[içinde] Gönderme arabirimini tanımlar.

*piid*<br/>
[içinde] Gönderme arabirimine işaretçi.

*Dıspıd*<br/>
[içinde] Belirtilen olayı tanımlar.

*Fn*<br/>
[içinde] Olay işleyicisi işlevinin adı. Bu işlev, `_stdcall` çağrı kuralını kullanmalı ve uygun dispinterface tarzı imzaya sahip olmalıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#136](../../atl/codesnippet/cpp/composite-control-macros_2.h)]

### <a name="remarks"></a>Açıklamalar

ActiveX olay lavabolarının CE ATL uygulaması yalnızca HRESULT türü veya olay işleyicisi yöntemlerinizden geçersiz olan iade değerlerini destekler; başka bir iade değeri desteklenmez ve davranışı tanımsızdır.

## <a name="sink_entry_info-and-sink_entry_info_p"></a><a name="sink_entry_info"></a>SINK_ENTRY_INFO ve SINK_ENTRY_INFO_P

Olayları ilgili işleyici işlevine yönlendirmek için [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) tarafından gerekli bilgileri sağlamak için bir olay lavabo haritası ndaki SINK_ENTRY_INFO makroyu kullanın.

```
SINK_ENTRY_INFO( id, iid, dispid, fn, info )
SINK_ENTRY_INFO_P( id, piid, dispid, fn, info ) // (Visual Studio 2017)
```

### <a name="parameters"></a>Parametreler

*Kimliği*<br/>
[içinde] Olay kaynağını tanımlayan imzasız bir insa. Bu değer, ilgili [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) taban sınıfında kullanılan *nID* şablon parametresi ile eşleşmelidir.

*ııd*<br/>
[içinde] Gönderme arabirimini tanımlayan IID.

*piid*<br/>
[içinde] Sevk arabirimini tanımlayan IID işaretçisi.

*Dıspıd*<br/>
[içinde] DISPID belirtilen olayı tanımlıyor.

*Fn*<br/>
[içinde] Olay işleyicisi işlevinin adı. Bu işlev, `_stdcall` çağrı kuralını kullanmalı ve uygun dispinterface tarzı imzaya sahip olmalıdır.

*Bilgi*<br/>
[içinde] Olay işleyicisi işlevi için bilgi yazın. Bu tür bilgiler bir `_ATL_FUNC_INFO` yapıya işaretçi şeklinde sağlanır. `_ATL_FUNC_INFO` CC_CDECL, yapının CALLCONV alanı için Windows CE'de desteklenen tek seçenektir. Başka bir değer desteklenmez, bu nedenle davranışı tanımsızdır.

### <a name="remarks"></a>Açıklamalar

İlk dört makro parametreleri [SINK_ENTRY_EX](#sink_entry_ex) makro için aynıdır. Son parametre olay için tür bilgileri sağlar. ActiveX olay lavabolarının CE ATL uygulaması yalnızca HRESULT türü veya olay işleyicisi yöntemlerinizden geçersiz olan iade değerlerini destekler; başka bir iade değeri desteklenmez ve davranışı tanımsızdır.

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar](../../atl/reference/atl-macros.md)<br/>
[Kompozit Kontrol Küresel Fonksiyonlar](../../atl/reference/composite-control-global-functions.md)
