---
title: Idispeventsimpleımpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- IDispEventSimpleImpl class
ms.assetid: 971d82b7-a921-47fa-a4d8-909bed377ab0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 68e6b4730be3679e4309a298d40657dcecde94b6
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43755716"
---
# <a name="idispeventsimpleimpl-class"></a>Idispeventsimpleımpl sınıfı

Bu sınıf uygulamalarını sağlar `IDispatch` yöntemleri olmadan bir tür kitaplığından türü bilgileri alınıyor.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <UINT nID, class T, const IID* pdiid>  
class ATL_NO_VTABLE IDispEventSimpleImpl : public _IDispEventLocator<nID, pdiid>
```

#### <a name="parameters"></a>Parametreler

*nID*  
Kaynak nesne için benzersiz bir tanımlayıcı. Zaman `IDispEventSimpleImpl` temel sınıf için bileşik denetim, bu parametre için istenen kapsanan denetiminin kaynak kimliği kullanın. Diğer durumlarda, rastgele bir pozitif tamsayı kullanın.

*T*  
Sınıfından türetilen kullanıcının sınıfı `IDispEventSimpleImpl`.

*pdiid*  
Bu sınıf tarafından uygulanan olay görüntüleme arabirimi Laboratuvardaki işaretçisi.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IDispEventSimpleImpl::Advise](#advise)|Varsayılan olay kaynağı ile bağlantı kurar.|
|[IDispEventSimpleImpl::DispEventAdvise](#dispeventadvise)|Olay kaynağı ile bağlantı kurar.|
|[IDispEventSimpleImpl::DispEventUnadvise](#dispeventunadvise)|Olay kaynağı ile bağlantıyı keser.|
|[IDispEventSimpleImpl::GetIDsOfNames](#getidsofnames)|E_NOTIMPL döndürür.|
|[IDispEventSimpleImpl::GetTypeInfo](#gettypeinfo)|E_NOTIMPL döndürür.|
|[IDispEventSimpleImpl::GetTypeInfoCount](#gettypeinfocount)|E_NOTIMPL döndürür.|
|[IDispEventSimpleImpl::Invoke](#invoke)|Olay işleyicileri çağrıları olay havuzu harita listelenir.|
|[IDispEventSimpleImpl::Unadvise](#unadvise)|Varsayılan olay kaynağı ile bağlantıyı keser.|

## <a name="remarks"></a>Açıklamalar

`IDispEventSimpleImpl` uygulama kodu bu arabirimdeki her yöntem/olay için sağlamak için bir olay görüntüleme arabirimi gerek kalmadan uygulama bir yol sağlar. `IDispEventSimpleImpl` uygulamaları sağlar `IDispatch` yöntemleri. İşlemede ilgilenen olayları için uygulamaları sağlamak yeterlidir.

`IDispEventSimpleImpl` sınıfınızdaki uygun işleyici işlevi rota olayları için olay havuz eşlemesi ile birlikte çalışır. Bu sınıf kullanmak için:

- Ekleme bir [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info) makrosunu kullanmak istediğiniz her bir nesnedeki her bir olay için olay havuzu eşlemesi.

- Bir işaretçi geçirerek her olay için tür bilgileri sağlamanız bir [_atl_func_ınfo](../../atl/reference/atl-func-info-structure.md) her giriş parametresi olarak yapısı. X86 platform `_ATL_FUNC_INFO.cc` değeri CC_CDECL __stdcall yöntemini çağırarak geri çağırma işlevi olmalıdır.

- Çağrı [DispEventAdvise](#dispeventadvise) kaynak nesnesi ve temel sınıf arasında bağlantı kurmak için.

- Çağrı [DispEventUnadvise](#dispeventunadvise) bağlantıyı kesmek için.

Öğesinden türetilmelidir `IDispEventSimpleImpl` (için benzersiz bir değer kullanarak *nID*) için ihtiyaç duyduğunuz olayları işlemek her bir nesne. Ardından farklı kaynak nesneyle bildiren bir kaynak nesnesi karşı unadvising tarafından temel sınıfı yeniden kullanabilirsiniz, ancak tek seferde tek bir nesne tarafından işlenebilen kaynak nesneleri sayısı sayısıyla sınırlıdır `IDispEventSimpleImpl` temel sınıflar.

`IDispEventSimplImpl` aynı işlevselliği sağlar [Idispeventımpl](../../atl/reference/idispeventimpl-class.md)dışında bir tür kitaplığından arabirimi hakkında bilgi türü almaz. Yalnızca temel kodu sihirbazları oluşturma `IDispEventImpl`, ancak kullanabilirsiniz `IDispEventSimpleImpl` kodu el ile ekleyerek. Kullanım `IDispEventSimpleImpl` olduğunda olay arabirimi açıklayan bir tür kitaplığı veya yoksa tür kitaplığını kullanma ile ilgili ek yükü ortadan kaldırmak istiyorsanız.

> [!NOTE]
> `IDispEventImpl` ve `IDispEventSimpleImpl` kendi uygulamasını sağlamak `IUnknown::QueryInterface` her etkinleştirme `IDispEventImpl` veya `IDispEventSimpleImpl` temel sınıf üyelerine doğrudan erişimi ana COM nesnesinde hala izin verirken ayrı bir COM kimliği davranacak şekilde sınıfı.

ActiveX olayı havuzlarını yalnızca destekler dönüş türü değerlerinin HRESULT ya da geçersiz kılma, olay işleyicisi yöntemleri gelen CE ATL uygulaması; herhangi bir dönüş değeri desteklenmiyor ve davranışı tanımlanmamış olur.

Daha fazla bilgi için [Idispeventımpl destekleme](../../atl/supporting-idispeventimpl.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`_IDispEvent`

`_IDispEventLocator`

`IDispEventSimpleImpl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

##  <a name="advise"></a>  IDispEventSimpleImpl::Advise

Tarafından temsil edilen olay kaynağı ile bağlantı kurmak için bu yöntemi çağırın *pUnk*.

```
HRESULT Advise(IUnknown* pUnk);
```

### <a name="parameters"></a>Parametreler

*pUnk*  
[in] Bir işaretçi `IUnknown` olay kaynağı nesnesinin arabirimi.

### <a name="return-value"></a>Dönüş Değeri

S_OK veya herhangi bir hata HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

Bağlantı kurulduktan sonra gelen olaylar *pUnk* işleyicilere sınıfınızdaki olay havuzu eşlemesi aracılığıyla yönlendirilir.

> [!NOTE]
>  Sınıfınız birden çok türetilen varsa `IDispEventSimpleImpl` sınıfları, ilgilendiğiniz belirli bir taban sınıf ile arama kapsamı tarafından bu yönteme çağrıları ayırt etmek gerekir.

`Advise` bir bağlantı kurar ve isteğe bağlı olarak varsayılan olay kaynağı ile Laboratuvardaki tarafından belirlendiği şekilde, nesnenin varsayılan olay kaynağı alır [AtlGetObjectSourceInterface](composite-control-global-functions.md#atlgetobjectsourceinterface).

##  <a name="dispeventadvise"></a>  IDispEventSimpleImpl::DispEventAdvise

Tarafından temsil edilen olay kaynağı ile bağlantı kurmak için bu yöntemi çağırın *pUnk*.

```
HRESULT DispEventAdvise(IUnknown* pUnk  const IID* piid);
```

### <a name="parameters"></a>Parametreler

*pUnk*  
[in] Bir işaretçi `IUnknown` olay kaynağı nesnesinin arabirimi.

*piid*  
Olay kaynağı nesnesinin IID için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

S_OK veya herhangi bir hata HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

Daha sonra gelen olaylar *pUnk* işleyicilere sınıfınızdaki olay havuzu eşlemesi aracılığıyla yönlendirilir.

> [!NOTE]
>  Sınıfınız birden çok türetilen varsa `IDispEventSimpleImpl` sınıfları, ilgilendiğiniz belirli bir taban sınıf ile arama kapsamı tarafından bu yönteme çağrıları ayırt etmek gerekir.

`DispEventAdvise` Belirtilen olay kaynağı ile bağlantı kurar `pdiid`.

##  <a name="dispeventunadvise"></a>  IDispEventSimpleImpl::DispEventUnadvise

Tarafından temsil edilen olay kaynağı ile bağlantıyı keser *pUnk*.

```
HRESULT DispEventUnadvise(IUnknown* pUnk  const IID* piid);
```

### <a name="parameters"></a>Parametreler

*pUnk*  
[in] Bir işaretçi `IUnknown` olay kaynağı nesnesinin arabirimi.

*piid*  
Olay kaynağı nesnesinin IID için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

S_OK veya herhangi bir hata HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

Bağlantı kesildiğinde sonra olayları olay havuzu haritada listelenen işleyici işlevleri artık yönlendirilir.

> [!NOTE]
>  Sınıfınız birden çok türetilen varsa `IDispEventSimpleImpl` sınıfları, ilgilendiğiniz belirli bir taban sınıf ile arama kapsamı tarafından bu yönteme çağrıları ayırt etmek gerekir.

`DispEventAdvise` Belirtilen olay kaynağı ile kurulan bir bağlantıyı keser `pdiid`.

##  <a name="getidsofnames"></a>  IDispEventSimpleImpl::GetIDsOfNames

Bu uygulaması `IDispatch::GetIDsOfNames` E_NOTIMPL döndürür.

```
STDMETHOD(GetIDsOfNames)(
    REFIID /* riid */,
    LPOLESTR* /* rgszNames */,
    UINT /* cNames */,
    LCID /* lcid */,
    DISPID* /* rgdispid */);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [IDispatch::getıdsofnames](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-getidsofnames) Windows SDK içinde.

##  <a name="gettypeinfo"></a>  IDispEventSimpleImpl::GetTypeInfo

Bu uygulaması `IDispatch::GetTypeInfo` E_NOTIMPL döndürür.

```
STDMETHOD(GetTypeInfo)(
    UINT /* itinfo */,
    LCID /* lcid */,
    ITypeInfo** /* pptinfo */);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [IDispatch::GetTypeInfo](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-gettypeinfo) Windows SDK içinde.

##  <a name="gettypeinfocount"></a>  IDispEventSimpleImpl::GetTypeInfoCount

Bu uygulaması `IDispatch::GetTypeInfoCount` E_NOTIMPL döndürür.

```
STDMETHOD(GetTypeInfoCount)(UINT* /* pctinfo */);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [IDispatch::GetTypeInfoCount](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-gettypeinfocount) Windows SDK içinde.

##  <a name="invoke"></a>  IDispEventSimpleImpl::Invoke

Bu uygulaması `IDispatch::Invoke` olay işleyicileri listelenen olay havuzu harita çağırır.

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

Bkz: [IDispatch::Invoke](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke).

##  <a name="unadvise"></a>  IDispEventSimpleImpl::Unadvise

Tarafından temsil edilen olay kaynağı ile bağlantıyı keser *pUnk*.

```
HRESULT Unadvise(IUnknown* pUnk);
```

### <a name="parameters"></a>Parametreler

*pUnk*  
[in] Bir işaretçi `IUnknown` olay kaynağı nesnesinin arabirimi.

### <a name="return-value"></a>Dönüş Değeri

S_OK veya herhangi bir hata HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

Bağlantı kesildiğinde sonra olayları olay havuzu haritada listelenen işleyici işlevleri artık yönlendirilir.

> [!NOTE]
>  Sınıfınız birden çok türetilen varsa `IDispEventSimpleImpl` sınıfları, ilgilendiğiniz belirli bir taban sınıf ile arama kapsamı tarafından bu yönteme çağrıları ayırt etmek gerekir.

`Unadvise` Belirtilen varsayılan olay kaynağı ile kurulan bir bağlantıyı keser `pdiid`.

`Unavise` sonu bir varsayılan olay kaynağı ile bağlantı tarafından belirlendiği şekilde, nesnenin varsayılan olay kaynağının IID alır [AtlGetObjectSourceInterface](composite-control-global-functions.md#atlgetobjectsourceinterface).

## <a name="see-also"></a>Ayrıca Bkz.

[_Atl_func_ınfo yapısı](../../atl/reference/atl-func-info-structure.md)   
[Idispatchımpl sınıfı](../../atl/reference/idispatchimpl-class.md)   
[Idispeventımpl sınıfı](../../atl/reference/idispeventimpl-class.md)   
[SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)   
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
