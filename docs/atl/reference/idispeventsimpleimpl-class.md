---
title: IDispEventSimpleImpl sınıfı
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
ms.openlocfilehash: 3ceb436e4f20a17ecd086fb68f9c1cfdcbe0be3e
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78864770"
---
# <a name="idispeventsimpleimpl-class"></a>IDispEventSimpleImpl sınıfı

Bu sınıf, bir tür kitaplığından tür bilgilerini almadan `IDispatch` yöntemlerinin uygulamalarını sağlar.

> [!IMPORTANT]
>  Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <UINT nID, class T, const IID* pdiid>
class ATL_NO_VTABLE IDispEventSimpleImpl : public _IDispEventLocator<nID, pdiid>
```

#### <a name="parameters"></a>Parametreler

*NID*<br/>
Kaynak nesne için benzersiz bir tanımlayıcı. Bileşik denetimin temel sınıfı `IDispEventSimpleImpl`, bu parametre için istenen içerilen denetimin kaynak KIMLIĞINI kullanın. Diğer durumlarda rastgele pozitif bir tamsayı kullanın.

*Şı*<br/>
`IDispEventSimpleImpl`türetilen kullanıcının sınıfı.

*pdiıd*<br/>
Bu sınıf tarafından uygulanan olay görüntüleme arabiriminin IID 'sine yönelik işaretçi.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IDispEventSimpleImpl:: Advise](#advise)|Varsayılan olay kaynağıyla bir bağlantı kurar.|
|[IDispEventSimpleImpl::D ıspeventadmenlik](#dispeventadvise)|Olay kaynağıyla bir bağlantı kurar.|
|[IDispEventSimpleImpl::D ispEventUnadvise](#dispeventunadvise)|Olay kaynağıyla bağlantıyı keser.|
|[IDispEventSimpleImpl:: GetIDsOfNames](#getidsofnames)|E_NOTIMPL döndürür.|
|[IDispEventSimpleImpl:: GetTypeInfo](#gettypeinfo)|E_NOTIMPL döndürür.|
|[IDispEventSimpleImpl:: GetTypeInfoCount](#gettypeinfocount)|E_NOTIMPL döndürür.|
|[IDispEventSimpleImpl:: Invoke](#invoke)|Olay havuzu eşlemesinde listelenen olay işleyicilerini çağırır.|
|[IDispEventSimpleImpl:: Unadvise](#unadvise)|Varsayılan olay kaynağıyla bağlantıyı keser.|

## <a name="remarks"></a>Açıklamalar

`IDispEventSimpleImpl`, bu arabirimdeki her yöntem/olay için uygulama kodu vermenizi gerektirmeden bir olay görüntüleme arabirimi uygulamanın bir yolunu sağlar. `IDispEventSimpleImpl`, `IDispatch` yöntemlerin uygulamalarını sağlar. Yalnızca işleme ilgilendiğiniz olaylara yönelik uygulamalar sağlamanız gerekir.

`IDispEventSimpleImpl`, olayınızdaki olay havuzu eşlemesiyle birlikte çalışarak olayları uygun işleyici işlevine yönlendirebilir. Bu sınıfı kullanmak için:

- İşlemek istediğiniz her nesnedeki her bir olay için olay havuzu eşlemesine bir [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info) makrosu ekleyin.

- Her bir olaya bir [_ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md) yapısına bir işaretçi geçirerek her olay için tür bilgilerini sağlayın. X86 platformunda, `_ATL_FUNC_INFO.cc` değeri, geri çağırma işlevi çağıran __stdcall metodu ile CC_CDECL olmalıdır.

- Kaynak nesne ve temel sınıf arasındaki bağlantıyı kurmak için [Dispeventadmentıon](#dispeventadvise) çağırın.

- Bağlantıyı kesmek için [DispEventUnadvise](#dispeventunadvise) çağırın.

Olaylarını işlemek için gereken her nesne için `IDispEventSimpleImpl` ( *NID*için benzersiz bir değer kullanarak) türetmeniz gerekir. Temel sınıfı, bir kaynak nesnesine karşı geri yüklemeden sonra farklı bir kaynak nesnesine karşı daha sonra da kullanabilirsiniz, ancak aynı anda tek bir nesne tarafından işlenebilen en fazla kaynak nesne sayısı `IDispEventSimpleImpl` temel sınıf sayısıyla sınırlıdır.

`IDispEventSimplImpl`, [IDispEventImpl](../../atl/reference/idispeventimpl-class.md)ile aynı işlevselliği sağlar, ancak bir tür kitaplığından arabirim hakkında tür bilgisi almaz. Sihirbazlar yalnızca `IDispEventImpl`temel kod oluşturur, ancak kodu el ile ekleyerek `IDispEventSimpleImpl` kullanabilirsiniz. Olay arabirimini açıklayan bir tür kitaplığınız yoksa veya tür kitaplığını kullanarak ilişkili ek yükün önüne geçmek istiyorsanız `IDispEventSimpleImpl` kullanın.

> [!NOTE]
> `IDispEventImpl` ve `IDispEventSimpleImpl`, her `IDispEventImpl` veya `IDispEventSimpleImpl` temel sınıfını ayrı bir COM kimliği olarak davranacak şekilde `IUnknown::QueryInterface` kendi uygulanmasını sağlar, ancak yine de ana COM nesnenizin sınıf üyelerine doğrudan erişim olanağı sağlar.

ActiveX olay havuzları 'nın CE ATL uygulamasında yalnızca HRESULT veya olay işleyicisi yöntemlerinizin void türü dönüş değerleri desteklenir; diğer bir dönüş değeri desteklenmez ve davranışı tanımsız olur.

Daha fazla bilgi için bkz. [IDispEventImpl 'Yi destekleme](../../atl/supporting-idispeventimpl.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`_IDispEvent`

`_IDispEventLocator`

`IDispEventSimpleImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

##  <a name="advise"></a>IDispEventSimpleImpl:: Advise

*Punk*tarafından temsil edilen olay kaynağıyla bağlantı kurmak için bu yöntemi çağırın.

```
HRESULT Advise(IUnknown* pUnk);
```

### <a name="parameters"></a>Parametreler

*pUnk dili*<br/>
'ndaki Olay kaynağı nesnesinin `IUnknown` arabirimine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

S_OK veya herhangi bir hata HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bağlantı kurulduktan sonra, *punk* 'dan tetiklenen olaylar, olay havuzu eşlemesi yoluyla sınıfınıza olan işleyicilere yönlendirilir.

> [!NOTE]
>  Sınıfınız birden çok `IDispEventSimpleImpl` sınıftan türetiliyorsa, bu yönteme yapılan çağrıları, ilgilendiğiniz belirli temel sınıfla tanımlayarak ayırt etmeniz gerekir.

`Advise`, varsayılan olay kaynağıyla bağlantı kurarak, [AtlGetObjectSourceInterface](composite-control-global-functions.md#atlgetobjectsourceinterface)tarafından belirlendiği şekilde nesnenin varsayılan olay kaynağının IID 'sini alır.

##  <a name="dispeventadvise"></a>IDispEventSimpleImpl::D ıspeventadmenlik

*Punk*tarafından temsil edilen olay kaynağıyla bağlantı kurmak için bu yöntemi çağırın.

```
HRESULT DispEventAdvise(IUnknown* pUnk  const IID* piid);
```

### <a name="parameters"></a>Parametreler

*pUnk dili*<br/>
'ndaki Olay kaynağı nesnesinin `IUnknown` arabirimine yönelik bir işaretçi.

*piıd*<br/>
Olay kaynağı nesnesinin IID 'sine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

S_OK veya herhangi bir hata HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Daha sonra, *punk* 'dan tetiklenen olaylar, olay havuzu eşlemesi yoluyla sınıfınıza olan işleyicilere yönlendirilir.

> [!NOTE]
>  Sınıfınız birden çok `IDispEventSimpleImpl` sınıftan türetiliyorsa, bu yönteme yapılan çağrıları, ilgilendiğiniz belirli temel sınıfla tanımlayarak ayırt etmeniz gerekir.

`DispEventAdvise`, `pdiid`belirtilen olay kaynağıyla bağlantı kurar.

##  <a name="dispeventunadvise"></a>IDispEventSimpleImpl::D ispEventUnadvise

*Punk*tarafından temsil edilen olay kaynağıyla bağlantıyı keser.

```
HRESULT DispEventUnadvise(IUnknown* pUnk  const IID* piid);
```

### <a name="parameters"></a>Parametreler

*pUnk dili*<br/>
'ndaki Olay kaynağı nesnesinin `IUnknown` arabirimine yönelik bir işaretçi.

*piıd*<br/>
Olay kaynağı nesnesinin IID 'sine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

S_OK veya herhangi bir hata HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bağlantı bozulur, olaylar artık olay havuzu eşlemesinde listelenen işleyici işlevlerine yönlendirilmeyecektir.

> [!NOTE]
>  Sınıfınız birden çok `IDispEventSimpleImpl` sınıftan türetiliyorsa, bu yönteme yapılan çağrıları, ilgilendiğiniz belirli temel sınıfla tanımlayarak ayırt etmeniz gerekir.

`DispEventAdvise`, `pdiid`belirtilen olay kaynağıyla kurulan bir bağlantıyı keser.

##  <a name="getidsofnames"></a>IDispEventSimpleImpl:: GetIDsOfNames

`IDispatch::GetIDsOfNames` bu uygulama E_NOTIMPL döndürür.

```
STDMETHOD(GetIDsOfNames)(
    REFIID /* riid */,
    LPOLESTR* /* rgszNames */,
    UINT /* cNames */,
    LCID /* lcid */,
    DISPID* /* rgdispid */);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK için bkz. [IDispatch:: GetIDsOfNames](/windows/win32/api/oaidl/nf-oaidl-idispatch-getidsofnames) .

##  <a name="gettypeinfo"></a>IDispEventSimpleImpl:: GetTypeInfo

`IDispatch::GetTypeInfo` bu uygulama E_NOTIMPL döndürür.

```
STDMETHOD(GetTypeInfo)(
    UINT /* itinfo */,
    LCID /* lcid */,
    ITypeInfo** /* pptinfo */);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK [IDispatch:: GetTypeInfo](/windows/win32/api/oaidl/nf-oaidl-idispatch-gettypeinfo) bölümüne bakın.

##  <a name="gettypeinfocount"></a>IDispEventSimpleImpl:: GetTypeInfoCount

`IDispatch::GetTypeInfoCount` bu uygulama E_NOTIMPL döndürür.

```
STDMETHOD(GetTypeInfoCount)(UINT* /* pctinfo */);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK bkz. [IDispatch:: GetTypeInfoCount](/windows/win32/api/oaidl/nf-oaidl-idispatch-gettypeinfocount) .

##  <a name="invoke"></a>IDispEventSimpleImpl:: Invoke

Bu `IDispatch::Invoke` uygulanması, olay havuzu eşlemesinde listelenen olay işleyicilerini çağırır.

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

Bkz. [IDispatch:: Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke).

##  <a name="unadvise"></a>IDispEventSimpleImpl:: Unadvise

*Punk*tarafından temsil edilen olay kaynağıyla bağlantıyı keser.

```
HRESULT Unadvise(IUnknown* pUnk);
```

### <a name="parameters"></a>Parametreler

*pUnk dili*<br/>
'ndaki Olay kaynağı nesnesinin `IUnknown` arabirimine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

S_OK veya herhangi bir hata HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Bağlantı bozulur, olaylar artık olay havuzu eşlemesinde listelenen işleyici işlevlerine yönlendirilmeyecektir.

> [!NOTE]
>  Sınıfınız birden çok `IDispEventSimpleImpl` sınıftan türetiliyorsa, bu yönteme yapılan çağrıları, ilgilendiğiniz belirli temel sınıfla tanımlayarak ayırt etmeniz gerekir.

`Unadvise`, `pdiid`belirtilen varsayılan olay kaynağıyla kurulan bir bağlantıyı keser.

varsayılan olay kaynağıyla bir bağlantıyı keser `Unavise`, [AtlGetObjectSourceInterface](composite-control-global-functions.md#atlgetobjectsourceinterface)tarafından belirlendiği şekilde nesnenin varsayılan olay kaynağının IID 'sini alır.

## <a name="see-also"></a>Ayrıca bkz.

[_ATL_FUNC_INFO Yapısı](../../atl/reference/atl-func-info-structure.md)<br/>
[IDispatchImpl Sınıfı](../../atl/reference/idispatchimpl-class.md)<br/>
[IDispEventImpl Sınıfı](../../atl/reference/idispeventimpl-class.md)<br/>
[SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
