---
title: CAsyncMonikerFile sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAsyncMonikerFile
- AFXOLE/CAsyncMonikerFile
- AFXOLE/CAsyncMonikerFile::CAsyncMonikerFile
- AFXOLE/CAsyncMonikerFile::Close
- AFXOLE/CAsyncMonikerFile::GetBinding
- AFXOLE/CAsyncMonikerFile::GetFormatEtc
- AFXOLE/CAsyncMonikerFile::Open
- AFXOLE/CAsyncMonikerFile::CreateBindStatusCallback
- AFXOLE/CAsyncMonikerFile::GetBindInfo
- AFXOLE/CAsyncMonikerFile::GetPriority
- AFXOLE/CAsyncMonikerFile::OnDataAvailable
- AFXOLE/CAsyncMonikerFile::OnLowResource
- AFXOLE/CAsyncMonikerFile::OnProgress
- AFXOLE/CAsyncMonikerFile::OnStartBinding
- AFXOLE/CAsyncMonikerFile::OnStopBinding
dev_langs:
- C++
helpviewer_keywords:
- CAsyncMonikerFile [MFC], CAsyncMonikerFile
- CAsyncMonikerFile [MFC], Close
- CAsyncMonikerFile [MFC], GetBinding
- CAsyncMonikerFile [MFC], GetFormatEtc
- CAsyncMonikerFile [MFC], Open
- CAsyncMonikerFile [MFC], CreateBindStatusCallback
- CAsyncMonikerFile [MFC], GetBindInfo
- CAsyncMonikerFile [MFC], GetPriority
- CAsyncMonikerFile [MFC], OnDataAvailable
- CAsyncMonikerFile [MFC], OnLowResource
- CAsyncMonikerFile [MFC], OnProgress
- CAsyncMonikerFile [MFC], OnStartBinding
- CAsyncMonikerFile [MFC], OnStopBinding
ms.assetid: 17378b66-a49a-4b67-88e3-7756ad26a2fc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 16d4b5169ffa93892b8a3076cbfa24227ccf569f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33356024"
---
# <a name="casyncmonikerfile-class"></a>CAsyncMonikerFile sınıfı
ActiveX denetimlerinde zaman uyumsuz adlar kullanmak için işlevsellik sağlar (önceki adıyla OLE denetimleri).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CAsyncMonikerFile : public CMonikerFile  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAsyncMonikerFile::CAsyncMonikerFile](#casyncmonikerfile)|Oluşturan bir `CAsyncMonikerFile` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAsyncMonikerFile::Close](#close)|Kapatır ve tüm kaynakları serbest bırakır.|  
|[CAsyncMonikerFile::GetBinding](#getbinding)|Zaman uyumsuz aktarım bağlama için bir işaretçi alır.|  
|[CAsyncMonikerFile::GetFormatEtc](#getformatetc)|Akıştaki verilerin biçimini alır.|  
|[CAsyncMonikerFile::Open](#open)|Zaman uyumsuz olarak bir dosyayı açar.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAsyncMonikerFile::CreateBindStatusCallback](#createbindstatuscallback)|Arabirimini uygulayan bir COM nesnesi oluşturur `IBindStatusCallback`.|  
|[CAsyncMonikerFile::GetBindInfo](#getbindinfo)|Oluşturulacak Bağ türü isteği bilgilere OLE sistem kitaplığı tarafından çağrılır.|  
|[CAsyncMonikerFile::GetPriority](#getpriority)|Bağlama önceliğini almak için OLE sistem kitaplığı tarafından çağrılır.|  
|[CAsyncMonikerFile::OnDataAvailable](#ondataavailable)|Zaman uyumsuz bağlama işlemleri sırasında istemciye uygun olduğunda veri sağlamak için çağrılır.|  
|[CAsyncMonikerFile::OnLowResource](#onlowresource)|Kaynakları düşük olduğunda çağrılır.|  
|[CAsyncMonikerFile::OnProgress](#onprogress)|Yükleme işlemi veri ilerlemeyi göstermek için çağrılır.|  
|[CAsyncMonikerFile::OnStartBinding](#onstartbinding)|Bağlama başlatma sırasında çağrılır.|  
|[CAsyncMonikerFile::OnStopBinding](#onstopbinding)|Zaman uyumsuz aktarım durdurulduğunda çağrılır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Türetilen [CMonikerFile](../../mfc/reference/cmonikerfile-class.md), sırayla türetilen [COleStreamFile](../../mfc/reference/colestreamfile-class.md), `CAsyncMonikerFile` kullanan [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) hiçbir veri akışı erişmek için arabirimi zaman uyumsuz olarak dosyaları zaman uyumsuz olarak bir URL'den yükleme dahil olmak üzere. Dosyalar ActiveX denetimlerinin datapath özelliklerini olabilir.  
  
 Zaman uyumsuz adlar, öncelikle Internet özellikli uygulamalar ve ActiveX denetimleri, dosya aktarımı sırasında bir yanıt kullanıcı arabirimi sağlamak için kullanılır. Bu prime örneği kullanımıdır [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md) ActiveX denetimleri için zaman uyumsuz özellikler sağlamak için. `CDataPathProperty` Nesnesini art arda uzun özelliği exchange işlemi sırasında yeni verilerin kullanılabilirliğini belirtmek için bir geri alın.  
  
 Zaman uyumsuz adlar ve ActiveX denetimlerini Internet uygulamalarında kullanma hakkında daha fazla bilgi için aşağıdaki makalelere bakın:  
  
- [Internet ilk adımlar: Zaman uyumsuz adlar](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
- [Internet ilk adımlar: ActiveX denetimleri](../../mfc/activex-controls-on-the-internet.md)  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 [CMonikerFile](../../mfc/reference/cmonikerfile-class.md)  
  
 `CAsyncMonikerFile`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxole.h  
  
##  <a name="casyncmonikerfile"></a>  CAsyncMonikerFile::CAsyncMonikerFile  
 Oluşturan bir `CAsyncMonikerFile` nesnesi.  
  
```  
CAsyncMonikerFile();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturma `IBindHost` arabirimi. `IBindHost` içinde yalnızca sağlarsanız, kullanılan **açık** üye işlevi.  
  
 Bir açıklaması için `IBindHost` arabirimi, Windows SDK konusuna bakın.  
  
##  <a name="close"></a>  CAsyncMonikerFile::Close  
 Kapatmak ve tüm kaynakları serbest bırakmak için bu işlevini çağırın.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Açılmamış ya da zaten kapalı dosyalar üzerinde çağrılabilir.  
  
##  <a name="createbindstatuscallback"></a>  CAsyncMonikerFile::CreateBindStatusCallback  
 Arabirimini uygulayan bir COM nesnesi oluşturur `IBindStatusCallback`.  
  
```  
virtual IUnknown* CreateBindStatusCallback(IUnknown* pUnkControlling);
```  
  
### <a name="parameters"></a>Parametreler  
 `pUnkControlling`  
 Denetleme bilinmeyen işaretçisine (dış **IUnknown**) veya **NULL** toplama olmayan kullanılıyorsa.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsa `pUnkControlling` değil **NULL**, işlevi için iç işaretçi döndüren **IUnknown** yeni bir COM nesnesi destekleme üzerinde `IBindStatusCallback`. Varsa `pUnkControlling` olan **NULL**, işlevi için bir işaretçi döndürür bir **IUnknown** yeni bir COM nesnesi destekleme üzerinde `IBindStatusCallback`.  
  
### <a name="remarks"></a>Açıklamalar  
 `CAsyncMonikerFile` arabirimini uygulayan bir COM nesnesi gerektirir `IBindStatusCallback`. Böyle bir nesnenin MFC uygular ve toplanabilir. Geçersiz kılabilirsiniz `CreateBindStatusCallback` kendi COM nesnesi dönün. COM nesnesi çağırarak MFC'nin uygulama toplayabilirsiniz `CreateBindStatusCallback` denetleme bilinmeyen COM nesnesi ile. COM nesneleri kullanılarak uygulanan `CCmdTarget` COM desteği denetleme bilinmeyen kullanarak alabilir **CCmdTarget::GetControllingUnknown**.  
  
 Alternatif olarak, COM nesnesi MFC'nin uygulamasına çağırarak temsilci seçebilirsiniz **CreateBindStatusCallback (boş)**.  
  
 [CAsyncMonikerFile::Open](#open) çağrıları `CreateBindStatusCallback`.  
  
 Zaman uyumsuz adlar ve zaman uyumsuz bağlama hakkında daha fazla bilgi için bkz: [IBindStatusCallback](http://msdn.microsoft.com/library/ie/ms775060) arabirimi ve [ne zaman uyumsuz bağlama ve depolama iş](http://msdn.microsoft.com/library/windows/desktop/aa379152). Bir toplama tartışma için bkz: [toplama](http://msdn.microsoft.com/library/windows/desktop/ms686558). Tüm üç Windows SDK'ın konulardır.  
  
##  <a name="getbindinfo"></a>  CAsyncMonikerFile::GetBindInfo  
 Zaman uyumsuz ad nasıl bağlanacağını istediği bildirmek için istemciden zaman uyumsuz bir bilinen ad olarak çağrılır.  
  
```  
virtual DWORD GetBindInfo() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ayarlarını alır **IBindStatusCallBack**. Bir açıklaması için `IBindStatusCallback` arabirimi, Windows SDK konusuna bakın.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama bağlama zaman uyumsuz, bir depolama ortamına (akış) kullanın ve veri gönderme modeli kullanmak için olacak şekilde ayarlar. Bağlama davranışı değiştirmek istiyorsanız, bu işlev geçersiz kılar.  
  
 Bunu yapmak için bir sebep veri çekme modeli yerine veri gönderme modeli kullanarak bağlamak için olacaktır. Bir veri çekme modeli bağlama işlemi istemci sürücüleri ve onu okunduğunda ad veri istemciye yalnızca sağlar. Bir veri gönderimi modeldeki ad zaman uyumsuz bağlama işlemi sürücüler ve yeni veriler kullanılabilir olduğunda istemci sürekli olarak bildirir.  
  
##  <a name="getbinding"></a>  CAsyncMonikerFile::GetBinding  
 Zaman uyumsuz aktarım bağlama için bir işaretçi almak için bu işlevini çağırın.  
  
```  
IBinding* GetBinding() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi `IBinding` zaman uyumsuz aktarım başladığında sağlanan arabirim. Döndürür **NULL** herhangi bir nedenle aktarımı zaman uyumsuz olarak gerçekleştirilemezse.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu, veri aktarım işlemi aracılığıyla denetlemenize olanak tanır `IBinding` , ile örnek için arabirim **IBinding::Abort**, **IBinding::Pause**, ve **IBinding::Resume**.  
  
 Bir açıklaması için `IBinding` arabirimi, Windows SDK konusuna bakın.  
  
##  <a name="getformatetc"></a>  CAsyncMonikerFile::GetFormatEtc  
 Akıştaki verilerin biçimi almak için bu işlevini çağırın.  
  
```  
FORMATETC* GetFormatEtc() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Windows yapısına yönelik işaretçinin [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) açılmış akış için. Döndürür **NULL** zaman uyumsuz değilse, ad, bağlı değil veya zaman uyumsuz işlemi başlatılmamıştır.  
  
##  <a name="getpriority"></a>  CAsyncMonikerFile::GetPriority  
 Zaman uyumsuz bir bilinen ad istemcisinden çağrılan iş parçacığına bağlama işlemi için verilen önceliği almak bağlama işlemi başlatılırken.  
  
```  
virtual LONG GetPriority() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Zaman uyumsuz aktarım yer alacak önceliği. Standart iş parçacığı önceliği bayrakları birini: **THREAD_PRIORITY_ABOVE_NORMAL**, **THREAD_PRIORITY_BELOW_NORMAL**, **THREAD_PRIORITY_HIGHEST**,  **THREAD_PRIORITY_IDLE**, **THREAD_PRIORITY_LOWEST**, **THREAD_PRIORITY_NORMAL**, ve **THREAD_PRIORITY_TIME_CRITICAL**. Windows işlevi görmek [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) bu değerleri açıklaması.  
  
### <a name="remarks"></a>Açıklamalar  
 `GetPriority` doğrudan çağrılmamalıdır. **THREAD_PRIORITY_NORMAL** varsayılan uygulama tarafından döndürülür.  
  
##  <a name="ondataavailable"></a>  CAsyncMonikerFile::OnDataAvailable  
 Zaman uyumsuz bir bilinen ad çağırır `OnDataAvailable` kullanılabilir hale geldiğinde istemciye veri sağlamak için sırasında zaman uyumsuz işlemleri bağlayın.  
  
```  
virtual void OnDataAvailable(DWORD dwSize, DWORD bscfFlag);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwSize`  
 Toplu miktarı (bayt cinsinden) veri bağlama başına itibaren kullanılabilir. Veri miktarını işlemi için uygun değilse veya belirli bir miktar kullanılabilen gösteren sıfır olabilir.  
  
 *bscfFlag*  
 A **BSCF** numaralandırma değeri. Bir veya daha fazla aşağıdaki değerlerden biri olabilir:  
  
- **BSCF_FIRSTDATANOTIFICATION** ilk çağrıda tanımlayan `OnDataAvailable` verilen bağlama işlemi için.  
  
- **BSCF_INTERMEDIATEDATANOTIFICATION** Ara çağrısına tanımlayan `OnDataAvailable` bağlama işlemi için.  
  
- **BSCF_LASTDATANOTIFICATION** yapılan son çağrı tanımlayan `OnDataAvailable` bağlama işlemi için.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev varsayılan uygulaması hiçbir şey yapmaz. Örnek uygulama için aşağıdaki örneğe bakın.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWinInet#5](../../mfc/codesnippet/cpp/casyncmonikerfile-class_1.cpp)]  
  
##  <a name="onlowresource"></a>  CAsyncMonikerFile::OnLowResource  
 Kaynakları düşük olduğunda ad tarafından çağrılır.  
  
```  
virtual void OnLowResource();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan Uygulama çağrıları `GetBinding( )-> Abort( )`.  
  
##  <a name="onprogress"></a>  CAsyncMonikerFile::OnProgress  
 Art arda genellikle aralıklarla makul uzun bir işlem sırasında bu bağlama işleminin geçerli ilerlemeyi göstermek için ad tarafından çağrılır.  
  
```  
virtual void OnProgress(
    ULONG ulProgress,  
    ULONG ulProgressMax,  
    ULONG ulStatusCode,  
    LPCTSTR szStatusText);
```  
  
### <a name="parameters"></a>Parametreler  
 `ulProgress`  
 Bağlama işlemi belirtilen beklenen maksimum göre geçerli ilerlemesini gösterir `ulProgressMax`.  
  
 `ulProgressMax`  
 Beklenen maksimum değeri belirten `ulProgress` çağrıları süresince `OnProgress` bu işlem için.  
  
 `ulStatusCode`  
 Bağlama işleminin ilerleme durumu ile ilgili ek bilgiler sağlar. Geçerli değerler gerçekleştirilecek `BINDSTATUS` numaralandırması. Uyarılar için olası değerler başvurun.  
  
 `szStatusText`  
 Değerine bağlı olarak geçerli ilerleme durumu hakkında bilgi `ulStatusCode`. Uyarılar için olası değerler başvurun.  
  
### <a name="remarks"></a>Açıklamalar  
 Olası değerler için `ulStatusCode` (ve `szStatusText` her bir değer için) şunlardır:  
  
 **BINDSTATUS_FINDINGRESOURCE**  
 Bağlama işlemi nesne ya da bağlanan depolama tutan kaynak bulma. `szStatusText` Aranmakta kaynak görünen adını sağlar (örneğin, "www.microsoft.com") için.  
  
 **BINDSTATUS_CONNECTING**  
 Bağlama işlemi nesne ya da bağlanan depolama tutan kaynağına bağlanıyor. `szStatusText` (Örneğin, bir IP adresi) bağlı kaynak görünen adı sağlar.  
  
 **BINDSTATUS_SENDINGREQUEST**  
 Bağlama işlemi nesne veya bağlanan depolama istiyor. `szStatusText` (Örneğin, bir dosya adı) nesnenin görünen adını sağlar.  
  
 **BINDSTATUS_REDIRECTING**  
 Bağlama işlemi farklı veri konumuna yönlendirildi. `szStatusText` Yeni veri konumu görünen adını sağlar.  
  
 **BINDSTATUS_USINGCACHEDCOPY**  
 Bağlama işlemi, istenen nesne veya depolama önbelleğe alınmış bir kopyasından alıyor. `szStatusText` Olan **NULL**.  
  
 **BINDSTATUS_BEGINDOWNLOADDATA**  
 Nesne veya bağlanan depolama alma bağlama işlemi başladı. `szStatusText` Veri konumu görünen adını sağlar.  
  
 **BINDSTATUS_DOWNLOADINGDATA**  
 Bağlama işlemi nesne veya bağlanan depolama almaya devam eder. `szStatusText` Veri konumu görünen adını sağlar.  
  
 **BINDSTATUS_ENDDOWNLOADDATA**  
 Nesne veya bağlanan depolama alma bağlama işlemi tamamlandı. `szStatusText` Veri konumu görünen adını sağlar.  
  
 **BINDSTATUS_CLASSIDAVAILABLE**  
 Bağlanan nesne neredeyse oluşturulacak örneğidir. `szStatusText` Bağlama işlemini iptal etmek bir fırsat isterseniz izin vermeden CLSID yeni nesnenin dize biçimindeki sağlar.  
  
##  <a name="onstartbinding"></a>  CAsyncMonikerFile::OnStartBinding  
 Bu işlev bağlama başlatma sırasında eylemleri gerçekleştirmek için türetilmiş sınıflarda geçersiz kılar.  
  
```  
virtual void OnStartBinding();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev geri ad tarafından çağrılır. Varsayılan uygulama hiçbir şey yapmaz.  
  
##  <a name="onstopbinding"></a>  CAsyncMonikerFile::OnStopBinding  
 Bağlama işlemi sonunda ad tarafından çağrılır.  
  
```  
virtual void OnStopBinding(HRESULT hresult, LPCTSTR szError);
```  
  
### <a name="parameters"></a>Parametreler  
 `hresult`  
 Bir `HRESULT` diğer bir deyişle hata veya uyarı değeri.  
  
 *szErrort*  
 Hatayı açıklayan bir karakter dizesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Aktarım durdurulduğunda eylemleri gerçekleştirmek için bu işlevi geçersiz kılar. Varsayılan olarak, işlevi serbest `IBinding`.  
  
 Bir açıklaması için `IBinding` arabirimi, Windows SDK konusuna bakın.  
  
##  <a name="open"></a>  CAsyncMonikerFile::Open  
 Zaman uyumsuz olarak bir dosyayı açmak için bu üye işlevini çağırın.  
  
```  
virtual BOOL Open(
    LPCTSTR lpszURL,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    IMoniker* pMoniker,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    LPCTSTR lpszURL,
    IBindHost* pBindHost,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    IMoniker* pMoniker,
    IBindHost* pBindHost,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    LPCTSTR lpszURL,
    IServiceProvider* pServiceProvider,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    IMoniker* pMoniker,
    IServiceProvider* pServiceProvider,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    LPCTSTR lpszURL,
    IUnknown* pUnknown,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    IMoniker* pMoniker,
    IUnknown* pUnknown,
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszURL`  
 Zaman uyumsuz olarak açılması için dosyayı gösteren bir işaretçi. Dosya geçerli bir URL ya da dosya olabilir.  
  
 `pError`  
 Dosya özel durumları için bir işaretçi. Bir hata durumunda neden ayarlanır.  
  
 `pMoniker`  
 Zaman uyumsuz ad arayüzü için bir işaretçi `IMoniker`, ile alabilir belgenin kendi ad birleşimidir kesin bir bilinen ad **IOleClientSite::GetMoniker (** *OLEWHICHMK_ KAPSAYICI* **)** ve yol adından oluşturulan bir ad. Denetim bağlamak için bu ad kullanabilirsiniz, ancak bu denetim kaydetmelisiniz ad değil.  
  
 *pBindHost*  
 Bir işaretçi `IBindHost` ad olası göreli bir yol adı oluşturmak için kullanılan arabirim. Bağ konak geçersiz veya bir bilinen ad sağlamaz, arama varsayılan olarak **açık (** `lpszFileName` **,**`pError`**)**. Bir açıklaması için `IBindHost` arabirimi, Windows SDK konusuna bakın.  
  
 `pServiceProvider`  
 Bir işaretçi `IServiceProvider` arabirimi. Hizmet sağlayıcısı geçersiz veya servis sağlamak başarısız olursa `IBindHost`, çağrı varsayılanları **açık (** `lpszFileName` **,**`pError`**)**.  
  
 *pUnknown*  
 Bir işaretçi **IUnknown** arabirimi. Varsa `IServiceProvider` bulunursa, işlevi sorgularında `IBindHost`. Hizmet sağlayıcısı geçersiz veya servis sağlamak başarısız olursa `IBindHost`, çağrı varsayılanları **açık (** `lpszFileName` **,**`pError`**)**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dosya başarılı bir şekilde açılırsa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu çağrı bağlama işlemi başlatır.  
  
 Bir URL veya bir dosya adı için kullanabileceğiniz `lpszURL` parametresi. Örneğin:  
  
 [!code-cpp[NVC_MFCWinInet#6](../../mfc/codesnippet/cpp/casyncmonikerfile-class_2.cpp)]  
  
 - veya -  
  
 [!code-cpp[NVC_MFCWinInet#7](../../mfc/codesnippet/cpp/casyncmonikerfile-class_3.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CMonikerFile sınıfı](../../mfc/reference/cmonikerfile-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CMonikerFile sınıfı](../../mfc/reference/cmonikerfile-class.md)   
 [CDataPathProperty Sınıfı](../../mfc/reference/cdatapathproperty-class.md)
