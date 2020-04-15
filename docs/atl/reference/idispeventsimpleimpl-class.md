---
title: IDispEventSimpleImpl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- IDispEventSimpleImpl
- ATLCOM/ATL::IDispEventSimpleImpl
- ATLCOM/ATL::IDispEventSimpleImpl::Advise
- ATLCOM/ATL::IDispEventSimpleImpl::DispEventAdvise
- ATLCOM/ATL::IDispEventSimpleImpl::DispEventUnadvise
- ATLCOM/ATL::IDispEventSimpleImpl::GetIDsOfNames
- ATLCOM/ATL::IDispEventSimpleImpl::GetTypeInfo
- ATLCOM/ATL::IDispEventSimpleImpl::GetTypeInfoCount
- ATLCOM/ATL::IDispEventSimpleImpl::Invoke
- ATLCOM/ATL::IDispEventSimpleImpl::Unadvise
helpviewer_keywords:
- IDispEventSimpleImpl class
ms.assetid: 971d82b7-a921-47fa-a4d8-909bed377ab0
ms.openlocfilehash: 779e143094760c7bd868ad33f590f7fd8f004762
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329733"
---
# <a name="idispeventsimpleimpl-class"></a>IDispEventSimpleImpl Sınıfı

Bu sınıf, bir `IDispatch` tür kitaplığından tür bilgisi almadan yöntemlerin uygulamalarını sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <UINT nID, class T, const IID* pdiid>
class ATL_NO_VTABLE IDispEventSimpleImpl : public _IDispEventLocator<nID, pdiid>
```

#### <a name="parameters"></a>Parametreler

*Nıd*<br/>
Kaynak nesne için benzersiz bir tanımlayıcı. Bileşik `IDispEventSimpleImpl` denetimin taban sınıfı ne zaman, bu parametre için istenen denetimin kaynak kimliğini kullanın. Diğer durumlarda, rasgele pozitif tamsayı kullanın.

*T*<br/>
Kullanıcının sınıfından `IDispEventSimpleImpl`türetilen.

*pdiid*<br/>
Bu sınıf tarafından uygulanan olay dispinterface IID işaretçisi.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IDispEventSimpleImpl::Tavsiye](#advise)|Varsayılan olay kaynağıyla bir bağlantı kurar.|
|[IDispEventSimpleImpl::DispEventAdvise](#dispeventadvise)|Olay kaynağıyla bir bağlantı kurar.|
|[IDispEventSimpleImpl::DispEventUnadvise](#dispeventunadvise)|Olay kaynağıyla bağlantıyı koparır.|
|[IDispEventSimpleImpl::GetIDsOfNames](#getidsofnames)|E_NOTIMPL döndürür.|
|[IDispEventSimpleImpl::GetTypeInfo](#gettypeinfo)|E_NOTIMPL döndürür.|
|[IDispEventSimpleImpl::GetTypeInfoCount](#gettypeinfocount)|E_NOTIMPL döndürür.|
|[IDispEventSimpleImpl::Invoke](#invoke)|Olay lavabo haritasında listelenen olay işleyicilerini çağırır.|
|[IDispEventSimpleImpl::Tavsiye siz](#unadvise)|Varsayılan olay kaynağıyla bağlantıyı keser.|

## <a name="remarks"></a>Açıklamalar

`IDispEventSimpleImpl`bu arabirimdeki her yöntem/olay için uygulama kodu sağlamanızı gerektirmeden bir olay dispinterface uygulama yöntemi sağlar. `IDispEventSimpleImpl`yöntemlerin `IDispatch` uygulamalarını sağlar. Yalnızca işlemek le ilgilendiğiniz olaylar için uygulamalar sağlamanız gerekir.

`IDispEventSimpleImpl`olayları uygun işleyici işlevine yönlendirmek için sınıfınızdaki olay lavabo haritasıyla birlikte çalışır. Bu sınıfı kullanmak için:

- Işlemek istediğiniz her nesnedeki her olay için olay lavabo haritasına [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info) makro ekleyin.

- Her giriş için bir parametre olarak [bir işaretçi _ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md) yapısına geçirerek her olay için tür bilgileri kaynağı. x86 platformunda, `_ATL_FUNC_INFO.cc` değer, __stdcall geri arama işlevi ile CC_CDECL olmalıdır.

- Kaynak nesne ve taban sınıf arasındaki bağlantıyı kurmak için [DispEventAdvise'i](#dispeventadvise) arayın.

- Bağlantıyı kırmak için [DispEventUnadvise'i](#dispeventunadvise) arayın.

Olayları işlemek için `IDispEventSimpleImpl` gereken her nesne için *(nID*için benzersiz bir değer kullanarak) türetmeniz gerekir. Bir kaynak nesneye karşı tavsiyede sonra farklı bir kaynak nesneye karşı tavsiyede bulunabilir, ancak aynı anda tek bir nesne tarafından işlenebilecek `IDispEventSimpleImpl` en fazla kaynak nesne sayısı temel sınıf sayısıyla sınırlıdır.

`IDispEventSimplImpl`[IDispEventImpl](../../atl/reference/idispeventimpl-class.md)ile aynı işlevselliği sağlar, ancak bir tür kitaplığından arabirim hakkında tür bilgisi almaz. Sihirbazlar yalnızca , ancak `IDispEventImpl`kodu elle `IDispEventSimpleImpl` ekleyerek kod alabildiğinizi temel alarak kod oluştururlar. Olay `IDispEventSimpleImpl` arabirimini açıklayan bir tür kitaplığınız yoksa veya tür kitaplığını kullanmakla ilişkili genel merkezlerden kaçınmak istediğinizde kullanın.

> [!NOTE]
> `IDispEventImpl`ve `IDispEventSimpleImpl` ana COM `IUnknown::QueryInterface` nesnenizdeki `IDispEventImpl` sınıf `IDispEventSimpleImpl` üyelerine doğrudan erişim sağlarken, her bir veya taban sınıfın ayrı bir COM kimliği olarak hareket etmesini etkinleştirme uygulamalarını sağlar.

ActiveX olay lavabolarının CE ATL uygulaması yalnızca HRESULT türü veya olay işleyicisi yöntemlerinizden geçersiz olan iade değerlerini destekler; başka bir iade değeri desteklenmez ve davranışı tanımsızdır.

Daha fazla bilgi için Bkz. [IDispEventImpl'i Destekleme](../../atl/supporting-idispeventimpl.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`_IDispEvent`

`_IDispEventLocator`

`IDispEventSimpleImpl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="idispeventsimpleimpladvise"></a><a name="advise"></a>IDispEventSimpleImpl::Tavsiye

*pUnk*tarafından temsil edilen olay kaynağı ile bağlantı kurmak için bu yöntemi arayın.

```
HRESULT Advise(IUnknown* pUnk);
```

### <a name="parameters"></a>Parametreler

*Punk*<br/>
[içinde] Olay kaynağı `IUnknown` nesnenin arabirimine bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

S_OK veya herhangi bir hata HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bağlantı kurulduktan sonra, *pUnk'tan* ateşlenen olaylar, olay lavabo haritası ile sınıfınızdaki işleyicilere yönlendirilir.

> [!NOTE]
> Sınıfınız birden çok `IDispEventSimpleImpl` sınıftan türetiliyorsa, çağrıyı ilgilendiğiniz taban sınıfla birlikte kapsama alarak bu yönteme çağrıları ayrıştırmanız gerekir.

`Advise`varsayılan olay kaynağı ile bir bağlantı kurar, [atlGetObjectSourceInterface](composite-control-global-functions.md#atlgetobjectsourceinterface)tarafından belirlenen nesnenin varsayılan olay kaynağının IID alır.

## <a name="idispeventsimpleimpldispeventadvise"></a><a name="dispeventadvise"></a>IDispEventSimpleImpl::DispEventAdvise

*pUnk*tarafından temsil edilen olay kaynağı ile bağlantı kurmak için bu yöntemi arayın.

```
HRESULT DispEventAdvise(IUnknown* pUnk  const IID* piid);
```

### <a name="parameters"></a>Parametreler

*Punk*<br/>
[içinde] Olay kaynağı `IUnknown` nesnenin arabirimine bir işaretçi.

*piid*<br/>
Olay kaynağı nesnenin IID için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

S_OK veya herhangi bir hata HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Daha sonra, *pUnk'tan* ateşlenen olaylar, olay lavabo haritası ile sınıfınızdaki işleyicilere yönlendirilecektir.

> [!NOTE]
> Sınıfınız birden çok `IDispEventSimpleImpl` sınıftan türetiliyorsa, çağrıyı ilgilendiğiniz taban sınıfla birlikte kapsama alarak bu yönteme çağrıları ayrıştırmanız gerekir.

`DispEventAdvise`' de `pdiid`belirtilen olay kaynağı ile bir bağlantı kurar.

## <a name="idispeventsimpleimpldispeventunadvise"></a><a name="dispeventunadvise"></a>IDispEventSimpleImpl::DispEventUnadvise

*pUnk*tarafından temsil edilen olay kaynağı ile bağlantıyı bozar.

```
HRESULT DispEventUnadvise(IUnknown* pUnk  const IID* piid);
```

### <a name="parameters"></a>Parametreler

*Punk*<br/>
[içinde] Olay kaynağı `IUnknown` nesnenin arabirimine bir işaretçi.

*piid*<br/>
Olay kaynağı nesnenin IID için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

S_OK veya herhangi bir hata HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bağlantı koptuktan sonra, olaylar artık olay lavabo haritasında listelenen işleyici işlevlerine yönlendirilmez.

> [!NOTE]
> Sınıfınız birden çok `IDispEventSimpleImpl` sınıftan türetiliyorsa, çağrıyı ilgilendiğiniz taban sınıfla birlikte kapsama alarak bu yönteme çağrıları ayrıştırmanız gerekir.

`DispEventAdvise`'de `pdiid`belirtilen olay kaynağıyla kurulan bağlantıyı bozar.

## <a name="idispeventsimpleimplgetidsofnames"></a><a name="getidsofnames"></a>IDispEventSimpleImpl::GetIDsOfNames

İadelerin `IDispatch::GetIDsOfNames` bu uygulaması E_NOTIMPL.

```
STDMETHOD(GetIDsOfNames)(
    REFIID /* riid */,
    LPOLESTR* /* rgszNames */,
    UINT /* cNames */,
    LCID /* lcid */,
    DISPID* /* rgdispid */);
```

### <a name="remarks"></a>Açıklamalar

Bkz. IDispatch::Windows SDK'daki [GetIDsOfNames.](/windows/win32/api/oaidl/nf-oaidl-idispatch-getidsofnames)

## <a name="idispeventsimpleimplgettypeinfo"></a><a name="gettypeinfo"></a>IDispEventSimpleImpl::GetTypeInfo

İadelerin `IDispatch::GetTypeInfo` bu uygulaması E_NOTIMPL.

```
STDMETHOD(GetTypeInfo)(
    UINT /* itinfo */,
    LCID /* lcid */,
    ITypeInfo** /* pptinfo */);
```

### <a name="remarks"></a>Açıklamalar

Bkz. IDispatch::Windows SDK'da [TypeInfo'yu alın.](/windows/win32/api/oaidl/nf-oaidl-idispatch-gettypeinfo)

## <a name="idispeventsimpleimplgettypeinfocount"></a><a name="gettypeinfocount"></a>IDispEventSimpleImpl::GetTypeInfoCount

İadelerin `IDispatch::GetTypeInfoCount` bu uygulaması E_NOTIMPL.

```
STDMETHOD(GetTypeInfoCount)(UINT* /* pctinfo */);
```

### <a name="remarks"></a>Açıklamalar

Bkz. IDispatch::Windows SDK'da [TypeInfoCount'u alın.](/windows/win32/api/oaidl/nf-oaidl-idispatch-gettypeinfocount)

## <a name="idispeventsimpleimplinvoke"></a><a name="invoke"></a>IDispEventSimpleImpl::Invoke

Bu uygulama, olay lavabo haritasında listelenen olay işleyicilerini `IDispatch::Invoke` çağırır.

```
STDMETHOD(Invoke)(
    DISPID dispidMember,
    REFIID /* riid */,
    LCID lcid,
    WORD /* wFlags */,
    DISPPARMS* pdispparams,
    VARIANT* pvarResult,
    EXCEPINFO* /* pexcepinfo */,
    UINT* /* puArgErr */);
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IDispatch::Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke).

## <a name="idispeventsimpleimplunadvise"></a><a name="unadvise"></a>IDispEventSimpleImpl::Tavsiye siz

*pUnk*tarafından temsil edilen olay kaynağı ile bağlantıyı bozar.

```
HRESULT Unadvise(IUnknown* pUnk);
```

### <a name="parameters"></a>Parametreler

*Punk*<br/>
[içinde] Olay kaynağı `IUnknown` nesnenin arabirimine bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

S_OK veya herhangi bir hata HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bağlantı koptuktan sonra, olaylar artık olay lavabo haritasında listelenen işleyici işlevlerine yönlendirilmez.

> [!NOTE]
> Sınıfınız birden çok `IDispEventSimpleImpl` sınıftan türetiliyorsa, çağrıyı ilgilendiğiniz taban sınıfla birlikte kapsama alarak bu yönteme çağrıları ayrıştırmanız gerekir.

`Unadvise`'de `pdiid`belirtilen varsayılan olay kaynağıyla kurulan bağlantıyı bozar.

`Unavise`varsayılan olay kaynağı ile bir bağlantı tatili, [atlGetObjectSourceInterface](composite-control-global-functions.md#atlgetobjectsourceinterface)tarafından belirlenen nesnenin varsayılan olay kaynağının IID alır.

## <a name="see-also"></a>Ayrıca bkz.

[_ATL_FUNC_INFO Yapısı](../../atl/reference/atl-func-info-structure.md)<br/>
[IDispatchImpl Sınıfı](../../atl/reference/idispatchimpl-class.md)<br/>
[IDispEventImpl Sınıfı](../../atl/reference/idispeventimpl-class.md)<br/>
[SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
