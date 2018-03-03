---
title: "CBindStatusCallback sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- asynchronous data transfer [C++]
- data transfer [C++]
- data transfer [C++], asynchronous
- CBindStatusCallback class
ms.assetid: 0f5da276-6031-4418-b2a9-a4750ef29e77
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 19aa979cb69bdbf8d74acbd96291fac9af78c845
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cbindstatuscallback-class"></a>CBindStatusCallback sınıfı
Bu sınıf uygulayan `IBindStatusCallback` arabirimi.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T,
    int nBindFlags = BINDF_ASYNCHRONOUS |   BINDF_ASYNCSTORAGE | BINDF_GETNEWESTVERSION | BINDF_NOWRITECACHE>  
class ATL_NO_VTABLE CBindStatusCallback : public CComObjectRootEx
 <T ::_ThreadModel::ThreadModelNoCS>,
    public IBindStatusCallbackImpl<T>
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sınıfınıza içeren veri alındı olarak çağrılacak işlev.  
  
 *nBindFlags*  
 Tarafından döndürülen bağlama bayrakları belirtir [GetBindInfo](#getbindinfo). Varsayılan uygulama bağlama zaman uyumsuz olarak ayarlar, veri/nesnesi en yeni sürümünü alır ve alınan veriler disk önbelleğinde depolamaz.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CBindStatusCallback::CBindStatusCallback](#cbindstatuscallback)|Oluşturucu.|  
|[CBindStatusCallback:: ~ CBindStatusCallback](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CBindStatusCallback::Download](#download)|İndirme işlemi başlatır statik yöntemi oluşturur bir `CBindStatusCallback` nesne ve çağrıları `StartAsyncDownload`.|  
|[CBindStatusCallback::GetBindInfo](#getbindinfo)|Zaman uyumsuz ad isteği bilgilere oluşturulacak Bağ türü tarafından çağrılır.|  
|[CBindStatusCallback::GetPriority](#getpriority)|Bağlama işlemi önceliğini almak için zaman uyumsuz ad tarafından çağrılır. ATL uygulamasını döndürür `E_NOTIMPL`.|  
|[CBindStatusCallback::OnDataAvailable](#ondataavailable)|Kullanılabilir olduğunda, uygulamanızın veri sağlamak için çağrılır. Veri okur ve verileri kullanmak için kendisine geçirilen işlevi çağırır.|  
|[CBindStatusCallback::OnLowResource](#onlowresource)|Kaynakları düşük olduğunda çağrılır. ATL uygulamasını döndürür `S_OK`.|  
|[CBindStatusCallback::OnObjectAvailable](#onobjectavailable)|Uygulamanız için bir nesne arabirimi işaretçisi geçirmek için zaman uyumsuz ad tarafından çağrılır. ATL uygulamasını döndürür `S_OK`.|  
|[CBindStatusCallback::OnProgress](#onprogress)|Yükleme işlemi veri ilerlemeyi göstermek için çağrılır. ATL uygulamasını döndürür `S_OK`.|  
|[CBindStatusCallback::OnStartBinding](#onstartbinding)|Bağlama başlatıldığında çağrılır.|  
|[CBindStatusCallback::OnStopBinding](#onstopbinding)|Zaman uyumsuz veri aktarımını durdurulduğunda çağrılır.|  
|[CBindStatusCallback::StartAsyncDownload](#startasyncdownload)|Kullanılabilir bayt sayısı başlatır ve sıfır olarak bayt okuma itme türü stream nesnesi bir URL ve çağrıları oluşturur `OnDataAvailable` veriler kullanılabilir her zaman.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CBindStatusCallback::m_dwAvailableToRead](#m_dwavailabletoread)|Okumak kullanılabilir bayt sayısı.|  
|[CBindStatusCallback::m_dwTotalRead](#m_dwtotalread)|Okunan toplam bayt sayısı.|  
|[CBindStatusCallback::m_pFunc](#m_pfunc)|Veriler kullanılabilir olduğunda işlev işaretçisi olarak adlandırılır.|  
|[CBindStatusCallback::m_pT](#m_pt)|Zaman uyumsuz veri aktarımı isteyen nesnesine işaretçi.|  
|[CBindStatusCallback::m_spBindCtx](#m_spbindctx)|İşaretçi [IBindCtx](http://msdn.microsoft.com/library/windows/desktop/ms693755) geçerli bağlama işlemi için arabirim.|  
|[CBindStatusCallback::m_spBinding](#m_spbinding)|İşaretçi `IBinding` geçerli bağlama işlemi için arabirim.|  
|[CBindStatusCallback::m_spMoniker](#m_spmoniker)|İşaretçi [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) arabirimi için kullanılacak URL.|  
|[CBindStatusCallback::m_spStream](#m_spstream)|İşaretçi [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) veri aktarımı için arabirim.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CBindStatusCallback` Uygulayan sınıf `IBindStatusCallback` arabirimi. `IBindStatusCallback`bir zaman uyumsuz veri aktarımı bildirimleri alabilecek şekilde uygulama tarafından uygulanmalıdır. Sistem tarafından sağlanan zaman uyumsuz ad kullanan `IBindStatusCallback` göndermek ve zaman uyumsuz veriler hakkında bilgi almak için yöntemleri aktarım nesnenizin gelen ve giden.  
  
 Genellikle, `CBindStatusCallback` nesne belirli bağlama işlemi ile ilişkili değil. Örneğin, [zaman UYUMSUZ](../../visual-cpp-samples.md) örnek, URL özelliğini ayarlarken oluşturduğu bir `CBindStatusCallback` çağrısı nesnesinde `Download`:  
  
 [!code-cpp[NVC_ATL_Windowing#86](../../atl/codesnippet/cpp/cbindstatuscallback-class_1.h)]  
  
 Zaman uyumsuz ad geri çağırma işlevini kullanıyor `OnData` veri sahip olduğunda, uygulamanızın çağırmak için. Zaman uyumsuz ad sistem tarafından sağlanır.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CComObjectRootBase`  
  
 `IBindStatusCallback`  
  
 [İn uygulamasına](../../atl/reference/ccomobjectrootex-class.md)  
  
 `CBindStatusCallback`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlctl.h  
  
##  <a name="cbindstatuscallback"></a>CBindStatusCallback::CBindStatusCallback  
 Oluşturucu.  
  
```
CBindStatusCallback();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Zaman uyumsuz veri aktarımı ile ilgili bildirimleri almak için bir nesne oluşturur. Genellikle, bir nesne her bağlama işlemi için oluşturulur.  
  
 Oluşturucu ayrıca başlatır [m_pT](#m_pt) ve [m_pFunc](#m_pfunc) için **NULL**.  
  
##  <a name="dtor"></a>CBindStatusCallback:: ~ CBindStatusCallback  
 Yok Edicisi.  
  
```
~CBindStatusCallback();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrılan tüm kaynakları serbest bırakır.  
  
##  <a name="download"></a>CBindStatusCallback::Download  
 Oluşturur bir `CBindStatusCallback` nesne ve çağrıları `StartAsyncDownload` verileri zaman uyumsuz olarak belirtilen URL'den indirmeye başlayın.  
  
```
static HRESULT Download(  
    T* pT,
    ATL_PDATAAVAILABLE pFunc,
    BSTR bstrURL,
    IUnknown* pUnkContainer = NULL,
    BOOL bRelative = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 *pT*  
 [in] Zaman uyumsuz veri aktarımı isteyen nesnesine bir işaretçi. `CBindStatusCallback` Nesne şablonlaştırılmış bu nesne sınıfı üzerinde.  
  
 *pFunc*  
 [in] Salt okunur verileri alan işlevi için bir işaretçi. İşlev türü, nesnenin sınıf üyesi olan `T`. Bkz: [StartAsyncDownload](#startasyncdownload) sözdizimi ve bir örnek için.  
  
 `bstrURL`  
 [in] Verileri almak için URL. Herhangi bir geçerli URL veya dosya adı olabilir. Olamaz **NULL**. Örneğin:  
  
 `CComBSTR mybstr =_T("http://somesite/data.htm")`  
  
 `pUnkContainer`  
 [in] **IUnknown** kapsayıcısının. **NULL** varsayılan olarak.  
  
 `bRelative`  
 [in] URL göreli veya mutlak olup olmadığını belirten bir bayrak. **YANLIŞ** varsayılan olarak, URL anlamına gelir mutlak.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart birini `HRESULT` değerleri.  
  
### <a name="remarks"></a>Açıklamalar  
 Veriler kullanılabilir her zaman nesnesi üzerinden gönderilir `OnDataAvailable`. `OnDataAvailable`Veri okur ve gösterdiği işlevi çağırır *pFunc* (örneğin, verileri depolamak veya ekrana yazdırmak için).  
  
##  <a name="getbindinfo"></a>CBindStatusCallback::GetBindInfo  
 Ad nasıl bağlanacağını belirtmek için çağrılır.  
  
```
STDMETHOD(GetBindInfo)(
    DWORD* pgrfBSCF,
    BINDINFO* pbindinfo);
```  
  
### <a name="parameters"></a>Parametreler  
 *pgrfBSCF*  
 [out] Bir işaretçi **BINDF** bağlama işleminin nasıl yapılacağını belirten numaralandırma değerlerinin. Varsayılan olarak, aşağıdaki numaralandırma değerleri ile ayarlayın:  
  
 **BINDF_ASYNCHRONOUS** zaman uyumsuz indirme.  
  
 **BINDF_ASYNCSTORAGE** `OnDataAvailable` döndürür **E_PENDING** ne zaman veri henüz veri kullanılabilir hale gelene kadar engelleme yerine kullanılabilir değil.  
  
 **BINDF_GETNEWESTVERSION** bağlama işlemi verileri en yeni sürümünü almak.  
  
 **BINDF_NOWRITECACHE** bağlama işlemi alınan veriler disk önbelleğinde saklamalısınız değil.  
  
 *pbindinfo*  
 [içinde out] Bir işaretçi **bağlama bilgisi** nasıl gerçekleşmesi için bağlama nesnesi istediği hakkında daha fazla bilgi veren yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart birini `HRESULT` değerleri.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama bağlama zaman uyumsuz ve veri gönderme modeli kullanacak şekilde ayarlar. Veri gönderimi modelindeki ad zaman uyumsuz bağlama işlemi sürücüler ve yeni veriler kullanılabilir olduğunda istemci sürekli olarak bildirir.  
  
##  <a name="getpriority"></a>CBindStatusCallback::GetPriority  
 Bağlama işlemi önceliğini almak için zaman uyumsuz ad tarafından çağrılır.  
  
```
STDMETHOD(GetPriority)(LONG* pnPriority);
```  
  
### <a name="parameters"></a>Parametreler  
 *pnPriority*  
 [out] Adres **uzun** başarılıysa önceliği alır, değişkeni.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **E_NOTIMPL**.  
  
##  <a name="m_dwavailabletoread"></a>CBindStatusCallback::m_dwAvailableToRead  
 Okunacak kullanılabilir bayt sayısını depolamak için kullanılabilir.  
  
```
DWORD m_dwAvailableToRead;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Sıfıra başlatılmış `StartAsyncDownload`.  
  
##  <a name="m_dwtotalread"></a>CBindStatusCallback::m_dwTotalRead  
 Toplam bayt sayısı zaman uyumsuz veri aktarma işleminde okuyun.  
  
```
DWORD m_dwTotalRead;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Her zaman artar `OnDataAvailable` gerçekte okunan bayt sayısını tarafından çağrılır. Sıfıra başlatılmış `StartAsyncDownload`.  
  
##  <a name="m_pfunc"></a>CBindStatusCallback::m_pFunc  
 Tarafından işlevi işaret için `m_pFunc` tarafından çağrılır `OnDataAvailable` (örneğin, verileri depolamak veya ekrana yazdırmak için) kullanılabilir veri okuduktan sonra.  
  
```
ATL_PDATAAVAILABLE m_pFunc;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından işlevi işaret için `m_pFunc` , nesnenin sınıfı bir üyesidir ve sözdizimi aşağıdaki gibidir:  
  
```  
void Function_Name(  
   CBindStatusCallback<T>* pbsc,  
   BYTE* pBytes,  
   DWORD dwSize  
   );  
```  
  
##  <a name="m_pt"></a>CBindStatusCallback::m_pT  
 Zaman uyumsuz veri aktarımı isteyen nesnesine bir işaretçi.  
  
```
T* m_pT;
```  
  
### <a name="remarks"></a>Açıklamalar  
 `CBindStatusCallback` Nesne şablonlaştırılmış bu nesne sınıfı üzerinde.  
  
##  <a name="m_spbindctx"></a>CBindStatusCallback::m_spBindCtx  
 Bir işaretçi bir [IBindCtx](http://msdn.microsoft.com/library/windows/desktop/ms693755) bağlama bağlamı (belirli ad bağlama işlemi hakkında bilgi depolayan bir nesne) erişim sağlayan arabirim.  
  
```
CComPtr<IBindCtx> m_spBindCtx;
```  
  
### <a name="remarks"></a>Açıklamalar  
 İçinde başlatılmış `StartAsyncDownload`.  
  
##  <a name="m_spbinding"></a>CBindStatusCallback::m_spBinding  
 Bir işaretçi `IBinding` geçerli bağlama işleminin arabirimi.  
  
```
CComPtr<IBinding> m_spBinding;
```  
  
### <a name="remarks"></a>Açıklamalar  
 İçinde başlatılmış `OnStartBinding` ve de serbest `OnStopBinding`.  
  
##  <a name="m_spmoniker"></a>CBindStatusCallback::m_spMoniker  
 Bir işaretçi [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) arabirimi için kullanılacak URL.  
  
```
CComPtr<IMoniker> m_spMoniker;
```  
  
### <a name="remarks"></a>Açıklamalar  
 İçinde başlatılmış `StartAsyncDownload`.  
  
##  <a name="m_spstream"></a>CBindStatusCallback::m_spStream  
 Bir işaretçi [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) geçerli bağlama işleminin arabirimi.  
  
```
CComPtr<IStream> m_spStream;
```  
  
### <a name="remarks"></a>Açıklamalar  
 İçinde başlatılmış `OnDataAvailable` gelen **STGMEDIUM** ne zaman yapısı **BCSF** bayrağı **BCSF_FIRSTDATANOTIFICATION** ve ne zaman serbest **BCSF**  bayrağı **BCSF_LASTDATANOTIFICATION**.  
  
##  <a name="ondataavailable"></a>CBindStatusCallback::OnDataAvailable  
 Sistem tarafından sağlanan zaman uyumsuz ad çağrıları `OnDataAvailable` kullanılabilir hale geldiğinde nesneye veri sağlamak için.  
  
```
STDMETHOD(  
    OnDataAvailable)(DWORD grfBSCF,
    DWORD dwSize,
    FORMATETC* /* pformatetc */,
    STGMEDIUM* pstgmed);
```  
  
### <a name="parameters"></a>Parametreler  
 *grfBSCF*  
 [in] A **BSCF** numaralandırma değeri. Bir veya daha fazlasını: **BSCF_FIRSTDATANOTIFICATION**, **BSCF_INTERMEDIARYDATANOTIFICATION**, veya **BSCF_LASTDATANOTIFICATION**.  
  
 `dwSize`  
 [in] Toplu miktarı (bayt cinsinden) veri bağlama başına itibaren kullanılabilir. Veri miktarını ilgili değildir veya belirli bir miktar kullanılabilen gösteren sıfır olabilir.  
  
 *pformatetc*  
 [in] İşaretçi [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682242) kullanılabilir veri biçimi içeren yapısı. Biçim yok ise olabilir **CF_NULL**.  
  
 *pstgmed*  
 [in] İşaretçi [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms695269) sunuldu gerçek verileri tutar yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart birini `HRESULT` değerleri.  
  
### <a name="remarks"></a>Açıklamalar  
 `OnDataAvailable`Veri okur ve sonra (örneğin, verileri depolamak veya ekrana yazdırmak için), nesnenin sınıfının bir yöntemi çağırır. Bkz: [CBindStatusCallback::StartAsyncDownload](#startasyncdownload) Ayrıntılar için.  
  
##  <a name="onlowresource"></a>CBindStatusCallback::OnLowResource  
 Kaynakları düşük olduğunda çağrılır.  
  
```
STDMETHOD(OnLowResource)(DWORD /* dwReserved */);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwReserved`  
 Ayrılmış.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK`.  
  
##  <a name="onobjectavailable"></a>CBindStatusCallback::OnObjectAvailable  
 Uygulamanız için bir nesne arabirimi işaretçisi geçirmek için zaman uyumsuz ad tarafından çağrılır.  
  
```
STDMETHOD(OnObjectAvailable)(REFID /* riid */, IUnknown* /* punk */);
```  
  
### <a name="parameters"></a>Parametreler  
 `riid`  
 İstenen arabirimi arabirim tanımlayıcısı. Kullanılmayan.  
  
 `punk`  
 IUnknown arabirimi adresidir. Kullanılmayan.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK`.  
  
##  <a name="onprogress"></a>CBindStatusCallback::OnProgress  
 Yükleme işlemi veri ilerlemeyi göstermek için çağrılır.  
  
```
STDMETHOD(OnProgress)(
    ULONG /* ulProgress */,
    ULONG /* ulProgressMax */,
    ULONG /* ulStatusCode */,
    LPCWSTRONG /* szStatusText */);
```  
  
### <a name="parameters"></a>Parametreler  
 `ulProgress`  
 İmzasız uzun tamsayı. Kullanılmayan.  
  
 `ulProgressMax`  
 İmzasız uzun tamsayı kullanılmıyor.  
  
 `ulStatusCode`  
 İmzasız uzun tamsayı. Kullanılmayan.  
  
 `szStatusText`  
 Bir dize değeri adresidir. Kullanılmayan.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK`.  
  
##  <a name="onstartbinding"></a>CBindStatusCallback::OnStartBinding  
 Veri üyesi ayarlar [m_spBinding](#m_spbinding) için `IBinding` işaretçiyi `pBinding`.  
  
```
STDMETHOD(OnStartBinding)(DWORD /* dwReserved */, IBinding* pBinding);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwReserved`  
 Daha sonraki kullanımlar için ayrılmıştır.  
  
 `pBinding`  
 [in] Geçerli IBinding arabiriminin adresini işlemi bağlayın. Bu NULL olamaz. İstemci AddRef bağlama nesnesine başvuru tutmak için bu işaretçinin çağırmanız gerekir.  
  
##  <a name="onstopbinding"></a>CBindStatusCallback::OnStopBinding  
 Sürümler `IBinding` veri üyesi işaretçiyi [m_spBinding](#m_spbinding).  
  
```
STDMETHOD(OnStopBinding)(HRESULT hresult, LPCWSTR /* szError */);
```  
  
### <a name="parameters"></a>Parametreler  
 `hresult`  
 Bağlama işlemi durum kodunu döndürdü.  
  
 szStatusText  
 Bir dize değeri kullanılmayan adres.  
  
### <a name="remarks"></a>Açıklamalar  
 Bağlama işlemi sonunu belirtmek üzere sistem tarafından sağlanan zaman uyumsuz ad tarafından çağrılır.  
  
##  <a name="startasyncdownload"></a>CBindStatusCallback::StartAsyncDownload  
 Verileri zaman uyumsuz olarak belirtilen URL'den başlatır.  
  
```
HRESULT StartAsyncDownload(  
    T* pT,
    ATL_PDATAAVAILABLE pFunc,
    BSTR bstrURL,
    IUnknown* pUnkContainer = NULL,
    BOOL bRelative = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 *pT*  
 [in] Zaman uyumsuz veri aktarımı isteyen nesnesine bir işaretçi. `CBindStatusCallback` Nesne şablonlaştırılmış bu nesne sınıfı üzerinde.  
  
 *pFunc*  
 [in] Okunan verileri alan işlevi için bir işaretçi. İşlev türü, nesnenin sınıf üyesi olan `T`. Bkz: **açıklamalar** sözdizimi ve bir örnek için.  
  
 `bstrURL`  
 [in] Verileri almak için URL. Herhangi bir geçerli URL veya dosya adı olabilir. Olamaz **NULL**. Örneğin:  
  
 `CComBSTR mybstr =_T("http://somesite/data.htm")`  
  
 `pUnkContainer`  
 [in] **IUnknown** kapsayıcısının. **NULL** varsayılan olarak.  
  
 `bRelative`  
 [in] URL göreli veya mutlak olup olmadığını belirten bir bayrak. **YANLIŞ** varsayılan olarak, URL anlamına gelir mutlak.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart birini `HRESULT` değerleri.  
  
### <a name="remarks"></a>Açıklamalar  
 Veriler kullanılabilir her zaman nesnesi üzerinden gönderilir `OnDataAvailable`. `OnDataAvailable`Veri okur ve gösterdiği işlevi çağırır *pFunc* (örneğin, verileri depolamak veya ekrana yazdırmak için).  
  
 Tarafından işlevi işaret için *pFunc* , nesnenin sınıfı bir üyesidir ve sözdizimi aşağıdaki gibidir:  
  
 `void Function_Name(`  
  
 `CBindStatusCallback<T>*` `pbsc` `,`  
  
 `BYTE*` `pBytes` `,`  
  
 `DWORD``dwSize`  
  
 `);`  
  
 Aşağıdaki örnekte (alınan [zaman UYUMSUZ](../../visual-cpp-samples.md) örnek), işlevi `OnData` metin kutusuna alınan verileri yazar.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#87](../../atl/codesnippet/cpp/cbindstatuscallback-class_2.h)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
