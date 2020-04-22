---
title: CBindStatusCallback Sınıfı
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
ms.openlocfilehash: 0ae7f4fcdba18be84d99140e395b6f2ac3db792a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748203"
---
# <a name="cbindstatuscallback-class"></a>CBindStatusCallback Sınıfı

Bu sınıf `IBindStatusCallback` arabirimi uygular.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class T,
    int nBindFlags = BINDF_ASYNCHRONOUS | BINDF_ASYNCSTORAGE | BINDF_GETNEWESTVERSION | BINDF_NOWRITECACHE>
class ATL_NO_VTABLE CBindStatusCallback : public CComObjectRootEx <T ::_ThreadModel::ThreadModelNoCS>,
    public IBindStatusCallbackImpl<T>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Verileriniz alındıkça çağrılacak işlevi içeren sınıfınız.

*nBindBayraklar*<br/>
[GetBindInfo](#getbindinfo)tarafından döndürülen bağlama bayraklarını belirtir. Varsayılan uygulama bağlamayı eşzamanlı olarak ayarlar, veri/nesnenin en yeni sürümünü alır ve alınan verileri disk önbelleğinde depolamaz.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CBindStatusCallback::CBindStatusCallback](#cbindstatuscallback)|Oluşturucu.|
|[CBindStatusCallback::~CBindStatusCallback](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CBindStatusCallback::Download](#download)|İndirme işlemini başlatan, bir `CBindStatusCallback` nesne oluşturan `StartAsyncDownload`ve çağıran statik yöntem.|
|[CBindStatusCallback::GetBindInfo](#getbindinfo)|Oluşturulacak bağlama türü hakkında bilgi istemek için asynchronous lakap tarafından çağrılır.|
|[CBindStatusCallback::GetPriority](#getpriority)|Bağlama işleminin önceliğini almak için asynchronous lakabı yla çağrıldı. ATL uygulaması `E_NOTIMPL`döndürür.|
|[CBindStatusCallback::OnDataAvailable](#ondataavailable)|Kullanılabilir olduğunda uygulamanıza veri sağlamak için çağrılır. Verileri okur, sonra verileri kullanmak için kendisine geçen işlevi çağırır.|
|[CBindStatusCallback::OnLowResource](#onlowresource)|Kaynaklar düşük olduğunda çağrılır. ATL uygulaması S_OK döndürür.|
|[CBindStatusCallback::OnObjectAvailable](#onobjectavailable)|Uygulamanıza bir nesne arabirimi işaretçisi geçmek için asynchronous takma ad tarafından çağrılır. ATL uygulaması S_OK döndürür.|
|[CBindStatusCallback::OnProgress](#onprogress)|Veri indirme işleminin ilerlemesini belirtmek için çağrıldı. ATL uygulaması S_OK döndürür.|
|[CBindStatusCallback::OnStartBinding](#onstartbinding)|Bağlama başlatıldığında çağrılır.|
|[CBindStatusCallback::OnStopBinding](#onstopbinding)|Eşzamanlı veri aktarımı durdurulduğunda çağrılır.|
|[CBindStatusCallback::StartAsyncDownload](#startasyncdownload)|Kullanılabilir baytları ve sıfıra okunan baytları başolarak karşılar, URL'den bir `OnDataAvailable` push-type akış nesnesi oluşturur ve her veri kullanılabilir olduğunda çağırır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CBindStatusCallback::m_dwAvailableToRead](#m_dwavailabletoread)|Okunabilecek bayt sayısı.|
|[CBindStatusCallback::m_dwTotalRead](#m_dwtotalread)|Toplam bayt sayısı okunur.|
|[CBindStatusCallback::m_pFunc](#m_pfunc)|Veri kullanılabilir olduğunda çağrılan işleve işaretçi.|
|[CBindStatusCallback::m_pT](#m_pt)|Eşzamanlı veri aktarımını isteyen nesneye işaretçi.|
|[CBindStatusCallback::m_spBindCtx](#m_spbindctx)|Geçerli bağlama işlemi için [IBindCtx](/windows/win32/api/objidl/nn-objidl-ibindctx) arabirimine işaretçi.|
|[CBindStatusCallback::m_spBinding](#m_spbinding)|Geçerli bağlama `IBinding` işlemi için arabirimi işaretçi.|
|[CBindStatusCallback::m_spMoniker](#m_spmoniker)|URL'nin kullanması için [iMoniker](/windows/win32/api/objidl/nn-objidl-imoniker) arabirimine işaretçi.|
|[CBindStatusCallback::m_spStream](#m_spstream)|Veri aktarımı için [IStream](/windows/win32/api/objidl/nn-objidl-istream) arabirimine işaretçi.|

## <a name="remarks"></a>Açıklamalar

`CBindStatusCallback` sınıfı, `IBindStatusCallback` arabirimini uygular. `IBindStatusCallback`asynchronous veri aktarımı bildirimleri alabilirsiniz böylece uygulamanız tarafından uygulanmalıdır. Sistem tarafından sağlanan eşzamanlı takma ad, nesnenize ve nesnenizden eşzamanlı veri aktarımı hakkında bilgi göndermek ve almak için yöntemler kullanır. `IBindStatusCallback`

Genellikle, `CBindStatusCallback` nesne belirli bir bağlama işlemi ile ilişkilidir. Örneğin, [ASYNC](../../overview/visual-cpp-samples.md) örneğinde, URL özelliğini ayarladığınızda, çağrıda `CBindStatusCallback` bir nesne `Download`oluşturur:

[!code-cpp[NVC_ATL_Windowing#86](../../atl/codesnippet/cpp/cbindstatuscallback-class_1.h)]

Eşiz yamaç, veri saolduğunda `OnData` uygulamanızı aramak için geri arama işlevini kullanır. Asynchronous lakabı sistem tarafından sağlanır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CComObjectRootBase`

`IBindStatusCallback`

[Ccomobjectrootex](../../atl/reference/ccomobjectrootex-class.md)

`CBindStatusCallback`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl.h

## <a name="cbindstatuscallbackcbindstatuscallback"></a><a name="cbindstatuscallback"></a>CBindStatusCallback::CBindStatusCallback

Oluşturucu.

```
CBindStatusCallback();
```

### <a name="remarks"></a>Açıklamalar

Eşzamanlı veri aktarımı ile ilgili bildirimleralmak için bir nesne oluşturur. Genellikle, her bağlama işlemi için bir nesne oluşturulur.

Oluşturucu ayrıca [m_pT](#m_pt) ve [NULL'a m_pFunc](#m_pfunc) de çözer.

## <a name="cbindstatuscallbackcbindstatuscallback"></a><a name="dtor"></a>CBindStatusCallback::~CBindStatusCallback

Yıkıcı.

```
~CBindStatusCallback();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest sağlar.

## <a name="cbindstatuscallbackdownload"></a><a name="download"></a>CBindStatusCallback::Download

Bir `CBindStatusCallback` nesne oluşturur `StartAsyncDownload` ve belirtilen URL'den verileri eşit bir şekilde indirmeye başlamak için çağırır.

```
static HRESULT Download(
    T* pT,
    ATL_PDATAAVAILABLE pFunc,
    BSTR bstrURL,
    IUnknown* pUnkContainer = NULL,
    BOOL bRelative = FALSE);
```

### <a name="parameters"></a>Parametreler

*Pt*<br/>
[içinde] Asynchronous veri aktarımını isteyen nesneye işaretçi. Nesne `CBindStatusCallback` bu nesnenin sınıfında baştan çıkarıcıdır.

*pFunc*<br/>
[içinde] Okunan verileri alan işleve işaretçi. İşlev, nesnenizin sınıf türüne `T`üyedir. Sözdizimi ve bir örnek için [StartAsyncDownload'a](#startasyncdownload) bakın.

*bstrURL*<br/>
[içinde] Veri elde etmek için URL. Geçerli bir URL veya dosya adı olabilir. NULL olamaz. Örneğin:

`CComBSTR mybstr =_T("http://somesite/data.htm")`

*pUnkContainer*<br/>
[içinde] `IUnknown` Konteynerin. Varsayılan olarak NULL.

*bGöreceli*<br/>
[içinde] URL'nin göreceli mi yoksa mutlak mı olduğunu belirten bir bayrak. Varsayılan olarak FALSE, URL mutlak anlamına gelir.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Veriler her kullanılabilir olduğunda nesneye 'den' e `OnDataAvailable`gönderilir. `OnDataAvailable`verileri okur ve *pFunc* tarafından işaret edilen işlevi çağırır (örneğin, verileri depolamak veya ekrana yazdırmak için).

## <a name="cbindstatuscallbackgetbindinfo"></a><a name="getbindinfo"></a>CBindStatusCallback::GetBindInfo

Lakabına nasıl bağlanılsüreceğini söylemek için aradım.

```
STDMETHOD(GetBindInfo)(
    DWORD* pgrfBSCF,
    BINDINFO* pbindinfo);
```

### <a name="parameters"></a>Parametreler

*pgrfBSCF*<br/>
[çıkış] Bindf numaralandırma değerlerine işaretçi, bağlama işleminin nasıl gerçekleşmesi gerektiğini gösterir. Varsayılan olarak, aşağıdaki numaralandırma değerleri ile ayarlayın:

BINDF_ASYNCHRONOUS Asynchronous indir.

BINDF_ASYNCSTORAGE, `OnDataAvailable` veriler kullanılabilir olana kadar engellemek yerine henüz veri kullanılamadığında E_PENDING döndürür.

BINDF_GETNEWESTVERSION Bind işlemi verilerin en yeni sürümünü almalıdır.

BINDF_NOWRITECACHE Bağlama işlemi, alınan verileri disk önbelleğinde depolamamalıdır.

*pbindinfo*<br/>
[içinde, dışarı] Nesnenin bağlamanın `BINDINFO` nasıl oluşmasını istediği hakkında daha fazla bilgi veren yapının işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, bağlamayı eşzamanlı olarak ve veri itme modelini kullanacak şekilde ayarlar. Veri itme modelinde, takma adı asynchronous bağlama işlemini yönlendirir ve yeni veriler kullanılabilir olduğunda istemciyi sürekli olarak haber verirken.

## <a name="cbindstatuscallbackgetpriority"></a><a name="getpriority"></a>CBindStatusCallback::GetPriority

Bağlama işleminin önceliğini almak için asynchronous lakabı yla çağrıldı.

```
STDMETHOD(GetPriority)(LONG* pnPriority);
```

### <a name="parameters"></a>Parametreler

*pnÖncelikli*<br/>
[çıkış] Başarı üzerine önceliği alan **UZUN** değişkenin adresi.

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

## <a name="cbindstatuscallbackm_dwavailabletoread"></a><a name="m_dwavailabletoread"></a>CBindStatusCallback::m_dwAvailableToRead

Okunabilecek bayt sayısını depolamak için kullanılabilir.

```
DWORD m_dwAvailableToRead;
```

### <a name="remarks"></a>Açıklamalar

'de `StartAsyncDownload`sıfıra başlandı.

## <a name="cbindstatuscallbackm_dwtotalread"></a><a name="m_dwtotalread"></a>CBindStatusCallback::m_dwTotalRead

Asynchronous veri aktarımında okunan baytların kümülatif toplamı.

```
DWORD m_dwTotalRead;
```

### <a name="remarks"></a>Açıklamalar

Her zaman `OnDataAvailable` artış aslında okumak bayt sayısına göre denir. 'de `StartAsyncDownload`sıfıra başlandı.

## <a name="cbindstatuscallbackm_pfunc"></a><a name="m_pfunc"></a>CBindStatusCallback::m_pFunc

Tarafından işaret `m_pFunc` edilen işlev, `OnDataAvailable` kullanılabilir verileri okumadan sonra (örneğin, verileri depolamak veya ekrana yazdırmak) tarafından çağrılır.

```
ATL_PDATAAVAILABLE m_pFunc;
```

### <a name="remarks"></a>Açıklamalar

Işaret `m_pFunc` eden işlev nesnenizin sınıfının bir üyesidir ve aşağıdaki sözdizimine sahiptir:

```cpp
void Function_Name(
   CBindStatusCallback<T>* pbsc,
   BYTE* pBytes,
   DWORD dwSize
   );
```

## <a name="cbindstatuscallbackm_pt"></a><a name="m_pt"></a>CBindStatusCallback::m_pT

Asynchronous veri aktarımını isteyen nesneye işaretçi.

```
T* m_pT;
```

### <a name="remarks"></a>Açıklamalar

Nesne `CBindStatusCallback` bu nesnenin sınıfında baştan çıkarıcıdır.

## <a name="cbindstatuscallbackm_spbindctx"></a><a name="m_spbindctx"></a>CBindStatusCallback::m_spBindCtx

Bağlama bağlamına erişim sağlayan bir [IBindCtx](/windows/win32/api/objidl/nn-objidl-ibindctx) arabirimine işaretçi (belirli bir takma alan bağlama işlemi hakkında bilgi depolayan bir nesne).

```
CComPtr<IBindCtx> m_spBindCtx;
```

### <a name="remarks"></a>Açıklamalar

'de `StartAsyncDownload`başharf.

## <a name="cbindstatuscallbackm_spbinding"></a><a name="m_spbinding"></a>CBindStatusCallback::m_spBinding

Geçerli bağlama `IBinding` işleminin arabirimine işaretçi.

```
CComPtr<IBinding> m_spBinding;
```

### <a name="remarks"></a>Açıklamalar

İlk olarak `OnStartBinding` piyasaya `OnStopBinding`sürüldü ve içinde serbest bırakıldı.

## <a name="cbindstatuscallbackm_spmoniker"></a><a name="m_spmoniker"></a>CBindStatusCallback::m_spMoniker

URL'nin kullanması için [iMoniker](/windows/win32/api/objidl/nn-objidl-imoniker) arabirimine bir işaretçi.

```
CComPtr<IMoniker> m_spMoniker;
```

### <a name="remarks"></a>Açıklamalar

'de `StartAsyncDownload`başharf.

## <a name="cbindstatuscallbackm_spstream"></a><a name="m_spstream"></a>CBindStatusCallback::m_spStream

Geçerli bağlama işleminin [IStream](/windows/win32/api/objidl/nn-objidl-istream) arabirimine işaretçi.

```
CComPtr<IStream> m_spStream;
```

### <a name="remarks"></a>Açıklamalar

BCSF `OnDataAvailable` bayrağı `STGMEDIUM` BCSF_FIRSTDATANOTIFICATION ve BCSF bayrağı BCSF_LASTDATANOTIFICATION olduğunda serbest bırakıldığında yapıdan başharfe alınır.

## <a name="cbindstatuscallbackondataavailable"></a><a name="ondataavailable"></a>CBindStatusCallback::OnDataAvailable

Sistem tarafından sağlanan eşzamanlı takma ad, kullanılabilir `OnDataAvailable` olduğunda nesneye veri sağlamak için çağrıda bulunur.

```
STDMETHOD(
    OnDataAvailable)(DWORD grfBSCF,
    DWORD dwSize,
    FORMATETC* /* pformatetc */,
    STGMEDIUM* pstgmed);
```

### <a name="parameters"></a>Parametreler

*grfBSCF*<br/>
[içinde] Bir BSCF numaralandırma değeri. Aşağıdakilerden biri veya birkaçı: BSCF_FIRSTDATANOTIFICATION, BSCF_INTERMEDIARYDATANOTIFICATION veya BSCF_LASTDATANOTIFICATION.

*dwSize*<br/>
[içinde] Bağlamanın başlangıcından bu yana kullanılabilen verilerin kümülatif tutarı (baytlar içinde). Veri miktarının ilgili olmadığını veya belirli bir miktarın kullanılabilir olmadığını belirten sıfır olabilir.

*Pformatetc*<br/>
[içinde] Kullanılabilir verilerin biçimini içeren [FORMATETC](/windows/win32/com/the-formatetc-structure) yapısını işaretçi. Biçim yoksa, CF_NULL edilebilir.

*pstgmed*<br/>
[içinde] Gerçek verileri tutan [STGMEDIUM](/windows/win32/com/the-stgmedium-structure) yapısına işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

`OnDataAvailable`verileri okur, ardından nesnenizin sınıfının bir yöntemini çağırır (örneğin, verileri depolamak veya ekrana yazdırmak için). Ayrıntılar için [CBindStatusCallback::StartAsyncDownload](#startasyncdownload) bakın.

## <a name="cbindstatuscallbackonlowresource"></a><a name="onlowresource"></a>CBindStatusCallback::OnLowResource

Kaynaklar düşük olduğunda çağrılır.

```
STDMETHOD(OnLowResource)(DWORD /* dwReserved */);
```

### <a name="parameters"></a>Parametreler

*dwAyrılmış*<br/>
Ayrılmış.

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

## <a name="cbindstatuscallbackonobjectavailable"></a><a name="onobjectavailable"></a>CBindStatusCallback::OnObjectAvailable

Uygulamanıza bir nesne arabirimi işaretçisi geçmek için asynchronous takma ad tarafından çağrılır.

```
STDMETHOD(OnObjectAvailable)(REFID /* riid */, IUnknown* /* punk */);
```

### <a name="parameters"></a>Parametreler

*Riid*<br/>
İstenen arabirimin arabirim tanımlayıcısı. Kullanılmıyor.

*Punk*<br/>
IUnknown arabiriminin adresi. Kullanılmıyor.

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

## <a name="cbindstatuscallbackonprogress"></a><a name="onprogress"></a>CBindStatusCallback::OnProgress

Veri indirme işleminin ilerlemesini belirtmek için çağrıldı.

```
STDMETHOD(OnProgress)(
    ULONG /* ulProgress */,
    ULONG /* ulProgressMax */,
    ULONG /* ulStatusCode */,
    LPCWSTRONG /* szStatusText */);
```

### <a name="parameters"></a>Parametreler

*ulProgress*<br/>
İmzasız uzun tümseci. Kullanılmıyor.

*ulProgressMax*<br/>
İmzasız uzun tümseci Kullanılmaz.

*ulStatusCode*<br/>
İmzasız uzun tümseci. Kullanılmıyor.

*szStatusText*<br/>
Dize değerinin adresi. Kullanılmıyor.

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

## <a name="cbindstatuscallbackonstartbinding"></a><a name="onstartbinding"></a>CBindStatusCallback::OnStartBinding

veri [üyesini m_spBinding](#m_spbinding) `IBinding` *pBinding'deki*işaretçiye ayarlar.

```
STDMETHOD(OnStartBinding)(DWORD /* dwReserved */, IBinding* pBinding);
```

### <a name="parameters"></a>Parametreler

*dwAyrılmış*<br/>
Daha sonraki kullanımlar için ayrılmıştır.

*pBağlama*<br/>
[içinde] Geçerli bağlama işleminin IBinding arabiriminin adresi. Bu NULL olamaz. İstemci bağlayıcı nesneye bir başvuru tutmak için bu işaretçi üzerinde AddRef çağırmalıdır.

## <a name="cbindstatuscallbackonstopbinding"></a><a name="onstopbinding"></a>CBindStatusCallback::OnStopBinding

Veri `IBinding` [üyesi](#m_spbinding)m_spBinding işaretçisi bültenleri.

```
STDMETHOD(OnStopBinding)(HRESULT hresult, LPCWSTR /* szError */);
```

### <a name="parameters"></a>Parametreler

*Hresult*<br/>
Durum kodu bağlama işleminden döndürülür.

*szHata*<br/>
Dize değerinin adresi. Kullanılmıyor.

### <a name="remarks"></a>Açıklamalar

Bağlama işleminin sonunu belirtmek için sistem tarafından verilen eşzamanlı takma ad lakabıyla çağrılır.

## <a name="cbindstatuscallbackstartasyncdownload"></a><a name="startasyncdownload"></a>CBindStatusCallback::StartAsyncDownload

Belirtilen URL'den eşzamanlı olarak veri indirmeye başlar.

```
HRESULT StartAsyncDownload(
    T* pT,
    ATL_PDATAAVAILABLE pFunc,
    BSTR bstrURL,
    IUnknown* pUnkContainer = NULL,
    BOOL bRelative = FALSE);
```

### <a name="parameters"></a>Parametreler

*Pt*<br/>
[içinde] Asynchronous veri aktarımını isteyen nesneye işaretçi. Nesne `CBindStatusCallback` bu nesnenin sınıfında baştan çıkarıcıdır.

*pFunc*<br/>
[içinde] Okunan verileri alan işleve işaretçi. İşlev, nesnenizin sınıf türüne `T`üyedir. Sözdizimi ve bir örnek için **Açıklamalar'a** bakın.

*bstrURL*<br/>
[içinde] Veri elde etmek için URL. Geçerli bir URL veya dosya adı olabilir. NULL olamaz. Örneğin:

`CComBSTR mybstr =_T("http://somesite/data.htm")`

*pUnkContainer*<br/>
[içinde] `IUnknown` Konteynerin. Varsayılan olarak NULL.

*bGöreceli*<br/>
[içinde] URL'nin göreceli mi yoksa mutlak mı olduğunu belirten bir bayrak. Varsayılan olarak FALSE, URL mutlak anlamına gelir.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Veriler her kullanılabilir olduğunda nesneye 'den' e `OnDataAvailable`gönderilir. `OnDataAvailable`verileri okur ve *pFunc* tarafından işaret edilen işlevi çağırır (örneğin, verileri depolamak veya ekrana yazdırmak için).

*pFunc* tarafından işaret edilen işlev nesnenizin sınıfının bir üyesidir ve aşağıdaki sözdizimine sahiptir:

```cpp
void Function_Name(
    CBindStatusCallback<T>* pbsc,
    BYTE* pBytes,
    DWORD dwSize);
```

Aşağıdaki örnekte [(ASYNC](../../overview/visual-cpp-samples.md) örneğinden alınan), `OnData` işlev alınan verileri bir metin kutusuna yazar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#87](../../atl/codesnippet/cpp/cbindstatuscallback-class_2.h)]

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
