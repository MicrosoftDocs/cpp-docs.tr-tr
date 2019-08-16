---
title: IDispEventImpl sınıfı
ms.date: 11/04/2016
f1_keywords:
- IDispEventImpl
- ATLCOM/ATL::IDispEventImpl
- ATLCOM/ATL::IDispEventImpl::IDispEventImpl
- ATLCOM/ATL::IDispEventImpl::GetFuncInfoFromId
- ATLCOM/ATL::IDispEventImpl::GetIDsOfNames
- ATLCOM/ATL::IDispEventImpl::GetTypeInfo
- ATLCOM/ATL::IDispEventImpl::GetTypeInfoCount
- ATLCOM/ATL::IDispEventImpl::GetUserDefinedType
helpviewer_keywords:
- IDispEventImpl class
ms.assetid: a64b5288-35cb-4638-aad6-2d15b1c7cf7b
ms.openlocfilehash: e82a397b6d2abb66f773908c72a287c979e5ae1d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495926"
---
# <a name="idispeventimpl-class"></a>IDispEventImpl sınıfı

Bu sınıf `IDispatch` yöntemlerin uygulamalarını sağlar.

> [!IMPORTANT]
>  Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <UINT nID, class T,
    const IID* pdiid = &IID_NULL,
    const GUID* plibid = &GUID_NULL,
    WORD wMajor = 0,
    WORD wMinor = 0,
    class tihclass = CcomTypeInfoHolder>
class ATL_NO_VTABLE IDispEventImpl : public IDispEventSimpleImpl<nID, T, pdiid>
```

#### <a name="parameters"></a>Parametreler

*NID*<br/>
Kaynak nesne için benzersiz bir tanımlayıcı. Birleşik `IDispEventImpl` bir denetimin temel sınıfı olduğunda, bu parametre için istenen içerilen denetimin kaynak kimliğini kullanın. Diğer durumlarda rastgele pozitif bir tamsayı kullanın.

*ŞI*<br/>
' Den `IDispEventImpl`türetilen kullanıcının sınıfı.

*pdiıd*<br/>
Bu sınıf tarafından uygulanan olay görüntüleme arabiriminin IID 'sine yönelik işaretçi. Bu arabirimin, *plibıd*, *Wana*ve *wMinor*tarafından belirtilen tür kitaplığında tanımlanması gerekir.

*plibıd*<br/>
*Pdiıd*tarafından işaret edilen dağıtım arabirimini tanımlayan tür kitaplığına yönelik bir işaretçi. **&AMP; GUID_NULL**ise, olay kaynağı kaynak nesnesinden tür kitaplığı yüklenir.

*Wana*<br/>
Tür kitaplığının ana sürümü. Varsayılan değer 0’dır.

*wMinor*<br/>
Tür kitaplığının ikincil sürümü. Varsayılan değer 0’dır.

*tihclass*<br/>
*T*için tür bilgilerini yönetmek için kullanılan sınıf. Varsayılan değer, türünde `CComTypeInfoHolder`bir sınıftır; ancak, dışında bir türün `CComTypeInfoHolder`sınıfını sağlayarak bu şablon parametresini geçersiz kılabilirsiniz.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|[IDispEventImpl:: _tihclass](../../atl/reference/idispeventimpl-class.md)|Tür bilgilerini yönetmek için kullanılan sınıf. Varsayılan olarak, `CComTypeInfoHolder`.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[IDispEventImpl:: IDispEventImpl](#idispeventimpl)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IDispEventImpl:: GetFuncInfoFromId](#getfuncinfofromid)|Belirtilen dağıtım tanımlayıcısı için işlev dizinini bulur.|
|[IDispEventImpl:: GetIDsOfNames](#getidsofnames)|Tek bir üyeyi ve isteğe bağlı bir bağımsız değişken adları kümesini karşılık gelen tamsayı dispID kümesine eşler.|
|[IDispEventImpl:: GetTypeInfo](#gettypeinfo)|Bir nesnenin tür bilgilerini alır.|
|[IDispEventImpl:: GetTypeInfoCount](#gettypeinfocount)|Tür bilgisi arabirimlerinin sayısını alır.|
|[IDispEventImpl:: GetUserDefinedType](#getuserdefinedtype)|Kullanıcı tanımlı türün temel türünü alır.|

## <a name="remarks"></a>Açıklamalar

`IDispEventImpl`Bu arabirimdeki her yöntem/olay için uygulama kodu vermenizi gerektirmeden bir olay görüntüleme arabirimi uygulamanın bir yolunu sağlar. `IDispEventImpl``IDispatch` yöntemlerin uygulamalarını sağlar. Yalnızca işleme ilgilendiğiniz olaylara yönelik uygulamalar sağlamanız gerekir.

`IDispEventImpl`olayları uygun işleyici işlevine yönlendirmek için sınıfınızdaki olay havuzu eşlemesiyle birlikte çalışır. Bu sınıfı kullanmak için:

İşlemek istediğiniz her nesnedeki her bir olay için olay havuzu eşlemesine bir [SINK_ENTRY](composite-control-macros.md#sink_entry) veya [SINK_ENTRY_EX](composite-control-macros.md#sink_entry_ex) makrosu ekleyin. Bileşik denetimin `IDispEventImpl` temel sınıfı olarak kullanırken, olay havuzu eşlemesindeki tüm girdilerin olay kaynaklarıyla bağlantı kurmak ve kesmek için [AtlAdviseSinkMap](connection-point-global-functions.md#atladvisesinkmap) öğesini çağırabilirsiniz. Diğer durumlarda veya daha fazla denetim için, kaynak nesne ve temel sınıf arasında bağlantı kurmak için [Dispeventadmentıon](idispeventsimpleimpl-class.md#dispeventadvise) çağırın. Bağlantıyı kesmek için [DispEventUnadvise](idispeventsimpleimpl-class.md#dispeventunadvise) çağırın.

Olayları işlemek için gereken `IDispEventImpl` her nesne için ( *NID*için benzersiz bir değer kullanarak) türetmeniz gerekir. Temel sınıfı, bir kaynak nesneye karşı geri yüklemeden sonra farklı bir kaynak nesnesine karşı daha sonra bir kez daha sonra, aynı anda tek bir nesne tarafından işlenebilen en fazla kaynak nesne sayısı, `IDispEventImpl` temel sınıf sayısıyla sınırlıdır.

`IDispEventImpl`[IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)ile aynı işlevselliği sağlar, ancak bir [_Atl_func_ınfo](../../atl/reference/atl-func-info-structure.md) yapısına işaretçi olarak sağlanmaması yerine bir tür kitaplığından arabirim hakkındaki tür bilgilerini alır. Olay `IDispEventSimpleImpl` arabirimini açıklayan bir tür kitaplığınız yoksa veya tür kitaplığını kullanarak ilişkili ek yükün oluşmasını önlemek istiyorsanız kullanın.

> [!NOTE]
> `IDispEventImpl`ve `IDispEventSimpleImpl` , ana com nesnenizin sınıf üyelerine doğrudan `IDispEventImpl` erişime `IDispEventSimpleImpl` izin verirken her ve temel sınıfın ayrı bir com kimliği olarak çalışmasını sağlamak için kendi `IUnknown::QueryInterface` uygulamasını etkinleştirmeyi sağlar.

ActiveX olay havuzları 'nın CE ATL uygulamasında yalnızca HRESULT veya olay işleyicisi yöntemlerinizin void türü dönüş değerleri desteklenir; diğer bir dönüş değeri desteklenmez ve davranışı tanımsız olur.

Daha fazla bilgi için bkz. [IDispEventImpl 'Yi destekleme](../../atl/supporting-idispeventimpl.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`_IDispEvent`

`_IDispEventLocator`

[IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)

`IDispEventImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

##  <a name="getfuncinfofromid"></a>IDispEventImpl:: GetFuncInfoFromId

Belirtilen dağıtım tanımlayıcısı için işlev dizinini bulur.

```
HRESULT GetFuncInfoFromId(
    const IID& iid,
    DISPID dispidMember,
    LCID lcid,
    _ATL_FUNC_INFO& info);
```

### <a name="parameters"></a>Parametreler

*'si*<br/>
'ndaki İşlevin KIMLIĞINE bir başvuru.

*dispidMember*<br/>
'ndaki İşlevin dağıtım KIMLIĞI.

*lcid*<br/>
'ndaki İşlev KIMLIĞININ yerel ayar bağlamı.

*bilgisine*<br/>
'ndaki İşlevin nasıl çağrıldığını gösteren yapı.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

##  <a name="getidsofnames"></a>IDispEventImpl:: GetIDsOfNames

Tek bir üyeyi ve isteğe bağlı bir bağımsız değişken adları kümesini, [IDispatch:: Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke)' a yönelik sonraki çağrılar üzerinde kullanılabilen bir dizi tamsayı dispID kümesine eşler.

```
STDMETHOD(GetIDsOfNames)(
    REFIID riid,
    LPOLESTR* rgszNames,
    UINT cNames,
    LCID lcid,
    DISPID* rgdispid);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK için bkz. [IDispatch:: GetIDsOfNames](/windows/win32/api/oaidl/nf-oaidl-idispatch-getidsofnames) .

##  <a name="gettypeinfo"></a>IDispEventImpl:: GetTypeInfo

Bir nesne için tür bilgilerini alır ve bu da bir arabirimin tür bilgisini almak için kullanılabilir.

```
STDMETHOD(GetTypeInfo)(
    UINT itinfo,
    LCID lcid,
    ITypeInfo** pptinfo);
```

### <a name="remarks"></a>Açıklamalar

##  <a name="gettypeinfocount"></a>IDispEventImpl:: GetTypeInfoCount

Bir nesnenin sağladığı tür bilgisi arabirimlerinin sayısını alır (0 ya da 1).

```
STDMETHOD(GetTypeInfoCount)(UINT* pctinfo);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK bkz. [IDispatch:: GetTypeInfoCount](/windows/win32/api/oaidl/nf-oaidl-idispatch-gettypeinfocount) .

##  <a name="getuserdefinedtype"></a>IDispEventImpl:: GetUserDefinedType

Kullanıcı tanımlı türün temel türünü alır.

```
VARTYPE GetUserDefinedType(
    ITypeInfo* pTI,
    HREFTYPE hrt);
```

### <a name="parameters"></a>Parametreler

*PTI*<br/>
'ndaki Kullanıcı tanımlı türü içeren [ITypeInfo](/windows/win32/api/oaidl/nn-oaidl-itypeinfo) arabirimine yönelik bir işaretçi.

*HRT*<br/>
'ndaki Alınacak tür açıklamasına yönelik bir tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

Değişken türü.

### <a name="remarks"></a>Açıklamalar

Bkz. [ITypeInfo:: GetRefTypeInfo](/windows/win32/api/oaidl/nf-oaidl-itypeinfo-getreftypeinfo).

##  <a name="idispeventimpl"></a>IDispEventImpl:: IDispEventImpl

Oluşturucu. *Plibıd*, *pdiıd*, *Wana*ve *wMinor*sınıf şablonu parametrelerinin değerlerini depolar.

```
IDispEventImpl();
```

##  <a name="tihclass"></a>IDispEventImpl:: tihclass

Bu typedef, bir sınıf şablonu parametresinin bir örneğidir.

```
typedef tihclass _tihclass;
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, sınıfı `CComTypeInfoHolder`. `CComTypeInfoHolder`sınıf için tür bilgilerini yönetir.

## <a name="see-also"></a>Ayrıca bkz.

[_ATL_FUNC_INFO Yapısı](../../atl/reference/atl-func-info-structure.md)<br/>
[IDispatchImpl Sınıfı](../../atl/reference/idispatchimpl-class.md)<br/>
[IDispEventSimpleImpl Sınıfı](../../atl/reference/idispeventsimpleimpl-class.md)<br/>
[SINK_ENTRY](composite-control-macros.md#sink_entry)<br/>
[SINK_ENTRY_EX](composite-control-macros.md#sink_entry_ex)<br/>
[SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
