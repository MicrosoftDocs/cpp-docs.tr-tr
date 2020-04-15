---
title: IDispEventImpl Sınıfı
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
ms.openlocfilehash: fa6e9f972accd0115d9f1e3248bd97ddde0c3c63
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329766"
---
# <a name="idispeventimpl-class"></a>IDispEventImpl Sınıfı

Bu `IDispatch` sınıf, yöntemlerin uygulamalarını sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

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

*Nıd*<br/>
Kaynak nesne için benzersiz bir tanımlayıcı. Bileşik `IDispEventImpl` denetimin taban sınıfı ne zaman, bu parametre için istenen denetimin kaynak kimliğini kullanın. Diğer durumlarda, rasgele pozitif tamsayı kullanın.

*T*<br/>
Kullanıcının sınıfından `IDispEventImpl`türetilen.

*pdiid*<br/>
Bu sınıf tarafından uygulanan olay dispinterface IID işaretçisi. Bu arabirim *plibid*, *wMajor*ve *wMinor*ile gösterilen tür kitaplığında tanımlanmalıdır.

*plibid*<br/>
*Pdiid*tarafından işaret edilen gönderme arabirimini tanımlayan tür kitaplığına işaretçi. **&GUID_NULL,** tür kitaplığı olayları kaynak nesnesinden yüklenir.

*wMajor*<br/>
Tür kitaplığın ana sürümü. Varsayılan değer 0’dır.

*wMinor*<br/>
Tür kitaplığın küçük sürümü. Varsayılan değer 0’dır.

*tihclass*<br/>
*T.* için tür bilgilerini yönetmek için kullanılan sınıf. Varsayılan değer bir tür `CComTypeInfoHolder`sınıfıdır; ancak, `CComTypeInfoHolder`'den başka bir türde bir sınıf sağlayarak bu şablon parametresini geçersiz kılabilirsiniz.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

|Adı|Açıklama|
|----------|-----------------|
|[IDispEventImpl::_tihclass](../../atl/reference/idispeventimpl-class.md)|Tür bilgilerini yönetmek için kullanılan sınıf. Varsayılan olarak, `CComTypeInfoHolder`.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[IDispEventImpl::IDispEventImpl](#idispeventimpl)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IDispEventImpl::GetFuncInfoFromId](#getfuncinfofromid)|Belirtilen sevkiyat tanımlayıcısının işlev dizini bulur.|
|[IDispEventImpl::GetIDsOfNames](#getidsofnames)|Tek bir üyeyi ve isteğe bağlı bağımsız değişken adlarını karşılık gelen bir tamsayı DISPIDs kümesiyle eşler.|
|[IDispEventImpl::GetTypeInfo](#gettypeinfo)|Bir nesnenin tür bilgilerini alır.|
|[IDispEventImpl::GetTypeInfoCount](#gettypeinfocount)|Tür bilgi arabirimlerinin sayısını alır.|
|[IDispEventImpl::GetUserDefinedType](#getuserdefinedtype)|Kullanıcı tanımlı bir türün temel türünü alır.|

## <a name="remarks"></a>Açıklamalar

`IDispEventImpl`bu arabirimdeki her yöntem/olay için uygulama kodu sağlamanızı gerektirmeden bir olay dispinterface uygulama yöntemi sağlar. `IDispEventImpl`yöntemlerin `IDispatch` uygulamalarını sağlar. Yalnızca işlemek le ilgilendiğiniz olaylar için uygulamalar sağlamanız gerekir.

`IDispEventImpl`olayları uygun işleyici işlevine yönlendirmek için sınıfınızdaki olay lavabo haritasıyla birlikte çalışır. Bu sınıfı kullanmak için:

Işlemek istediğiniz her nesnedeki her olay için olay lavabo haritasına [bir SINK_ENTRY](composite-control-macros.md#sink_entry) veya [SINK_ENTRY_EX](composite-control-macros.md#sink_entry_ex) makro ekleyin. Bileşik `IDispEventImpl` denetimin taban sınıfı olarak kullanırken, olay lavabo haritasındaki tüm girişler için olay kaynaklarıyla bağlantıyı kurmak ve kırmak için [AtlAdviseSinkMap'i](connection-point-global-functions.md#atladvisesinkmap) arayabilirsiniz. Diğer durumlarda veya daha fazla denetim için kaynak nesne ile taban sınıf arasındaki bağlantıyı kurmak için [DispEventAdvise'i](idispeventsimpleimpl-class.md#dispeventadvise) arayın. Bağlantıyı kırmak için [DispEventUnadvise'i](idispeventsimpleimpl-class.md#dispeventunadvise) arayın.

Olayları işlemek için `IDispEventImpl` gereken her nesne için *(nID*için benzersiz bir değer kullanarak) türetmeniz gerekir. Bir kaynak nesneye karşı tavsiyede sonra farklı bir kaynak nesneye karşı tavsiyede bulunabilir, ancak aynı anda tek bir nesne tarafından işlenebilecek `IDispEventImpl` en fazla kaynak nesne sayısı temel sınıf sayısıyla sınırlıdır.

`IDispEventImpl`[iDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)ile aynı işlevselliği sağlar , ancak [_ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md) bir yapıya işaretçi olarak sağlanmış olması yerine bir tür kitaplığından arabirim hakkında tür bilgileri alır. Olay `IDispEventSimpleImpl` arabirimini açıklayan bir tür kitaplığınız yoksa veya tür kitaplığını kullanmakla ilişkili genel merkezlerden kaçınmak istediğinizde kullanın.

> [!NOTE]
> `IDispEventImpl`ve `IDispEventSimpleImpl` ana COM `IUnknown::QueryInterface` nesnenizdeki `IDispEventImpl` sınıf `IDispEventSimpleImpl` üyelerine doğrudan erişim sağlarken her ve taban sınıfın ayrı bir COM kimliği olarak hareket etmesini etkinleştirme uygulamalarını sağlar.

ActiveX olay lavabolarının CE ATL uygulaması yalnızca HRESULT türü veya olay işleyicisi yöntemlerinizden geçersiz olan iade değerlerini destekler; başka bir iade değeri desteklenmez ve davranışı tanımsızdır.

Daha fazla bilgi için Bkz. [IDispEventImpl'i Destekleme](../../atl/supporting-idispeventimpl.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`_IDispEvent`

`_IDispEventLocator`

[ıdispeventsimpleımpl](../../atl/reference/idispeventsimpleimpl-class.md)

`IDispEventImpl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="idispeventimplgetfuncinfofromid"></a><a name="getfuncinfofromid"></a>IDispEventImpl::GetFuncInfoFromId

Belirtilen sevkiyat tanımlayıcısının işlev dizini bulur.

```
HRESULT GetFuncInfoFromId(
    const IID& iid,
    DISPID dispidMember,
    LCID lcid,
    _ATL_FUNC_INFO& info);
```

### <a name="parameters"></a>Parametreler

*ııd*<br/>
[içinde] İşlevin kimliğine bir başvuru.

*dispidÜye*<br/>
[içinde] İşlevin sevk kimliği.

*lcid*<br/>
[içinde] İşlev kimliğinin yerel bağlamı.

*Bilgi*<br/>
[içinde] İşlevin nasıl adlandırıldığını gösteren yapı.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="idispeventimplgetidsofnames"></a><a name="getidsofnames"></a>IDispEventImpl::GetIDsOfNames

Tek bir üyeyi ve isteğe bağlı bir bağımsız değişken ad kümesini, Sonraki IDispatch aramalarında kullanılabilecek karşılık gelen bir tamsayı DISPIDs kümesiyle [eşler:Çağırın.](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke)

```
STDMETHOD(GetIDsOfNames)(
    REFIID riid,
    LPOLESTR* rgszNames,
    UINT cNames,
    LCID lcid,
    DISPID* rgdispid);
```

### <a name="remarks"></a>Açıklamalar

Bkz. IDispatch::Windows SDK'daki [GetIDsOfNames.](/windows/win32/api/oaidl/nf-oaidl-idispatch-getidsofnames)

## <a name="idispeventimplgettypeinfo"></a><a name="gettypeinfo"></a>IDispEventImpl::GetTypeInfo

Bir nesne için tür bilgilerini alır ve bu da bir arabirimin tür bilgisini almak için kullanılabilir.

```
STDMETHOD(GetTypeInfo)(
    UINT itinfo,
    LCID lcid,
    ITypeInfo** pptinfo);
```

### <a name="remarks"></a>Açıklamalar

## <a name="idispeventimplgettypeinfocount"></a><a name="gettypeinfocount"></a>IDispEventImpl::GetTypeInfoCount

Bir nesnenin sağladığı tür bilgisi arabirimlerinin sayısını alır (0 ya da 1).

```
STDMETHOD(GetTypeInfoCount)(UINT* pctinfo);
```

### <a name="remarks"></a>Açıklamalar

Bkz. IDispatch::Windows SDK'da [TypeInfoCount'u alın.](/windows/win32/api/oaidl/nf-oaidl-idispatch-gettypeinfocount)

## <a name="idispeventimplgetuserdefinedtype"></a><a name="getuserdefinedtype"></a>IDispEventImpl::GetUserDefinedType

Kullanıcı tanımlı bir türün temel türünü alır.

```
VARTYPE GetUserDefinedType(
    ITypeInfo* pTI,
    HREFTYPE hrt);
```

### <a name="parameters"></a>Parametreler

*Ptı*<br/>
[içinde] Kullanıcı tanımlı türü içeren [ITypeInfo](/windows/win32/api/oaidl/nn-oaidl-itypeinfo) arabirimine bir işaretçi.

*Hrt*<br/>
[içinde] Alınacak tür açıklamasına bir tutamaç.

### <a name="return-value"></a>Dönüş Değeri

Varyant türü.

### <a name="remarks"></a>Açıklamalar

Bkz. [iTypeInfo::GetrefTypeInfo](/windows/win32/api/oaidl/nf-oaidl-itypeinfo-getreftypeinfo).

## <a name="idispeventimplidispeventimpl"></a><a name="idispeventimpl"></a>IDispEventImpl::IDispEventImpl

Oluşturucu. Sınıf şablon parametreleri *plibid,* *pdiid*, *wMajor*ve *wMinor*değerlerini depolar.

```
IDispEventImpl();
```

## <a name="idispeventimpltihclass"></a><a name="tihclass"></a>IDispEventImpl::tihclass

Bu typedef sınıf şablonu parametre *tihclass*bir örneğidir.

```
typedef tihclass _tihclass;
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, sınıf `CComTypeInfoHolder`. `CComTypeInfoHolder`sınıfın tür bilgilerini yönetir.

## <a name="see-also"></a>Ayrıca bkz.

[_ATL_FUNC_INFO Yapısı](../../atl/reference/atl-func-info-structure.md)<br/>
[IDispatchImpl Sınıfı](../../atl/reference/idispatchimpl-class.md)<br/>
[IDispEventSimpleImpl Sınıfı](../../atl/reference/idispeventsimpleimpl-class.md)<br/>
[SINK_ENTRY](composite-control-macros.md#sink_entry)<br/>
[SINK_ENTRY_EX](composite-control-macros.md#sink_entry_ex)<br/>
[SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
