---
description: 'Daha fazla bilgi edinin: CBindStatusCallback sınıfı'
title: CBindStatusCallback sınıfı
ms.date: 11/04/2016
f1_keywords:
- CBindStatusCallback
- ATLCTL/ATL::CBindStatusCallback
- ATLCTL/ATL::CBindStatusCallback::CBindStatusCallback
- ATLCTL/ATL::CBindStatusCallback::Download
- ATLCTL/ATL::CBindStatusCallback::GetBindInfo
- ATLCTL/ATL::CBindStatusCallback::GetPriority
- ATLCTL/ATL::CBindStatusCallback::OnDataAvailable
- ATLCTL/ATL::CBindStatusCallback::OnLowResource
- ATLCTL/ATL::CBindStatusCallback::OnObjectAvailable
- ATLCTL/ATL::CBindStatusCallback::OnProgress
- ATLCTL/ATL::CBindStatusCallback::OnStartBinding
- ATLCTL/ATL::CBindStatusCallback::OnStopBinding
- ATLCTL/ATL::CBindStatusCallback::StartAsyncDownload
- ATLCTL/ATL::CBindStatusCallback::m_dwAvailableToRead
- ATLCTL/ATL::CBindStatusCallback::m_dwTotalRead
- ATLCTL/ATL::CBindStatusCallback::m_pFunc
- ATLCTL/ATL::CBindStatusCallback::m_pT
- ATLCTL/ATL::CBindStatusCallback::m_spBindCtx
- ATLCTL/ATL::CBindStatusCallback::m_spBinding
- ATLCTL/ATL::CBindStatusCallback::m_spMoniker
- ATLCTL/ATL::CBindStatusCallback::m_spStream
helpviewer_keywords:
- asynchronous data transfer [C++]
- data transfer [C++]
- data transfer [C++], asynchronous
- CBindStatusCallback class
ms.assetid: 0f5da276-6031-4418-b2a9-a4750ef29e77
ms.openlocfilehash: 8c57328be0cb2678e671f68ac5bb44471056f457
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146984"
---
# <a name="cbindstatuscallback-class"></a>CBindStatusCallback sınıfı

Bu sınıf, `IBindStatusCallback` arabirimini uygular.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class T,
    int nBindFlags = BINDF_ASYNCHRONOUS | BINDF_ASYNCSTORAGE | BINDF_GETNEWESTVERSION | BINDF_NOWRITECACHE>
class ATL_NO_VTABLE CBindStatusCallback : public CComObjectRootEx <T ::_ThreadModel::ThreadModelNoCS>,
    public IBindStatusCallbackImpl<T>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Veri alındığında çağrılacak işlevi içeren sınıfınız.

*nBindFlags*<br/>
[GetBindInfo](#getbindinfo)tarafından döndürülen bağlama bayraklarını belirtir. Varsayılan uygulama, bağlamayı zaman uyumsuz olacak şekilde ayarlar, veri/nesne ' nin en yeni sürümünü alır ve alınan verileri disk önbelleğinde depolamaz.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CBindStatusCallback:: CBindStatusCallback](#cbindstatuscallback)|Oluşturucu.|
|[CBindStatusCallback:: ~ CBindStatusCallback](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CBindStatusCallback::D ownload](#download)|İndirme işlemini başlatan statik yöntem, bir `CBindStatusCallback` nesne ve çağrılar oluşturur `StartAsyncDownload` .|
|[CBindStatusCallback:: GetBindInfo](#getbindinfo)|Oluşturulacak bağlama türü hakkında bilgi istemek için zaman uyumsuz bilinen ad tarafından çağırılır.|
|[CBindStatusCallback:: GetPriority](#getpriority)|Bağlama işleminin önceliğini almak için zaman uyumsuz bilinen ad tarafından çağırılır. ATL uygulamasının döndürdüğü değer `E_NOTIMPL` .|
|[CBindStatusCallback:: OnDataAvailable](#ondataavailable)|Uygulamanıza kullanılabilir hale geldiğinde veri sağlamak için çağırılır. Verileri okur, ardından bu verileri kullanmak için geçirilen işlevi çağırır.|
|[CBindStatusCallback:: OnLowResource](#onlowresource)|Kaynaklar azaldığında çağırılır. ATL uygulama S_OK döndürür.|
|[CBindStatusCallback:: OnObjectAvailable](#onobjectavailable)|Uygulamanıza bir nesne arabirimi işaretçisi geçirmek için zaman uyumsuz bilinen ad tarafından çağırılır. ATL uygulama S_OK döndürür.|
|[CBindStatusCallback:: OnProgress](#onprogress)|Bir veri indirme işleminin ilerlemesini göstermek için çağırılır. ATL uygulama S_OK döndürür.|
|[CBindStatusCallback:: OnStartBinding](#onstartbinding)|Bağlama başlatıldığında çağırılır.|
|[CBindStatusCallback:: OnStopBinding](#onstopbinding)|Zaman uyumsuz veri aktarımı durdurulduğunda çağırılır.|
|[CBindStatusCallback:: StartAsyncDownload](#startasyncdownload)|Kullanılabilir baytları ve baytların sıfıra okunduğunu başlatır, URL 'den bir gönderme türü Stream nesnesi oluşturur ve `OnDataAvailable` verilerin kullanılabildiği her seferinde çağırır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CBindStatusCallback:: m_dwAvailableToRead](#m_dwavailabletoread)|Okuma için kullanılabilir bayt sayısı.|
|[CBindStatusCallback:: m_dwTotalRead](#m_dwtotalread)|Okunan toplam bayt sayısı.|
|[CBindStatusCallback:: m_pFunc](#m_pfunc)|Veri kullanılabilir olduğunda çağrılan işlevin işaretçisi.|
|[CBindStatusCallback:: m_pT](#m_pt)|Zaman uyumsuz veri aktarımını isteyen nesneye yönelik işaretçi.|
|[CBindStatusCallback:: m_spBindCtx](#m_spbindctx)|Geçerli bağlama işlemi için [IBindCtx](/windows/win32/api/objidl/nn-objidl-ibindctx) arabirimine yönelik işaretçi.|
|[CBindStatusCallback:: m_spBinding](#m_spbinding)|`IBinding`Geçerli bağlama işlemi için arabirim işaretçisi.|
|[CBindStatusCallback:: m_spMoniker](#m_spmoniker)|Kullanılacak URL için [IMoniker](/windows/win32/api/objidl/nn-objidl-imoniker) arabirimine yönelik işaretçi.|
|[CBindStatusCallback:: m_spStream](#m_spstream)|Veri aktarımı için [IStream](/windows/win32/api/objidl/nn-objidl-istream) arabirimine yönelik işaretçi.|

## <a name="remarks"></a>Açıklamalar

`CBindStatusCallback` sınıfı, `IBindStatusCallback` arabirimini uygular. `IBindStatusCallback` zaman uyumsuz bir veri aktarımından bildirim alabilmesi için uygulamanız tarafından uygulanmalıdır. Sistem tarafından sunulan zaman uyumsuz bilinen ad, `IBindStatusCallback` nesnenizin zaman uyumsuz veri aktarımı hakkında bilgi göndermek ve almak için yöntemleri kullanır.

Genellikle, `CBindStatusCallback` nesne belirli bir bağlama işlemiyle ilişkilendirilir. Örneğin, [ASYNC](../../overview/visual-cpp-samples.md) ÖRNEĞINDE, URL özelliğini ayarladığınızda, ' `CBindStatusCallback` de yapılan çağrıda bir nesne oluşturur `Download` :

[!code-cpp[NVC_ATL_Windowing#86](../../atl/codesnippet/cpp/cbindstatuscallback-class_1.h)]

Zaman uyumsuz bilinen ad, `OnData` veri olduğunda uygulamanızı çağırmak için geri çağırma işlevini kullanır. Zaman uyumsuz bilinen ad sistem tarafından sağlanır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CComObjectRootBase`

`IBindStatusCallback`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`CBindStatusCallback`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl. h

## <a name="cbindstatuscallbackcbindstatuscallback"></a><a name="cbindstatuscallback"></a> CBindStatusCallback:: CBindStatusCallback

Oluşturucu.

```
CBindStatusCallback();
```

### <a name="remarks"></a>Açıklamalar

Zaman uyumsuz veri aktarımına ilişkin bildirimleri almak için bir nesnesi oluşturur. Genellikle, her bağlama işlemi için bir nesne oluşturulur.

Oluşturucu Ayrıca [m_pT](#m_pt) BAŞLATıR ve null [m_pFunc](#m_pfunc) .

## <a name="cbindstatuscallbackcbindstatuscallback"></a><a name="dtor"></a> CBindStatusCallback:: ~ CBindStatusCallback

Yok edicisi.

```
~CBindStatusCallback();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakır.

## <a name="cbindstatuscallbackdownload"></a><a name="download"></a> CBindStatusCallback::D ownload

`CBindStatusCallback` `StartAsyncDownload` Belirtilen URL 'den zaman uyumsuz olarak veri indirmeyi başlatacak bir nesne ve çağrılar oluşturur.

```
static HRESULT Download(
    T* pT,
    ATL_PDATAAVAILABLE pFunc,
    BSTR bstrURL,
    IUnknown* pUnkContainer = NULL,
    BOOL bRelative = FALSE);
```

### <a name="parameters"></a>Parametreler

*Yönergelerinin*<br/>
'ndaki Zaman uyumsuz veri aktarımı isteyen nesneye yönelik bir işaretçi. `CBindStatusCallback`Nesne bu nesnenin sınıfında şablonsaldır.

*pFunc*<br/>
'ndaki Okunan verileri alan işleve yönelik bir işaretçi. İşlevi, nesnenizin türü sınıfının bir üyesidir `T` . Sözdizimi ve örnek için bkz. [StartAsyncDownload](#startasyncdownload) .

*bstrURL*<br/>
'ndaki Verilerin alınacağı URL. Herhangi bir geçerli URL veya dosya adı olabilir. NULL olamaz. Örneğin:

`CComBSTR mybstr =_T("http://somesite/data.htm")`

*pUnkContainer*<br/>
'ndaki `IUnknown` Kapsayıcının. Varsayılan olarak NULL.

*Bgöreli*<br/>
'ndaki URL 'nin göreli veya mutlak olduğunu belirten bir bayrak. Varsayılan olarak FALSE, yani URL mutlak bir değer.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Veriler her kullanılabilir olduğunda nesnesine gönderilir `OnDataAvailable` . `OnDataAvailable` verileri okur ve *pFunc* tarafından işaret edilen işlevi çağırır (örneğin, verileri depolamak veya ekranda yazdırmak için).

## <a name="cbindstatuscallbackgetbindinfo"></a><a name="getbindinfo"></a> CBindStatusCallback:: GetBindInfo

Bilinen adı nasıl bağlayacağınızı söylemek için çağırılır.

```
STDMETHOD(GetBindInfo)(
    DWORD* pgrfBSCF,
    BINDINFO* pbindinfo);
```

### <a name="parameters"></a>Parametreler

*pgrfBSCF*<br/>
dışı , Bağlama işleminin nasıl gerçekleşeceğini gösteren BINDF numaralandırma değerlerine yönelik bir işaretçi. Varsayılan olarak, aşağıdaki numaralandırma değerleriyle ayarlanır:

Zaman uyumsuz indirme BINDF_ASYNCHRONOUS.

BINDF_ASYNCSTORAGE `OnDataAvailable` , veriler kullanılabilir olana kadar engelleme yerine henüz kullanılabilir olmadığında E_PENDING döndürür.

Bağlama işleminin, verilerin en yeni sürümünü alması BINDF_GETNEWESTVERSION.

Bağlama işlemi BINDF_NOWRITECACHE alınan verileri disk önbelleğinde depolamamalıdır.

*pbindinfo*<br/>
[in, out] `BINDINFO` Nesnenin, bağlamanın nasıl gerçekleşmesini istediğini hakkında daha fazla bilgi sağlayan yapı işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, bağlamayı zaman uyumsuz olacak şekilde ayarlar ve veri gönderim modelini kullanır. Veri gönderim modelinde, bilinen ad zaman uyumsuz bağlama işlemini ve yeni veriler kullanılabilir her seferinde sürekli olarak istemciye bildirir.

## <a name="cbindstatuscallbackgetpriority"></a><a name="getpriority"></a> CBindStatusCallback:: GetPriority

Bağlama işleminin önceliğini almak için zaman uyumsuz bilinen ad tarafından çağırılır.

```
STDMETHOD(GetPriority)(LONG* pnPriority);
```

### <a name="parameters"></a>Parametreler

*pnPriority*<br/>
dışı Başarı durumunda, önceliği alan **uzun** değişkeninin adresi.

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

## <a name="cbindstatuscallbackm_dwavailabletoread"></a><a name="m_dwavailabletoread"></a> CBindStatusCallback:: m_dwAvailableToRead

, Okunabilecek kullanılabilir bayt sayısını depolamak için kullanılabilir.

```
DWORD m_dwAvailableToRead;
```

### <a name="remarks"></a>Açıklamalar

İçinde sıfır olarak başlatıldı `StartAsyncDownload` .

## <a name="cbindstatuscallbackm_dwtotalread"></a><a name="m_dwtotalread"></a> CBindStatusCallback:: m_dwTotalRead

Zaman uyumsuz veri aktarımında okunan toplam bayt toplamı.

```
DWORD m_dwTotalRead;
```

### <a name="remarks"></a>Açıklamalar

`OnDataAvailable`Gerçekte okunan bayt sayısıyla her zaman artırılır. İçinde sıfır olarak başlatıldı `StartAsyncDownload` .

## <a name="cbindstatuscallbackm_pfunc"></a><a name="m_pfunc"></a> CBindStatusCallback:: m_pFunc

Tarafından işaret edilen işlev, `m_pFunc` `OnDataAvailable` kullanılabilir verileri okuduktan sonra (örneğin, verileri depolamak veya ekranda yazdırmak için) çağrılır.

```
ATL_PDATAAVAILABLE m_pFunc;
```

### <a name="remarks"></a>Açıklamalar

Tarafından işaret edilen işlev, `m_pFunc` nesnenizin sınıfının bir üyesidir ve aşağıdaki sözdizimine sahiptir:

```cpp
void Function_Name(
   CBindStatusCallback<T>* pbsc,
   BYTE* pBytes,
   DWORD dwSize
   );
```

## <a name="cbindstatuscallbackm_pt"></a><a name="m_pt"></a> CBindStatusCallback:: m_pT

Zaman uyumsuz veri aktarımı isteyen nesneye yönelik bir işaretçi.

```
T* m_pT;
```

### <a name="remarks"></a>Açıklamalar

`CBindStatusCallback`Nesne bu nesnenin sınıfında şablonsaldır.

## <a name="cbindstatuscallbackm_spbindctx"></a><a name="m_spbindctx"></a> CBindStatusCallback:: m_spBindCtx

Bağlama bağlamına (belirli bir bilinen ad bağlama işlemi hakkında bilgi depolayan bir nesne) erişim sağlayan bir [IBindCtx](/windows/win32/api/objidl/nn-objidl-ibindctx) arabirimine yönelik bir işaretçi.

```
CComPtr<IBindCtx> m_spBindCtx;
```

### <a name="remarks"></a>Açıklamalar

İçinde başlatıldı `StartAsyncDownload` .

## <a name="cbindstatuscallbackm_spbinding"></a><a name="m_spbinding"></a> CBindStatusCallback:: m_spBinding

`IBinding`Geçerli bağlama işleminin arabirimine yönelik bir işaretçi.

```
CComPtr<IBinding> m_spBinding;
```

### <a name="remarks"></a>Açıklamalar

' De başlatılmış `OnStartBinding` ve serbest bırakıldı `OnStopBinding` .

## <a name="cbindstatuscallbackm_spmoniker"></a><a name="m_spmoniker"></a> CBindStatusCallback:: m_spMoniker

Kullanılacak URL için [IMoniker](/windows/win32/api/objidl/nn-objidl-imoniker) arabirimine yönelik bir işaretçi.

```
CComPtr<IMoniker> m_spMoniker;
```

### <a name="remarks"></a>Açıklamalar

İçinde başlatıldı `StartAsyncDownload` .

## <a name="cbindstatuscallbackm_spstream"></a><a name="m_spstream"></a> CBindStatusCallback:: m_spStream

Geçerli bağlama işleminin [IStream](/windows/win32/api/objidl/nn-objidl-istream) arabirimine yönelik bir işaretçi.

```
CComPtr<IStream> m_spStream;
```

### <a name="remarks"></a>Açıklamalar

Bcsf bayrağı `OnDataAvailable` `STGMEDIUM` BCSF_FIRSTDATANOTIFICATION olduğunda ve sonra bcsf bayrağı BCSF_LASTDATANOTIFICATION olduğunda yapıdan başlatılır.

## <a name="cbindstatuscallbackondataavailable"></a><a name="ondataavailable"></a> CBindStatusCallback:: OnDataAvailable

Sistem tarafından sağlanan zaman uyumsuz bilinen ad, `OnDataAvailable` nesne kullanılabilir hale geldiğinde verileri sağlamak için çağırır.

```
STDMETHOD(
    OnDataAvailable)(DWORD grfBSCF,
    DWORD dwSize,
    FORMATETC* /* pformatetc */,
    STGMEDIUM* pstgmed);
```

### <a name="parameters"></a>Parametreler

*grfBSCF*<br/>
'ndaki Bir BSCF numaralandırma değeri. Aşağıdakilerden biri veya daha fazlası: BSCF_FIRSTDATANOTIFICATION, BSCF_INTERMEDIARYDATANOTIFICATION veya BSCF_LASTDATANOTIFICATION.

*dwSize*<br/>
'ndaki Bağlamanın başlangıcından bu yana kullanılabilir verilerin birikmeli miktarı (bayt cinsinden). Sıfır olabilir, verilerin miktarının ilgili olmadığını veya belirli bir tutarın kullanılabilir olmadığını gösterir.

*pFormatetc*<br/>
'ndaki Kullanılabilir verilerin biçimini içeren [FORMATETC](/windows/win32/com/the-formatetc-structure) yapısına yönelik işaretçi. Biçim yoksa CF_NULL olabilir.

*pstgmed*<br/>
'ndaki Gerçek verilerin bulunduğu [Stgorta](/windows/win32/com/the-stgmedium-structure) yapısına yönelik işaretçi artık kullanılabilir.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

`OnDataAvailable` verileri okur, ardından nesnenizin sınıfının bir yöntemini çağırır (örneğin, verileri depolamak veya ekranda yazdırmak için). Ayrıntılar için bkz. [CBindStatusCallback:: StartAsyncDownload](#startasyncdownload) .

## <a name="cbindstatuscallbackonlowresource"></a><a name="onlowresource"></a> CBindStatusCallback:: OnLowResource

Kaynaklar azaldığında çağırılır.

```
STDMETHOD(OnLowResource)(DWORD /* dwReserved */);
```

### <a name="parameters"></a>Parametreler

*Dwayrýlmýþ*<br/>
Ayrılmış.

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

## <a name="cbindstatuscallbackonobjectavailable"></a><a name="onobjectavailable"></a> CBindStatusCallback:: OnObjectAvailable

Uygulamanıza bir nesne arabirimi işaretçisi geçirmek için zaman uyumsuz bilinen ad tarafından çağırılır.

```
STDMETHOD(OnObjectAvailable)(REFID /* riid */, IUnknown* /* punk */);
```

### <a name="parameters"></a>Parametreler

*riıd*<br/>
İstenen arabirimin arabirim tanımlayıcısı. Kullanılmıyor.

*punk dili*<br/>
IUnknown arabiriminin adresi. Kullanılmıyor.

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

## <a name="cbindstatuscallbackonprogress"></a><a name="onprogress"></a> CBindStatusCallback:: OnProgress

Bir veri indirme işleminin ilerlemesini göstermek için çağırılır.

```
STDMETHOD(OnProgress)(
    ULONG /* ulProgress */,
    ULONG /* ulProgressMax */,
    ULONG /* ulStatusCode */,
    LPCWSTRONG /* szStatusText */);
```

### <a name="parameters"></a>Parametreler

*ulProgress*<br/>
İşaretsiz uzun tamsayı. Kullanılmıyor.

*ulProgressMax*<br/>
İşaretsiz uzun tamsayı kullanılmıyor.

*ulStatusCode*<br/>
İşaretsiz uzun tamsayı. Kullanılmıyor.

*szStatusText*<br/>
Bir dize değerinin adresi. Kullanılmıyor.

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

## <a name="cbindstatuscallbackonstartbinding"></a><a name="onstartbinding"></a> CBindStatusCallback:: OnStartBinding

Veri üyesini, [](#m_spbinding) `IBinding` *pbinding* içindeki işaretçiye m_spBinding ayarlar.

```
STDMETHOD(OnStartBinding)(DWORD /* dwReserved */, IBinding* pBinding);
```

### <a name="parameters"></a>Parametreler

*Dwayrýlmýþ*<br/>
Daha sonraki kullanımlar için ayrılmıştır.

*pBinding*<br/>
'ndaki Geçerli bağlama işleminin IBinding arabiriminin adresi. Bu NULL olamaz. İstemci, bağlama nesnesine bir başvuru tutmak için bu işaretçi üzerinde AddRef 'i çağırmalıdır.

## <a name="cbindstatuscallbackonstopbinding"></a><a name="onstopbinding"></a> CBindStatusCallback:: OnStopBinding

`IBinding` [M_spBinding](#m_spbinding)veri üyesinde işaretçiyi serbest bırakır.

```
STDMETHOD(OnStopBinding)(HRESULT hresult, LPCWSTR /* szError */);
```

### <a name="parameters"></a>Parametreler

*HRESULT*<br/>
Bağlama işleminden döndürülen durum kodu.

*szError*<br/>
Bir dize değerinin adresi. Kullanılmıyor.

### <a name="remarks"></a>Açıklamalar

Bağlama işleminin sonunu belirtmek için sistem tarafından sağlanan zaman uyumsuz bilinen ad tarafından çağırılır.

## <a name="cbindstatuscallbackstartasyncdownload"></a><a name="startasyncdownload"></a> CBindStatusCallback:: StartAsyncDownload

Verileri belirtilen URL 'den zaman uyumsuz olarak indirmeye başlar.

```
HRESULT StartAsyncDownload(
    T* pT,
    ATL_PDATAAVAILABLE pFunc,
    BSTR bstrURL,
    IUnknown* pUnkContainer = NULL,
    BOOL bRelative = FALSE);
```

### <a name="parameters"></a>Parametreler

*Yönergelerinin*<br/>
'ndaki Zaman uyumsuz veri aktarımı isteyen nesneye yönelik bir işaretçi. `CBindStatusCallback`Nesne bu nesnenin sınıfında şablonsaldır.

*pFunc*<br/>
'ndaki Okunan verileri alan işleve yönelik bir işaretçi. İşlevi, nesnenizin türü sınıfının bir üyesidir `T` . Sözdizimi ve örnek için **açıklamalar** bölümüne bakın.

*bstrURL*<br/>
'ndaki Verilerin alınacağı URL. Herhangi bir geçerli URL veya dosya adı olabilir. NULL olamaz. Örneğin:

`CComBSTR mybstr =_T("http://somesite/data.htm")`

*pUnkContainer*<br/>
'ndaki `IUnknown` Kapsayıcının. Varsayılan olarak NULL.

*Bgöreli*<br/>
'ndaki URL 'nin göreli veya mutlak olduğunu belirten bir bayrak. Varsayılan olarak FALSE, yani URL mutlak bir değer.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Veriler her kullanılabilir olduğunda nesnesine gönderilir `OnDataAvailable` . `OnDataAvailable` verileri okur ve *pFunc* tarafından işaret edilen işlevi çağırır (örneğin, verileri depolamak veya ekranda yazdırmak için).

*PFunc* tarafından işaret edilen işlev, nesnenizin sınıfının bir üyesidir ve aşağıdaki sözdizimine sahiptir:

```cpp
void Function_Name(
    CBindStatusCallback<T>* pbsc,
    BYTE* pBytes,
    DWORD dwSize);
```

Aşağıdaki örnekte ( [zaman uyumsuz](../../overview/visual-cpp-samples.md) örnekten alınmıştır), işlev `OnData` alınan verileri bir metin kutusuna yazar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#87](../../atl/codesnippet/cpp/cbindstatuscallback-class_2.h)]

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
