---
title: CBindStatusCallback sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a8df8ef2a0846f5ac90a2adfc53fa64da92930f3
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37881246"
---
# <a name="cbindstatuscallback-class"></a>CBindStatusCallback sınıfı
Bu sınıfın uyguladığı `IBindStatusCallback` arabirimi.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T,
    int nBindFlags = BINDF_ASYNCHRONOUS |   BINDF_ASYNCSTORAGE | BINDF_GETNEWESTVERSION | BINDF_NOWRITECACHE>  
class ATL_NO_VTABLE CBindStatusCallback : public CComObjectRootEx
 <T ::_ThreadModel::ThreadModelNoCS>,
    public IBindStatusCallbackImpl<T>
```  
  
#### <a name="parameters"></a>Parametreler  
 *T*  
 Kendi sınıfınızı içeren veri alındı olarak çağrılacak işlev.  
  
 *nBindFlags*  
 Tarafından döndürülen bağlama bayrakları belirtir [GetBindInfo](#getbindinfo). Varsayılan uygulama bağlama zaman uyumsuz olarak ayarlar, en yeni sürümü veri/nesnesini alır ve disk önbelleğine alınan verileri depolamaz.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CBindStatusCallback::CBindStatusCallback](#cbindstatuscallback)|Oluşturucu.|  
|[CBindStatusCallback:: ~ CBindStatusCallback](#dtor)|Yıkıcı.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CBindStatusCallback::Download](#download)|Yükleme işlemi başlatan statik yöntemi oluşturur bir `CBindStatusCallback` nesne ve çağrıları `StartAsyncDownload`.|  
|[CBindStatusCallback::GetBindInfo](#getbindinfo)|Zaman uyumsuz ad isteği bilgilere oluşturulacak bağlama türü tarafından çağrılır.|  
|[CBindStatusCallback::GetPriority](#getpriority)|Bağlama işlemi önceliğini almak için zaman uyumsuz ad tarafından çağrılır. ATL uygulamasını döndürür `E_NOTIMPL`.|  
|[CBindStatusCallback::OnDataAvailable](#ondataavailable)|Uygun olduğunda, uygulamanızın verilerini sağlamak için çağrılır. Verileri okur ve verileri kullanmak için geçirilen işlevini çağırır.|  
|[CBindStatusCallback::OnLowResource](#onlowresource)|Kaynaklar yetersiz olduğunda çağrılır. ATL uygulamasını S_OK döndürür.|  
|[CBindStatusCallback::OnObjectAvailable](#onobjectavailable)|Bir nesne arabirim işaretçisi uygulamanızı geçirmek için zaman uyumsuz ad tarafından çağrılır. ATL uygulamasını S_OK döndürür.|  
|[CBindStatusCallback::OnProgress](#onprogress)|Bir veri indirme işlemindeki ilerlemeyi göstermek için çağrılır. ATL uygulamasını S_OK döndürür.|  
|[CBindStatusCallback::OnStartBinding](#onstartbinding)|Bağlama başlatıldığında çağrılır.|  
|[CBindStatusCallback::OnStopBinding](#onstopbinding)|Zaman uyumsuz veri aktarım bittiğinde çağırılır.|  
|[CBindStatusCallback::StartAsyncDownload](#startasyncdownload)|Kullanılabilir bayt başlatır ve okunan bayt sayısı sıfır olarak basma türüne bir akış nesnesi bir URL ve çağrıları oluşturur `OnDataAvailable` veriler her zaman.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CBindStatusCallback::m_dwAvailableToRead](#m_dwavailabletoread)|Okunacak kullanılabilir bayt sayısı.|  
|[CBindStatusCallback::m_dwTotalRead](#m_dwtotalread)|Okunan toplam bayt sayısı.|  
|[CBindStatusCallback::m_pFunc](#m_pfunc)|İşlev işaretçisi, veriler kullanılabilir olduğunda çağrılır.|  
|[CBindStatusCallback::m_pT](#m_pt)|Zaman uyumsuz veri aktarımı isteyen nesne işaretçisi.|  
|[CBindStatusCallback::m_spBindCtx](#m_spbindctx)|İşaretçi [ıbindctx i](http://msdn.microsoft.com/library/windows/desktop/ms693755) geçerli bağlama işlemi için arabirim.|  
|[CBindStatusCallback::m_spBinding](#m_spbinding)|İşaretçi `IBinding` geçerli bağlama işlemi için arabirim.|  
|[CBindStatusCallback::m_spMoniker](#m_spmoniker)|İşaretçi [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) kullanılacak URL için arabirim.|  
|[CBindStatusCallback::m_spStream](#m_spstream)|İşaretçi [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) veri aktarımı için arabirim.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CBindStatusCallback` Sınıfının Implements `IBindStatusCallback` arabirimi. `IBindStatusCallback` uygulamanız tarafından bir zaman uyumsuz veri aktarımı bildirim alabilir şekilde uygulanmalıdır. Sistem tarafından sağlanan zaman uyumsuz ad kullanan `IBindStatusCallback` göndermek ve zaman uyumsuz veri hakkında bilgi almak için yöntemleri aktarma nesnenizin gelen ve giden.  
  
 Genellikle, `CBindStatusCallback` nesne bir belirli bağlama işlemi ile ilişkili değil. Örneğin, [zaman UYUMSUZ](../../visual-cpp-samples.md) URL'si özelliğini ayarladığınızda bu örnek, oluşturur bir `CBindStatusCallback` nesne çağrısında `Download`:  
  
 [!code-cpp[NVC_ATL_Windowing#86](../../atl/codesnippet/cpp/cbindstatuscallback-class_1.h)]  
  
 Zaman uyumsuz ad geri çağırma işlevi kullanır `OnData` verilerinizde olduğunda, uygulamanızın çağırmak için. Sistem tarafından sağlanan zaman uyumsuz bir bilinen ad.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CComObjectRootBase`  
  
 `IBindStatusCallback`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `CBindStatusCallback`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlctl.h  
  
##  <a name="cbindstatuscallback"></a>  CBindStatusCallback::CBindStatusCallback  
 Oluşturucu.  
  
```
CBindStatusCallback();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Zaman uyumsuz veri aktarımı ile ilgili bildirim almak için bir nesne oluşturur. Genellikle, bir nesnenin her bağlama işlemi için oluşturulur.  
  
 Oluşturucu ayrıca başlatır [m_pT](#m_pt) ve [m_pFunc](#m_pfunc) null.  
  
##  <a name="dtor"></a>  CBindStatusCallback:: ~ CBindStatusCallback  
 Yıkıcı.  
  
```
~CBindStatusCallback();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrılan tüm kaynakları serbest bırakır.  
  
##  <a name="download"></a>  CBindStatusCallback::Download  
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
 *PT*  
 [in] Zaman uyumsuz veri aktarımı isteyen nesnesine bir işaretçi. `CBindStatusCallback` Nesne, bu nesnenin sınıfı üzerinde şablonlaştırılır.  
  
 *pFunc*  
 [in] Okunan verileri alan işlev işaretçisi. İşlev, nesnenin sınıf türünün bir üyesidir `T`. Bkz: [StartAsyncDownload](#startasyncdownload) söz dizimi ve için.  
  
 *bstrURL*  
 [in] Verileri almak için URL. Herhangi bir geçerli URL veya dosya adı olabilir. NULL olamaz. Örneğin:  
  
 `CComBSTR mybstr =_T("http://somesite/data.htm")`  
  
 *pUnkContainer*  
 [in] `IUnknown` Kapsayıcının. Varsayılan olarak null değerini DÖNDÜRÜR.  
  
 *bRelative*  
 [in] URL göreli veya mutlak olup olmadığını belirten bir bayrak. Mutlak URL anlamına gelir ve varsayılan olarak FALSE.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
### <a name="remarks"></a>Açıklamalar  
 Veriler her zaman nesnesi üzerinden gönderilir `OnDataAvailable`. `OnDataAvailable` verileri okur ve işaret ettiği işlevi çağıran *pFunc* (örneğin, verileri depolamak veya ekrana yazdırmak için).  
  
##  <a name="getbindinfo"></a>  CBindStatusCallback::GetBindInfo  
 Bilinen ad nasıl bağlanacağını bildirmek için çağırılır.  
  
```
STDMETHOD(GetBindInfo)(
    DWORD* pgrfBSCF,
    BINDINFO* pbindinfo);
```  
  
### <a name="parameters"></a>Parametreler  
 *pgrfBSCF*  
 [out] BINDF numaralandırma değerlerinin nasıl bağlama işlemi gerçekleşmesi gerektiğini gösteren bir işaretçi. Varsayılan olarak, aşağıdaki sabit listesi değerleri ayarlayın:  
  
 BINDF_ASYNCHRONOUS zaman uyumsuz indirme.  
  
 BINDF_ASYNCSTORAGE `OnDataAvailable` veri henüz veri kullanılabilir hale gelene kadar engelleme yerine kullanılabilir olmadığında E_PENDING döndürür.  
  
 BINDF_GETNEWESTVERSION bağlama işlemi, verileri en yeni sürümünü almanız gerekir.  
  
 Bağlama işlemi değil saklamalısınız BINDF_NOWRITECACHE disk önbellekteki veriler alınır.  
  
 *pbindinfo*  
 [out içinde] Bir işaretçi `BINDINFO` yapısı nasıl gerçekleşmesi için bağlama nesnesi istediği hakkında daha fazla bilgi verir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama, zaman uyumsuz ve veri gönderme modeli kullanmak için bağlama ayarlar. Veri gönderimi modelinde, ad, zaman uyumsuz bağlama işlemi sürücüleri ve yeni veriler kullanılabilir olduğunda istemci sürekli olarak bildirir.  
  
##  <a name="getpriority"></a>  CBindStatusCallback::GetPriority  
 Bağlama işlemi önceliğini almak için zaman uyumsuz ad tarafından çağrılır.  
  
```
STDMETHOD(GetPriority)(LONG* pnPriority);
```  
  
### <a name="parameters"></a>Parametreler  
 *pnPriority*  
 [out] Adresi **uzun** değişkeni, başarı, öncelik alır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 E_NOTIMPL döndürür.  
  
##  <a name="m_dwavailabletoread"></a>  CBindStatusCallback::m_dwAvailableToRead  
 Okunacak kullanılabilir bayt sayısı depolamak için kullanılabilir.  
  
```
DWORD m_dwAvailableToRead;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Sıfır başlatılmış `StartAsyncDownload`.  
  
##  <a name="m_dwtotalread"></a>  CBindStatusCallback::m_dwTotalRead  
 Toplam bayt sayısı zaman uyumsuz veri aktarımı okuyun.  
  
```
DWORD m_dwTotalRead;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Her zaman artan `OnDataAvailable` gerçekten okunan bayt sayısını tarafından çağrılır. Sıfır başlatılmış `StartAsyncDownload`.  
  
##  <a name="m_pfunc"></a>  CBindStatusCallback::m_pFunc  
 İşlevi tarafından işaret edilen `m_pFunc` tarafından çağrılır `OnDataAvailable` sonra (örneğin, verileri depolamak veya ekrana yazdırmak için) kullanılabilir verileri okur.  
  
```
ATL_PDATAAVAILABLE m_pFunc;
```  
  
### <a name="remarks"></a>Açıklamalar  
 İşlevi tarafından işaret edilen `m_pFunc` nesnenizin sınıf üyesidir ve sözdizimi aşağıdaki gibidir:  
  
```  
void Function_Name(  
   CBindStatusCallback<T>* pbsc,  
   BYTE* pBytes,  
   DWORD dwSize  
   );  
```  
  
##  <a name="m_pt"></a>  CBindStatusCallback::m_pT  
 Zaman uyumsuz veri aktarımı isteyen nesnesine bir işaretçi.  
  
```
T* m_pT;
```  
  
### <a name="remarks"></a>Açıklamalar  
 `CBindStatusCallback` Nesne, bu nesnenin sınıfı üzerinde şablonlaştırılır.  
  
##  <a name="m_spbindctx"></a>  CBindStatusCallback::m_spBindCtx  
 Bir işaretçi bir [ıbindctx i](http://msdn.microsoft.com/library/windows/desktop/ms693755) bağlama bağlamı (belirli bir bilinen ad bağlama işlemiyle ilgili bilgileri depolayan bir nesne) erişim sağlayan bir arabirimi.  
  
```
CComPtr<IBindCtx> m_spBindCtx;
```  
  
### <a name="remarks"></a>Açıklamalar  
 İçinde başlatılan `StartAsyncDownload`.  
  
##  <a name="m_spbinding"></a>  CBindStatusCallback::m_spBinding  
 Bir işaretçi `IBinding` arabiriminin geçerli bağlama işlemi.  
  
```
CComPtr<IBinding> m_spBinding;
```  
  
### <a name="remarks"></a>Açıklamalar  
 İçinde başlatılan `OnStartBinding` ve yayımlanan `OnStopBinding`.  
  
##  <a name="m_spmoniker"></a>  CBindStatusCallback::m_spMoniker  
 Bir işaretçi [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) kullanılacak URL için arabirim.  
  
```
CComPtr<IMoniker> m_spMoniker;
```  
  
### <a name="remarks"></a>Açıklamalar  
 İçinde başlatılan `StartAsyncDownload`.  
  
##  <a name="m_spstream"></a>  CBindStatusCallback::m_spStream  
 Bir işaretçi [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) arabiriminin geçerli bağlama işlemi.  
  
```
CComPtr<IStream> m_spStream;
```  
  
### <a name="remarks"></a>Açıklamalar  
 İçinde başlatılan `OnDataAvailable` gelen `STGMEDIUM` yapısı BCSF bayrağı BCSF_FIRSTDATANOTIFICATION ve BCSF bayrağı BCSF_LASTDATANOTIFICATION olduğunda serbest olduğunda.  
  
##  <a name="ondataavailable"></a>  CBindStatusCallback::OnDataAvailable  
 Sistem tarafından sağlanan zaman uyumsuz ad aramaları `OnDataAvailable` kullanılabilir olduğunda, nesne verilerini sağlamak için.  
  
```
STDMETHOD(  
    OnDataAvailable)(DWORD grfBSCF,
    DWORD dwSize,
    FORMATETC* /* pformatetc */,
    STGMEDIUM* pstgmed);
```  
  
### <a name="parameters"></a>Parametreler  
 *grfBSCF*  
 [in] BSCF numaralandırma değeri. Bir veya daha fazlasını: BSCF_FIRSTDATANOTIFICATION, BSCF_INTERMEDIARYDATANOTIFICATION veya BSCF_LASTDATANOTIFICATION.  
  
 *dwSize*  
 [in] Veri bağlama başlangıcından itibaren kullanılabilir toplam miktarı (bayt cinsinden). Veri miktarı ilgili değilse veya hiçbir belirli bir miktarın mevcut geldiğini gösteren sıfır olabilir.  
  
 *pformatetc*  
 [in] İşaretçi [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682242) kullanılabilir verilerin biçimini içeren yapısı. Biçim verilmedi CF_NULL olabilir.  
  
 *pstgmed*  
 [in] İşaretçi [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms695269) sunuldu gerçek verileri tutan yapı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
### <a name="remarks"></a>Açıklamalar  
 `OnDataAvailable` verileri okur ve ardından (örneğin, verileri depolamak veya ekrana yazdırmak için) nesnenizin sınıfının bir yöntemi çağırır. Bkz: [CBindStatusCallback::StartAsyncDownload](#startasyncdownload) Ayrıntılar için.  
  
##  <a name="onlowresource"></a>  CBindStatusCallback::OnLowResource  
 Kaynaklar yetersiz olduğunda çağrılır.  
  
```
STDMETHOD(OnLowResource)(DWORD /* dwReserved */);
```  
  
### <a name="parameters"></a>Parametreler  
 *dwReserved*  
 Ayrılmış.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK döndürür.  
  
##  <a name="onobjectavailable"></a>  CBindStatusCallback::OnObjectAvailable  
 Bir nesne arabirim işaretçisi uygulamanızı geçirmek için zaman uyumsuz ad tarafından çağrılır.  
  
```
STDMETHOD(OnObjectAvailable)(REFID /* riid */, IUnknown* /* punk */);
```  
  
### <a name="parameters"></a>Parametreler  
 *riid*  
 İstenen arabirim arabirimi tanımlayıcısı. Kullanılmayan.  
  
 *Punk*  
 IUnknown arabirimi adresi. Kullanılmayan.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK döndürür.  
  
##  <a name="onprogress"></a>  CBindStatusCallback::OnProgress  
 Bir veri indirme işlemindeki ilerlemeyi göstermek için çağrılır.  
  
```
STDMETHOD(OnProgress)(
    ULONG /* ulProgress */,
    ULONG /* ulProgressMax */,
    ULONG /* ulStatusCode */,
    LPCWSTRONG /* szStatusText */);
```  
  
### <a name="parameters"></a>Parametreler  
 *ulProgress*  
 İşaretsiz uzun tamsayı. Kullanılmayan.  
  
 *ulProgressMax*  
 İşaretsiz uzun tamsayı kullanılmayan.  
  
 *ulStatusCode*  
 İşaretsiz uzun tamsayı. Kullanılmayan.  
  
 *szStatusText*  
 Bir dize değeri adresi. Kullanılmayan.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK döndürür.  
  
##  <a name="onstartbinding"></a>  CBindStatusCallback::OnStartBinding  
 Veri üyesi ayarlar [m_spBinding](#m_spbinding) için `IBinding` işaretçiyi *pBinding*.  
  
```
STDMETHOD(OnStartBinding)(DWORD /* dwReserved */, IBinding* pBinding);
```  
  
### <a name="parameters"></a>Parametreler  
 *dwReserved*  
 Daha sonraki kullanımlar için ayrılmıştır.  
  
 *pBinding*  
 [in] Geçerli IBinding arabiriminin adresini bağlama işlemi. Bu, NULL olamaz. İstemci, bağlama nesnesine bir başvuru tutmak için bu işaretçi üzerinde AddRef çağırmalıdır.  
  
##  <a name="onstopbinding"></a>  CBindStatusCallback::OnStopBinding  
 Yayınları `IBinding` veri üyesi işaretçiyi [m_spBinding](#m_spbinding).  
  
```
STDMETHOD(OnStopBinding)(HRESULT hresult, LPCWSTR /* szError */);
```  
  
### <a name="parameters"></a>Parametreler  
 *HRESULT*  
 Bağlama işlemi durum kodunu döndürdü.  
  
 szStatusText  
 Bir dize değeri kullanılmayan adresi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bağlama işleminin sonunu belirtmek için sistem tarafından sağlanan zaman uyumsuz ad tarafından çağrılır.  
  
##  <a name="startasyncdownload"></a>  CBindStatusCallback::StartAsyncDownload  
 Verileri zaman uyumsuz olarak belirtilen URL'den indirilmeye başlar.  
  
```
HRESULT StartAsyncDownload(  
    T* pT,
    ATL_PDATAAVAILABLE pFunc,
    BSTR bstrURL,
    IUnknown* pUnkContainer = NULL,
    BOOL bRelative = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 *PT*  
 [in] Zaman uyumsuz veri aktarımı isteyen nesnesine bir işaretçi. `CBindStatusCallback` Nesne, bu nesnenin sınıfı üzerinde şablonlaştırılır.  
  
 *pFunc*  
 [in] Okunan verilerin alan işlev işaretçisi. İşlev, nesnenin sınıf türünün bir üyesidir `T`. Bkz: **açıklamalar** söz dizimi ve için.  
  
 *bstrURL*  
 [in] Verileri almak için URL. Herhangi bir geçerli URL veya dosya adı olabilir. NULL olamaz. Örneğin:  
  
 `CComBSTR mybstr =_T("http://somesite/data.htm")`  
  
 *pUnkContainer*  
 [in] `IUnknown` Kapsayıcının. Varsayılan olarak null değerini DÖNDÜRÜR.  
  
 *bRelative*  
 [in] URL göreli veya mutlak olup olmadığını belirten bir bayrak. Mutlak URL anlamına gelir ve varsayılan olarak FALSE.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
### <a name="remarks"></a>Açıklamalar  
 Veriler her zaman nesnesi üzerinden gönderilir `OnDataAvailable`. `OnDataAvailable` verileri okur ve işaret ettiği işlevi çağıran *pFunc* (örneğin, verileri depolamak veya ekrana yazdırmak için).  
  
 İşlevi tarafından işaret edilen *pFunc* nesnenizin sınıf üyesidir ve sözdizimi aşağıdaki gibidir:  
  
 `void Function_Name(`  
  
 `CBindStatusCallback<T>*` `pbsc` `,`  
  
 `BYTE*` `pBytes` `,`  
  
 `DWORD``dwSize`  
  
 `);`  
  
 Aşağıdaki örnekte (alınan [zaman UYUMSUZ](../../visual-cpp-samples.md) örnek), işlev `OnData` bir metin kutusu alınan verileri yazar.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#87](../../atl/codesnippet/cpp/cbindstatuscallback-class_2.h)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)
