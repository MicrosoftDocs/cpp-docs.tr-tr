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
ms.openlocfilehash: 31d16279b4de6c0cca0d37161a37ce5e39b85b7b
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37339364"
---
# <a name="casyncmonikerfile-class"></a>CAsyncMonikerFile sınıfı
ActiveX denetimlerinde zaman uyumsuz adların kullanılması için işlevsellik sağlar (eski adı OLE denetimleri).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CAsyncMonikerFile : public CMonikerFile  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAsyncMonikerFile::CAsyncMonikerFile](#casyncmonikerfile)|Oluşturur bir `CAsyncMonikerFile` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAsyncMonikerFile::Close](#close)|Kapatır ve tüm kaynakları serbest bırakır.|  
|[CAsyncMonikerFile::GetBinding](#getbinding)|Zaman uyumsuz aktarımı bağlama bir işaretçi alır.|  
|[CAsyncMonikerFile::GetFormatEtc](#getformatetc)|Akıştaki verilerin biçimini alır.|  
|[CAsyncMonikerFile::Open](#open)|Zaman uyumsuz olarak bir dosya açar.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAsyncMonikerFile::CreateBindStatusCallback](#createbindstatuscallback)|Uygulayan bir COM nesnesi oluşturur `IBindStatusCallback`.|  
|[CAsyncMonikerFile::GetBindInfo](#getbindinfo)|OLE sistem kitaplığı için bilgi oluşturulacak bağlama türünü tarafından çağrılır.|  
|[CAsyncMonikerFile::GetPriority](#getpriority)|Bağlama önceliğini almak için OLE sistem kitaplığı tarafından çağrılır.|  
|[CAsyncMonikerFile::OnDataAvailable](#ondataavailable)|Zaman uyumsuz bağlama işlemleri sırasında istemciye uygun olduğunda veri sağlamak için çağrılır.|  
|[CAsyncMonikerFile::OnLowResource](#onlowresource)|Kaynaklar yetersiz olduğunda çağrılır.|  
|[CAsyncMonikerFile::OnProgress](#onprogress)|Veri indirme işlemindeki ilerlemeyi belirtmek için çağrılır.|  
|[CAsyncMonikerFile::OnStartBinding](#onstartbinding)|Bağlama başlandığında çağırılır.|  
|[CAsyncMonikerFile::OnStopBinding](#onstopbinding)|Zaman uyumsuz aktarım bittiğinde çağırılır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Öğesinden türetilen [CMonikerFile](../../mfc/reference/cmonikerfile-class.md), hangi sırayla türetilmiş olan [COleStreamFile](../../mfc/reference/colestreamfile-class.md), `CAsyncMonikerFile` kullanan [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) herhangi bir veri akışına erişmek için arabirimi zaman uyumsuz olarak dosyalarını bir URL'den zaman uyumsuz olarak yükleme dahil olmak üzere. Dosyaları datapath ActiveX denetimlerinin özelliklerini olabilir.  
  
 Zaman uyumsuz adlar, öncelikle Internet özellikli uygulamalar ve ActiveX denetimleri, hızlı yanıt veren bir kullanıcı arabirimi dosya aktarımlarında sağlamak için kullanılır. Bu prime örneği kullanımıdır [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md) ActiveX denetimleri için zaman uyumsuz özellikler sağlamak için. `CDataPathProperty` Nesnesi tekrar tekrar uzun özelliği değişimi sırasında yeni verilerin kullanılabilirliğini belirtmek için bir geri alma.  
  
 Zaman uyumsuz adlar ve ActiveX denetimleri, Internet uygulamalarında kullanma hakkında daha fazla bilgi için aşağıdaki makalelere bakın:  
  
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
 Oluşturur bir `CAsyncMonikerFile` nesne.  
  
```  
CAsyncMonikerFile();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturma `IBindHost` arabirimi. `IBindHost` içinde yalnızca sağlarsanız, kullanılan `Open` üye işlevi.  
  
 Bir açıklaması için `IBindHost` arabirimi, Windows SDK'sı bakın.  
  
##  <a name="close"></a>  CAsyncMonikerFile::Close  
 Kapat ve tüm kaynakları serbest bırakmak için bu işlevi çağırın.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Açılmamış veya zaten kapalı dosyaları çağrılabilir.  
  
##  <a name="createbindstatuscallback"></a>  CAsyncMonikerFile::CreateBindStatusCallback  
 Uygulayan bir COM nesnesi oluşturur `IBindStatusCallback`.  
  
```  
virtual IUnknown* CreateBindStatusCallback(IUnknown* pUnkControlling);
```  
  
### <a name="parameters"></a>Parametreler  
 *pUnkControlling*  
 Kontrol eden bilinmeyen bir işaretçi (dış `IUnknown`) veya toplama kullanılmadığı yoksa NULL.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsa *pUnkControlling* NULL değil işlevi iç işaretçi döndüren `IUnknown` yeni bir COM nesnesi destekleme üzerinde `IBindStatusCallback`. Varsa `pUnkControlling` null, işlev için bir işaretçi döndürür bir `IUnknown` yeni bir COM nesnesi destekleme üzerinde `IBindStatusCallback`.  
  
### <a name="remarks"></a>Açıklamalar  
 `CAsyncMonikerFile` uygulayan bir COM nesnesi gerektirir `IBindStatusCallback`. Böyle bir nesnenin MFC uygular ve toplanabilir. Geçersiz kılabilirsiniz `CreateBindStatusCallback` kendi COM nesnesi döndürmek için. COM nesnesi çağırarak denetlediği MFC'nin toplayabilirsiniz `CreateBindStatusCallback` kontrol eden bilinmeyen COM Nesne ile. COM nesneleri kullanılarak uygulanan `CCmdTarget` COM desteği kontrol eden bilinmeyen kullanarak alabilir `CCmdTarget::GetControllingUnknown`.  
  
 Alternatif olarak, COM nesnenizin MFC'nin uygulaması çağırarak temsilci olarak atayabilir miyim `CreateBindStatusCallback( NULL )`.  
  
 [CAsyncMonikerFile::Open](#open) çağrıları `CreateBindStatusCallback`.  
  
 Zaman uyumsuz adlar ve zaman uyumsuz bağlama hakkında daha fazla bilgi için bkz. [IBindStatusCallback](http://msdn.microsoft.com/library/ie/ms775060) arabirimi ve [ne zaman uyumsuz bağlama ve depolama iş](http://msdn.microsoft.com/library/windows/desktop/aa379152). Toplama için bkz [toplama](http://msdn.microsoft.com/library/windows/desktop/ms686558). Tüm üç Windows SDK'da konulardır.  
  
##  <a name="getbindinfo"></a>  CAsyncMonikerFile::GetBindInfo  
 Nasıl bağlanacağını istediği zaman uyumsuz ad bildirmek için istemciden zaman uyumsuz bir bilinen ad'ın adı.  
  
```  
virtual DWORD GetBindInfo() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ayarlarını alır `IBindStatusCallBack`. Bir açıklaması için `IBindStatusCallback` arabirimi, Windows SDK'sı bakın.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama bağlama depolama Orta (akışı) kullanın ve veri gönderimi modelini kullanmak için uyumsuz olarak ayarlar. Bağlama davranışını değiştirmek istiyorsanız, bu işlev geçersiz kılar.  
  
 Veri çekme modeli yerine veri gönderme modeli kullanarak bağlamak için bunu yapmak için bir neden olacaktır. Bir veri çekme modeli, bağlama işlemi istemci sürücüleri ve onu okunduğunda ad verileri istemciye yalnızca sağlar. Bir veri alım modelinde bilinen ad, zaman uyumsuz bağlama işlemi sürücüleri ve yeni veriler kullanılabilir olduğunda istemci sürekli olarak bildirir.  
  
##  <a name="getbinding"></a>  CAsyncMonikerFile::GetBinding  
 Zaman uyumsuz aktarım bağlama bir işaretçi almak için bu işlevi çağırın.  
  
```  
IBinding* GetBinding() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi `IBinding` zaman uyumsuz aktarımı başladığında sağlanan arabirim. Herhangi bir nedenle, aktarımı NULL döndürür, zaman uyumsuz olarak yapılamaz.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu, veri aktarım işlemi aracılığıyla denetlemenize olanak tanır `IBinding` , ile örnek için arabirim `IBinding::Abort`, `IBinding::Pause`, ve `IBinding::Resume`.  
  
 Bir açıklaması için `IBinding` arabirimi, Windows SDK'sı bakın.  
  
##  <a name="getformatetc"></a>  CAsyncMonikerFile::GetFormatEtc  
 Akıştaki verilerin biçimini almak için bu işlevi çağırın.  
  
```  
FORMATETC* GetFormatEtc() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Windows yapısı işaretçisi [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) şu anda açılan içerik akışı için. Zaman uyumsuz değilse, ad, bağlı değil veya zaman uyumsuz işlem başlatılmamıştır yoksa NULL döndürülür.  
  
##  <a name="getpriority"></a>  CAsyncMonikerFile::GetPriority  
 İş parçacığına bağlama işlemi için verilen öncelik almak bağlama işlemi başlattığında çağrılan zaman uyumsuz bir bilinen ad istemci.  
  
```  
virtual LONG GetPriority() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öncelik, zaman uyumsuz aktarımı yerini alacak. Standart iş parçacığı önceliği bayrakları birini: THREAD_PRIORITY_ABOVE_NORMAL, THREAD_PRIORITY_BELOW_NORMAL, THREAD_PRIORITY_HIGHEST, THREAD_PRIORITY_IDLE, THREAD_PRIORITY_LOWEST, THREAD_PRIORITY_NORMAL ve THREAD_PRIORITY_TIME_CRITICAL. Windows işlevi görmek [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) bu değerleri bir açıklaması.  
  
### <a name="remarks"></a>Açıklamalar  
 `GetPriority` doğrudan çağrılmamalıdır. THREAD_PRIORITY_NORMAL varsayılan uygulama tarafından döndürülür.  
  
##  <a name="ondataavailable"></a>  CAsyncMonikerFile::OnDataAvailable  
 Zaman uyumsuz bir bilinen ad çağırır `OnDataAvailable` kullanılabilir olduğunda, istemcinin veri sağlamak için sırasında zaman uyumsuz işlemleri bağlayın.  
  
```  
virtual void OnDataAvailable(DWORD dwSize, DWORD bscfFlag);
```  
  
### <a name="parameters"></a>Parametreler  
 *dwSize*  
 Veri bağlama başlangıcından itibaren kullanılabilir toplam miktarı (bayt cinsinden). Veri miktarı işlemi için uygun değil ya da hiçbir belirli bir miktarın mevcut geldiğini gösteren sıfır olabilir.  
  
 *bscfFlag*  
 BSCF numaralandırma değeri. Bir veya daha fazla aşağıdaki değerlerden biri olabilir:  
  
- İlk çağrıda BSCF_FIRSTDATANOTIFICATION tanımlar `OnDataAvailable` verilen bağlama işlemi için.  
  
- BSCF_INTERMEDIATEDATANOTIFICATION tanımlayan bir aracı çağrı `OnDataAvailable` bağlama işlemi için.  
  
- BSCF_LASTDATANOTIFICATION tanımlayan son çağrı `OnDataAvailable` bağlama işlemi için.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlevin varsayılan uygulama, hiçbir şey yapmaz. Örnek uygulama için aşağıdaki örneğe bakın.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWinInet#5](../../mfc/codesnippet/cpp/casyncmonikerfile-class_1.cpp)]  
  
##  <a name="onlowresource"></a>  CAsyncMonikerFile::OnLowResource  
 Kaynaklar yetersiz olduğunda ad tarafından çağrılır.  
  
```  
virtual void OnLowResource();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan Uygulama çağrıları `GetBinding( )-> Abort( )`.  
  
##  <a name="onprogress"></a>  CAsyncMonikerFile::OnProgress  
 Art arda genellikle aralıklarla makul uzun bir işlem sırasında bu bağlama işleminin geçerli ilerlemeyi göstermek için bilinen ad tarafından çağrılır.  
  
```  
virtual void OnProgress(
    ULONG ulProgress,  
    ULONG ulProgressMax,  
    ULONG ulStatusCode,  
    LPCTSTR szStatusText);
```  
  
### <a name="parameters"></a>Parametreler  
 *ulProgress*  
 Bağlama işlemi belirtilen beklenen en yüksek göre geçerli ilerlemesini gösteren *ulProgressMax*.  
  
 *ulProgressMax*  
 Beklenen maksimum değeri belirten *ulProgress* yapılan çağrıların süresi `OnProgress` bu işlem için.  
  
 *ulStatusCode*  
 Bağlama işlemi ilerleme durumu ile ilgili ek bilgiler sağlar. Geçerli değerler verilerinden alınır `BINDSTATUS` sabit listesi. Uyarılar için olası değerler başvurun.  
  
 *szStatusText*  
 Değerine bağlı olarak, geçerli ilerleme durumu hakkında bilgi *ulStatusCode*. Uyarılar için olası değerler başvurun.  
  
### <a name="remarks"></a>Açıklamalar  
 Olası değerler için *ulStatusCode* (ve *szStatusText* her değerin) şunlardır:  
  
 BINDSTATUS_FINDINGRESOURCE  
 Bağlama işlemi, nesne ya da depolama için bağlı kaynağı buluyor. *SzStatusText* Aranan kaynak görünen adını sağlar (örneğin, "www.microsoft.com") için.  
  
 BINDSTATUS_CONNECTING  
 Bağlama işlemi nesne veya depolama için bağlı tutar kaynak bağlanıyor demektir. *SzStatusText* görünen adını (örneğin, bir IP adresi) bağlı kaynak sağlar.  
  
 BINDSTATUS_SENDINGREQUEST  
 Bağlama işlemi nesne veya depolama için bağlı istiyor. *SzStatusText* nesnesinin görünen adını (örneğin, bir dosya adı) sağlar.  
  
 BINDSTATUS_REDIRECTING  
 Bağlama işlemi, farklı veri konumuna yönlendirildi. *SzStatusText* yeni veri konumu görünen adını sağlar.  
  
 BINDSTATUS_USINGCACHEDCOPY  
 Bağlama işlemi, depolama ve istenen nesne önbelleğe alınmış bir kopyasından alıyor. *SzStatusText* null.  
  
 BINDSTATUS_BEGINDOWNLOADDATA  
 Bağlama işlemi, nesne veya depolama için bağlı Alma başladı. *SzStatusText* veri konumu görünen adını sağlar.  
  
 BINDSTATUS_DOWNLOADINGDATA  
 Bağlama işlemi, nesne veya depolama için bağlı almaya devam eder. *SzStatusText* veri konumu görünen adını sağlar.  
  
 BINDSTATUS_ENDDOWNLOADDATA  
 Bağlama işlemi, nesne veya depolama için bağlı alma tamamlandı. *SzStatusText* veri konumu görünen adını sağlar.  
  
 BINDSTATUS_CLASSIDAVAILABLE  
 Bağlanan nesne neredeyse oluşturulacak örneğidir. *SzStatusText* bağlama işlemi iptal etmek bir fırsat isterseniz rotasyonunun CLSID yeni nesnenin dize biçiminde sağlar.  
  
##  <a name="onstartbinding"></a>  CAsyncMonikerFile::OnStartBinding  
 Bu işlev, türetilmiş sınıflarda bağlama başlatma sırasında eylemleri gerçekleştirmek için geçersiz kılın.  
  
```  
virtual void OnStartBinding();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, ad tarafından geri çağrılır. Varsayılan uygulama, hiçbir şey yapmaz.  
  
##  <a name="onstopbinding"></a>  CAsyncMonikerFile::OnStopBinding  
 Bağlama işlemi sonunda ad tarafından çağrılır.  
  
```  
virtual void OnStopBinding(HRESULT hresult, LPCTSTR szError);
```  
  
### <a name="parameters"></a>Parametreler  
 *HRESULT*  
 Hata veya uyarı değeri HRESULT.  
  
 *szErrort*  
 Hatayı açıklayan bir karakter dizesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Aktarım bittiğinde eylemleri gerçekleştirmek için bu işlevi geçersiz kılar. Varsayılan olarak, işlev serbest `IBinding`.  
  
 Bir açıklaması için `IBinding` arabirimi, Windows SDK'sı bakın.  
  
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
 *lpszURL*  
 Zaman uyumsuz olarak açılmasını dosyaya bir işaretçi. Dosya geçerli bir URL veya dosya adı olabilir.  
  
 *pError*  
 Dosya özel durumları için bir işaretçi. Bir hata olması durumunda, neden ayarlanır.  
  
 *pMoniker*  
 Zaman uyumsuz ad arabirim işaretçisi `IMoniker`, ile alabilirsiniz belgenin kendi ad birleşimidir kesin bir bilinen ad `IOleClientSite::GetMoniker(OLEWHICHMK_CONTAINER)`ve yol adından oluşturulmuş bir bilinen ad. Denetimi, bu ad bağlamak için kullanabilirsiniz, ancak bu denetimin kaydetmelisiniz bilinen adı değil.  
  
 *pBindHost*  
 Bir işaretçi `IBindHost` ad potansiyel olarak göreli bir yol oluşturmak için kullanılan arabirim. Bağlama ana bilgisayar geçersiz ya da bir bilinen ad sağlamaz, arama için varsayılan olarak `Open(lpszFileName,pError)`. Bir açıklaması için `IBindHost` arabirimi, Windows SDK'sı bakın.  
  
 *pServiceProvider*  
 Bir işaretçi `IServiceProvider` arabirimi. Hizmet sağlayıcısı geçersiz, veya hizmet için sunamaz `IBindHost`, çağrı varsayılanları `Open(lpszFileName,pError)`.  
  
 *pUnknown*  
 Bir işaretçi `IUnknown` arabirimi. Varsa `IServiceProvider` bulunduğunda işlevi sorgularında `IBindHost`. Hizmet sağlayıcısı geçersiz, veya hizmet için sunamaz `IBindHost`, çağrı varsayılanları `Open(lpszFileName,pError)`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dosya başarıyla açıldı olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu çağrı, bağlama işlemi başlatır.  
  
 Bir URL veya dosya adı için kullanabileceğiniz *lpszURL* parametresi. Örneğin:  
  
 [!code-cpp[NVC_MFCWinInet#6](../../mfc/codesnippet/cpp/casyncmonikerfile-class_2.cpp)]  
  
 - veya -  
  
 [!code-cpp[NVC_MFCWinInet#7](../../mfc/codesnippet/cpp/casyncmonikerfile-class_3.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CMonikerFile sınıfı](../../mfc/reference/cmonikerfile-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CMonikerFile sınıfı](../../mfc/reference/cmonikerfile-class.md)   
 [CDataPathProperty Sınıfı](../../mfc/reference/cdatapathproperty-class.md)
