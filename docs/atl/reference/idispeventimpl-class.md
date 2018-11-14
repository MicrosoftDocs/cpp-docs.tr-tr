---
title: Idispeventımpl sınıfı
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
ms.openlocfilehash: 75946005acc22874b17ee806cd89ec99095f9c35
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51524306"
---
# <a name="idispeventimpl-class"></a>Idispeventımpl sınıfı

Bu sınıf uygulamalarını sağlar `IDispatch` yöntemleri.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

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

*nID*<br/>
Kaynak nesne için benzersiz bir tanımlayıcı. Zaman `IDispEventImpl` temel sınıf için bileşik denetim, bu parametre için istenen kapsanan denetiminin kaynak kimliği kullanın. Diğer durumlarda, rastgele bir pozitif tamsayı kullanın.

*T*<br/>
Sınıfından türetilen kullanıcının sınıfı `IDispEventImpl`.

*pdiid*<br/>
Bu sınıf tarafından uygulanan olay görüntüleme arabirimi Laboratuvardaki işaretçisi. Bu arabirim tarafından belirtilen tür kitaplığı tanımlanmalıdır *plibid*, *wMajor*, ve *wMinor*.

*plibid*<br/>
Dağıtım arabirimi tanımlayan tür kitaplığı için bir işaretçi tarafından işaret edilen *pdiid*. Varsa **& GUID_NULL**, olay kaynağını belirleme nesneden tür kitaplığı yüklenir.

*wMajor*<br/>
Tür kitaplığının ana sürümü. Varsayılan değer 0’dır.

*wMinor*<br/>
Tür kitaplığının bir alt sürümü. Varsayılan değer 0’dır.

*tihclass*<br/>
İçin tür bilgilerini yönetmek için kullanılan sınıf *T*. Varsayılan değer türünün bir sınıftır `CComTypeInfoHolder`; ancak, bir türün bir sınıf dışında sağlayarak bu şablon parametresi geçersiz kılabilirsiniz `CComTypeInfoHolder`.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|[IDispEventImpl::_tihclass](../../atl/reference/idispeventimpl-class.md)|Tür bilgilerini yönetmek için kullanılan sınıf. Varsayılan olarak, `CComTypeInfoHolder`.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[IDispEventImpl::IDispEventImpl](#idispeventimpl)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IDispEventImpl::GetFuncInfoFromId](#getfuncinfofromid)|Belirtilen gönderme tanımlayıcısının işlevi dizini bulur.|
|[IDispEventImpl::GetIDsOfNames](#getidsofnames)|Tek bir üye ve isteğe bağlı bir bağımsız değişken adları kümesini karşılık gelen bir tamsayı DISPID değeri kümesine eşler.|
|[IDispEventImpl::GetTypeInfo](#gettypeinfo)|Bir nesne için tür bilgilerini alır.|
|[IDispEventImpl::GetTypeInfoCount](#gettypeinfocount)|Tür bilgisi arabirimlerinin sayısını alır.|
|[IDispEventImpl::GetUserDefinedType](#getuserdefinedtype)|Kullanıcı tanımlı bir türün temel türünü alır.|

## <a name="remarks"></a>Açıklamalar

`IDispEventImpl` uygulama kodu bu arabirimdeki her yöntem/olay için sağlamak için bir olay görüntüleme arabirimi gerek kalmadan uygulama bir yol sağlar. `IDispEventImpl` uygulamaları sağlar `IDispatch` yöntemleri. İşlemede ilgilenen olayları için uygulamaları sağlamak yeterlidir.

`IDispEventImpl` sınıfınızdaki uygun işleyici işlevi rota olayları için olay havuz eşlemesi ile birlikte çalışır. Bu sınıf kullanmak için:

Ekleme bir [SINK_ENTRY](composite-control-macros.md#sink_entry) veya [SINK_ENTRY_EX](composite-control-macros.md#sink_entry_ex) makrosunu kullanmak istediğiniz her bir nesnedeki her bir olay için olay havuzu eşlemesi. Kullanırken `IDispEventImpl` bileşik denetim temel sınıf olarak çağırabilirsiniz [AtlAdviseSinkMap](connection-point-global-functions.md#atladvisesinkmap) kurmak ve tüm girişleri olay eşlemesi havuz için olay kaynağı ile bağlantıyı kesin. Diğer durumlarda ya da daha fazla denetim için arama [DispEventAdvise](idispeventsimpleimpl-class.md#dispeventadvise) kaynak nesnesi ve temel sınıf arasında bağlantı kurmak için. Çağrı [DispEventUnadvise](idispeventsimpleimpl-class.md#dispeventunadvise) bağlantıyı kesmek için.

Öğesinden türetilmelidir `IDispEventImpl` (için benzersiz bir değer kullanarak *nID*) için ihtiyaç duyduğunuz olayları işlemek her bir nesne. Ardından farklı kaynak nesneyle bildiren bir kaynak nesnesi karşı unadvising tarafından temel sınıfı yeniden kullanabilirsiniz, ancak tek seferde tek bir nesne tarafından işlenebilen kaynak nesneleri sayısı sayısıyla sınırlıdır `IDispEventImpl` temel sınıflar.

`IDispEventImpl` aynı işlevselliği sağlar [Idispeventsimpleımpl](../../atl/reference/idispeventsimpleimpl-class.md)sağlanan işaretçisi olarak sahip olmak yerine bir tür kitaplığı arabirimi hakkında bilgi türü alır dışında bir [_atl_func_ınfo](../../atl/reference/atl-func-info-structure.md) yapısı. Kullanım `IDispEventSimpleImpl` ne zaman, olay arabirimi açıklayan bir tür kitaplığı olan bir ya da tür kitaplığını kullanma ile ilgili ek yükü ortadan kaldırmak istiyorsanız.

> [!NOTE]
> `IDispEventImpl` ve `IDispEventSimpleImpl` kendi uygulamasını sağlamak `IUnknown::QueryInterface` her etkinleştirme `IDispEventImpl` ve `IDispEventSimpleImpl` temel sınıf üyelerine doğrudan erişimi ana COM nesnesinde hala izin verirken ayrı bir COM kimliği davranacak şekilde sınıfı.

ActiveX olayı havuzlarını yalnızca destekler dönüş türü değerlerinin HRESULT ya da geçersiz kılma, olay işleyicisi yöntemleri gelen CE ATL uygulaması; herhangi bir dönüş değeri desteklenmiyor ve davranışı tanımlanmamış olur.

Daha fazla bilgi için [Idispeventımpl destekleme](../../atl/supporting-idispeventimpl.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`_IDispEvent`

`_IDispEventLocator`

[IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)

`IDispEventImpl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

##  <a name="getfuncinfofromid"></a>  IDispEventImpl::GetFuncInfoFromId

Belirtilen gönderme tanımlayıcısının işlevi dizini bulur.

```
HRESULT GetFuncInfoFromId(
    const IID& iid,
    DISPID dispidMember,
    LCID lcid,
    _ATL_FUNC_INFO& info);
```

### <a name="parameters"></a>Parametreler

*IID*<br/>
[in] İşlev kodu bir başvuru.

*dispidMember*<br/>
[in] İşlev gönderme kimliği.

*lcid*<br/>
[in] İşlev kimliğine, yerel ayar bağlamı

*Bilgileri*<br/>
[in] İşlev nasıl çağrılır belirten yapısı.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

##  <a name="getidsofnames"></a>  IDispEventImpl::GetIDsOfNames

Tek bir üye ve isteğe bağlı bir bağımsız değişken adları kümesi tamsayı yapılan sonraki çağrılar kullanılabilir DISPID değeri karşılık gelen bir dizi eşleyen [IDispatch::Invoke](/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke).

```
STDMETHOD(GetIDsOfNames)(
    REFIID riid,
    LPOLESTR* rgszNames,
    UINT cNames,
    LCID lcid,
    DISPID* rgdispid);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [IDispatch::getıdsofnames](/windows/desktop/api/oaidl/nf-oaidl-idispatch-getidsofnames) Windows SDK içinde.

##  <a name="gettypeinfo"></a>  IDispEventImpl::GetTypeInfo

Bir nesne için tür bilgilerini alır ve bu da bir arabirimin tür bilgisini almak için kullanılabilir.

```
STDMETHOD(GetTypeInfo)(
    UINT itinfo,
    LCID lcid,
    ITypeInfo** pptinfo);
```

### <a name="remarks"></a>Açıklamalar

##  <a name="gettypeinfocount"></a>  IDispEventImpl::GetTypeInfoCount

Bir nesnenin sağladığı tür bilgisi arabirimlerinin sayısını alır (0 ya da 1).

```
STDMETHOD(GetTypeInfoCount)(UINT* pctinfo);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [IDispatch::GetTypeInfoCount](/windows/desktop/api/oaidl/nf-oaidl-idispatch-gettypeinfocount) Windows SDK içinde.

##  <a name="getuserdefinedtype"></a>  IDispEventImpl::GetUserDefinedType

Kullanıcı tanımlı bir türün temel türünü alır.

```
VARTYPE GetUserDefinedType(
    ITypeInfo* pTI,
    HREFTYPE hrt);
```

### <a name="parameters"></a>Parametreler

*PTI*<br/>
[in] Bir işaretçi [ITypeInfo](/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) arabirimi içeren kullanıcı tanımlı tür.

*hrt*<br/>
[in] Alınacak tür tanımı için bir tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

Değişken türü.

### <a name="remarks"></a>Açıklamalar

Bkz: [ITypeInfo::GetRefTypeInfo](/windows/desktop/api/oaidl/nf-oaidl-itypeinfo-getreftypeinfo).

##  <a name="idispeventimpl"></a>  IDispEventImpl::IDispEventImpl

Oluşturucu. Sınıf şablonu parametrelerinin değerlerini depolar *plibid*, *pdiid*, *wMajor*, ve *wMinor*.

```
IDispEventImpl();
```

##  <a name="tihclass"></a>  IDispEventImpl::tihclass

Bu typedef sınıfı şablon parametresi örneğidir *tihclass*.

```
typedef tihclass _tihclass;
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bir sınıftır `CComTypeInfoHolder`. `CComTypeInfoHolder` sınıfı için tür bilgilerini yönetir.

## <a name="see-also"></a>Ayrıca Bkz.

[_ATL_FUNC_INFO Yapısı](../../atl/reference/atl-func-info-structure.md)<br/>
[IDispatchImpl Sınıfı](../../atl/reference/idispatchimpl-class.md)<br/>
[IDispEventSimpleImpl Sınıfı](../../atl/reference/idispeventsimpleimpl-class.md)<br/>
[SINK_ENTRY](composite-control-macros.md#sink_entry)<br/>
[SINK_ENTRY_EX](composite-control-macros.md#sink_entry_ex)<br/>
[SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)