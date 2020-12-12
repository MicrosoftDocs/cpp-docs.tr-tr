---
description: 'Daha fazla bilgi edinin: bileşik denetim makroları'
title: Bileşik denetim makroları
ms.date: 05/06/2019
f1_keywords:
- atlcom/ATL::BEGIN_SINK_MAP
- atlcom/ATL::END_SINK_MAP
- atlcom/ATL::SINK_ENTRY
helpviewer_keywords:
- composite controls, macros
ms.assetid: 17f2dd5e-07e6-4aa6-b965-7a361c78c45e
ms.openlocfilehash: 0107f91350516bd0f7e35cf82a49f79ff3c5797e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141199"
---
# <a name="composite-control-macros"></a>Bileşik denetim makroları

Bu makrolar olay havuzu haritalarını ve girdilerini tanımlar.

|Makroya|Açıklama|
|-|-|
|[BEGIN_SINK_MAP](#begin_sink_map)|Bileşik denetim için olay havuzu haritasının başlangıcını işaretler.|
|[END_SINK_MAP](#end_sink_map)|Bileşik denetim için olay havuzu haritasının sonunu işaretler.|
|[SINK_ENTRY](#sink_entry)|Olay havuzu eşleme girişi.|
|[SINK_ENTRY_EX](#sink_entry_ex)|Olay havuzu eşlemesine ek bir parametreyle giriş.|
|[SINK_ENTRY_EX_P](#sink_entry_ex)| (Visual Studio 2017) SINK_ENTRY_EX benzer bir şekilde, IID için bir işaretçi sürer.|
|[SINK_ENTRY_INFO](#sink_entry_info)|[IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)ile kullanmak üzere el ile sağlanan tür bilgileriyle olay havuzu eşlemesine giriş.|
|[SINK_ENTRY_INFO_P](#sink_entry_info)| (Visual Studio 2017) SINK_ENTRY_INFO benzer bir şekilde, IID için bir işaretçi sürer.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

## <a name="begin_sink_map"></a><a name="begin_sink_map"></a> BEGIN_SINK_MAP

Bileşik denetim için olay havuzu haritasının başlangıcını bildirir.

```
BEGIN_SINK_MAP(_class)
```

### <a name="parameters"></a>Parametreler

*_class*<br/>
'ndaki Denetimi belirtir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]

### <a name="remarks"></a>Açıklamalar

ActiveX olay havuzları 'nın CE ATL uygulamasında yalnızca HRESULT veya olay işleyicisi yöntemlerinizin void türü dönüş değerleri desteklenir; diğer bir dönüş değeri desteklenmez ve davranışı tanımsız olur.

## <a name="end_sink_map"></a><a name="end_sink_map"></a> END_SINK_MAP

Bileşik denetim için olay havuzu haritasının sonunu bildirir.

```
END_SINK_MAP()
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]

### <a name="remarks"></a>Açıklamalar

ActiveX olay havuzları 'nın CE ATL uygulamasında yalnızca HRESULT veya olay işleyicisi yöntemlerinizin void türü dönüş değerleri desteklenir; diğer bir dönüş değeri desteklenmez ve davranışı tanımsız olur.

## <a name="sink_entry"></a><a name="sink_entry"></a> SINK_ENTRY

*Kimliği* tarafından tanımlanan denetimin belirtilen olay (*DISPID*) için işleyici işlevini (*FN*) bildirir.

```
SINK_ENTRY( id, dispid, fn )
```

### <a name="parameters"></a>Parametreler

*id*<br/>
'ndaki Denetimi tanımlar.

*dı*<br/>
'ndaki Belirtilen olayı tanımlar.

*FN*<br/>
'ndaki Olay işleyicisi işlevinin adı. Bu işlev, `_stdcall` çağırma kuralını kullanmalıdır ve uygun dispınterface stili imzaya sahip olmalıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]

### <a name="remarks"></a>Açıklamalar

ActiveX olay havuzları 'nın CE ATL uygulamasında yalnızca HRESULT veya olay işleyicisi yöntemlerinizin void türü dönüş değerleri desteklenir; diğer bir dönüş değeri desteklenmez ve davranışı tanımsız olur.

## <a name="sink_entry_ex-and-sink_entry_ex_p"></a><a name="sink_entry_ex"></a> SINK_ENTRY_EX ve SINK_ENTRY_EX_P

*Kimliğe* göre tanımlanan denetim için, dağıtım arabiriminin (*IID*) belirtilen olay (*DISPID*) için işleyici işlevini (*FN*) bildirir.

```
SINK_ENTRY_EX( id, iid, dispid, fn )
SINK_ENTRY_EX_P( id, piid, dispid, fn ) // (Visual Studio 2017)
```

### <a name="parameters"></a>Parametreler

*id*<br/>
'ndaki Denetimi tanımlar.

*'si*<br/>
'ndaki Dağıtım arabirimini tanımlar.

*piıd*<br/>
'ndaki Dağıtım arabirimine yönelik işaretçi.

*dı*<br/>
'ndaki Belirtilen olayı tanımlar.

*FN*<br/>
'ndaki Olay işleyicisi işlevinin adı. Bu işlev, `_stdcall` çağırma kuralını kullanmalıdır ve uygun dispınterface stili imzaya sahip olmalıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#136](../../atl/codesnippet/cpp/composite-control-macros_2.h)]

### <a name="remarks"></a>Açıklamalar

ActiveX olay havuzları 'nın CE ATL uygulamasında yalnızca HRESULT veya olay işleyicisi yöntemlerinizin void türü dönüş değerleri desteklenir; diğer bir dönüş değeri desteklenmez ve davranışı tanımsız olur.

## <a name="sink_entry_info-and-sink_entry_info_p"></a><a name="sink_entry_info"></a> SINK_ENTRY_INFO ve SINK_ENTRY_INFO_P

Olayları ilgili işleyici işlevine yönlendirmek için [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) tarafından gereken bilgileri sağlamak üzere bir olay havuzu eşlemesi içindeki SINK_ENTRY_INFO makrosunu kullanın.

```
SINK_ENTRY_INFO( id, iid, dispid, fn, info )
SINK_ENTRY_INFO_P( id, piid, dispid, fn, info ) // (Visual Studio 2017)
```

### <a name="parameters"></a>Parametreler

*id*<br/>
'ndaki Olay kaynağını tanımlayan işaretsiz tamsayı. Bu değer, ilişkili [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) temel sınıfında kullanılan *NID* şablon parametresiyle eşleşmelidir.

*'si*<br/>
'ndaki Dağıtım arabirimini tanımlayan IID.

*piıd*<br/>
'ndaki Dağıtım arabirimini tanımlayan IID 'ye yönelik işaretçi.

*dı*<br/>
'ndaki Belirtilen olayı belirten DISPID.

*FN*<br/>
'ndaki Olay işleyicisi işlevinin adı. Bu işlev, `_stdcall` çağırma kuralını kullanmalıdır ve uygun dispınterface stili imzaya sahip olmalıdır.

*bilgisine*<br/>
'ndaki Olay işleyicisi işlevinin bilgilerini yazın. Bu tür bilgileri, bir yapının işaretçisi biçiminde sağlanır `_ATL_FUNC_INFO` . CC_CDECL, yapının CALLCONV alanı için Windows CE desteklenen tek seçenektir `_ATL_FUNC_INFO` . Başka herhangi bir değer desteklenmez, dolayısıyla davranışı tanımsız olur.

### <a name="remarks"></a>Açıklamalar

İlk dört makro parametresi, [SINK_ENTRY_EX](#sink_entry_ex) makrodakilerle aynıdır. Son parametresi, olay için tür bilgilerini sağlar. ActiveX olay havuzları 'nın CE ATL uygulamasında yalnızca HRESULT veya olay işleyicisi yöntemlerinizin void türü dönüş değerleri desteklenir; diğer bir dönüş değeri desteklenmez ve davranışı tanımsız olur.

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar](../../atl/reference/atl-macros.md)<br/>
[Bileşik denetim genel Işlevleri](../../atl/reference/composite-control-global-functions.md)
