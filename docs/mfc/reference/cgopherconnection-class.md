---
title: CGopherConnection sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CGopherConnection
- AFXINET/CGopherConnection
- AFXINET/CGopherConnection::CGopherConnection
- AFXINET/CGopherConnection::CreateLocator
- AFXINET/CGopherConnection::GetAttribute
- AFXINET/CGopherConnection::OpenFile
dev_langs:
- C++
helpviewer_keywords:
- CGopherConnection [MFC], CGopherConnection
- CGopherConnection [MFC], CreateLocator
- CGopherConnection [MFC], GetAttribute
- CGopherConnection [MFC], OpenFile
ms.assetid: b5b96aea-ac99-430e-bd84-d1372b43f78f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ad48c78d46928a34a43fab5bbe660750928baf51
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37336767"
---
# <a name="cgopherconnection-class"></a>CGopherConnection sınıfı
Gopher Internet sunucusuyla olan bağlantınızı yönetir.  
  
> [!NOTE]
>  Sınıfları `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` ve üyeleri bırakılmıştır, Windows XP platformu üzerinde çalışmaz, ancak önceki platformları üzerinde çalışmaya devam eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CGopherConnection : public CInternetConnection  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CGopherConnection::CGopherConnection](#cgopherconnection)|Oluşturur bir `CGopherConnection` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CGopherConnection::CreateLocator](#createlocator)|Oluşturur bir [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) bir gopher sunucusunda dosyaları bulmak için nesne.|  
|[CGopherConnection::GetAttribute](#getattribute)|Gopher nesnesine ilişkin öznitelik bilgileri alır.|  
|[CGopherConnection::OpenFile](#openfile)|Bir gopher dosyasını açar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Gopher hizmet MFC WinINet sınıfları tarafından tanınan üç Internet Hizmetleri biridir.  
  
 Sınıf `CGopherConnection` bir oluşturucu ve gopher servisini yönetebileceğiniz üç ek üye işlevleri içerir: [Openfıle](#openfile), [CreateLocator](#createlocator), ve [GetAttribute](#getattribute).  
  
 Bir gopher Internet sunucusuyla iletişim kurmak için öncelikle bir örneğini oluşturmanız gerekir [Cınternetsession](../../mfc/reference/cinternetsession-class.md)ve sonra çağrı [CInternetSession::GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection), oluşturan `CGopherConnection` Nesne ve bir işaretçi döndürür. Asla oluşturma bir `CGopherConnection` doğrudan nesne.  
  
 Hakkında daha fazla bilgi edinmek için `CGopherConnection` diğer Internet MFC sınıfları ile çalışır, başlıklı makaleye bakın [Winınet'in Internet programlama](../../mfc/win32-internet-extensions-wininet.md). Desteklenen Internet hizmetlerine diğer iki kullanma hakkında daha fazla bilgi için FTP ve HTTP sınıfları görmek [CHttpConnection](../../mfc/reference/chttpconnection-class.md) ve [CFtpConnection](../../mfc/reference/cftpconnection-class.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)  
  
 `CGopherConnection`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxinet.h  
  
##  <a name="cgopherconnection"></a>  CGopherConnection::CGopherConnection  
 Bu üye işlevi oluşturmak için çağrılan bir `CGopherConnection` nesne.  
  
```  
CGopherConnection(
    CInternetSession* pSession,  
    HINTERNET hConnected,  
    LPCTSTR pstrServer,  
    DWORD_PTR dwContext);

 
CGopherConnection(
    CInternetSession* pSession,  
    LPCTSTR pstrServer,  
    LPCTSTR pstrUserName = NULL,  
    LPCTSTR pstrPassword = NULL,  
    DWORD_PTR dwContext = 0,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```  
  
### <a name="parameters"></a>Parametreler  
 *pSession*  
 İlgili bir işaretçiye [Cınternetsession](../../mfc/reference/cinternetsession-class.md) nesne.  
  
 *hConnected*  
 Geçerli Internet oturumu Windows tanıtıcısı.  
  
 *pstrServer*  
 FTP sunucusu adını içeren bir dize işaretçisi.  
  
 *dwContext*  
 İşlem bağlamı tanımlayıcısı. *dwContext* tarafından döndürülen işlem durumu bilgilerini tanımlayan [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback). Varsayılan değer 1 olarak ayarlanır; Ancak, belirli bir bağlam kimliği işlemi için açıkça atayabilirsiniz. Nesne ve mevcut herhangi bir iş, bir bağlam kimliği ile ilişkilendirilecek  
  
 *pstrUserName*  
 Oturum açmak için kullanıcı adını belirten bir null ile sonlandırılmış dize işaretçisi. NULL ise, anonim bir varsayılandır.  
  
 *pstrPassword*  
 Oturum açmak için kullanılacak parolayı belirten bir boş sonlandırılmış dizeye bir işaretçi. Her iki *pstrPassword* ve *pstrUserName* NULL, varsayılan anonim kullanıcı e-posta adını paroladır. Varsa *pstrPassword* boş (veya boş bir dize) ancak *pstrUserName* NULL değil boş bir parola kullanılır. Aşağıdaki tabloda dört olası ayarlarını davranışını açıklar *pstrUserName* ve *pstrPassword*:  
  
|*pstrUserName*|*pstrPassword*|FTP sunucusuna gönderilen kullanıcı adı|FTP sunucusuna gönderilen parola|  
|--------------------|--------------------|---------------------------------|---------------------------------|  
|NULL veya ""|NULL veya ""|"anonim"|Kullanıcının e-posta adı|  
|BOŞ olmayan bir dize|NULL veya ""|*pstrUserName*|" "|  
|BOŞ bir NULL olmayan dize|HATA|HATA||  
|BOŞ olmayan bir dize|BOŞ olmayan bir dize|*pstrUserName*|*pstrPassword*|  
  
 *nbağlantı noktası*  
 Sunucu üzerinde kullanılacak TCP/IP bağlantı noktasını tanımlayan bir sayı.  
  
### <a name="remarks"></a>Açıklamalar  
 Asla oluşturma bir `CGopherConnection` doğrudan. Bunun yerine çağrı [CInternetSession::GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection), oluşturan bir `CGopherConnection` nesnesi ve bir işaretçi döndürür.  
  
##  <a name="createlocator"></a>  CGopherConnection::CreateLocator  
 Bulmak veya bir gopher sunucusunda dosya tanımlamak için bir gopher Bulucusu oluşturmak için bu üye işlevini çağırın.  
  
```  
CGopherLocator CreateLocator(
    LPCTSTR pstrDisplayString,  
    LPCTSTR pstrSelectorString,  
    DWORD dwGopherType);  
  
static CGopherLocator CreateLocator(LPCTSTR pstrLocator);

 
static CGopherLocator CreateLocator(
    LPCTSTR pstrServerName,  
    LPCTSTR pstrDisplayString,  
    LPCTSTR pstrSelectorString,  
    DWORD dwGopherType,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```  
  
### <a name="parameters"></a>Parametreler  
 *pstrDisplayString*  
 Gopher belge veya alınacak dizin adını içeren bir dize işaretçisi. Varsa *pstrDisplayString* gopher sunucusu için varsayılan dizin parametresi, NULL döndürülür.  
  
 *pstrSelectorString*  
 Bir öğe almak için gopher sunucuya gönderilecek Seçici dizeye bir işaretçi. *pstrSelectorString* NULL olabilir.  
  
 *dwGopherType*  
 Bu belirtir olup olmadığını *pstrSelectorString* bir dizin veya belge ifade eder ve isteği gopher veya gopher + olup. Yapı için öznitelikleri görmek [GOPHER_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa384215) Windows SDK.  
  
 *pstrLocator*  
 Açmak için dosyaya tanımlayan bir dize işaretçisi. Genellikle, bu dize çağrısından döndürülen [CGopherFileFind::GetLocator](../../mfc/reference/cgopherfilefind-class.md#getlocator).  
  
 *pstrServerName*  
 Gopher sunucu adını içeren bir dize işaretçisi.  
  
 *nbağlantı noktası*  
 Bu bağlantı için Internet bağlantı noktasını tanımlayan numara.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini statik sürümünü, statik olmayan sürüm bağlantı nesnesi sunucu adını kullanırken, bir sunucu belirtmek gerektirir.  
  
 Bir gopher sunucusundan bilgi almak için bir uygulama ilk kez bir gopher Bulucu almanız gerekir. Uygulama ardından Bulucu donuk bir belirteç olarak ele almanız gerekir (diğer bir deyişle, uygulama Bulucu kullanın ancak değil doğrudan değiştirmek veya bu karşılaştırın). Normalde, çağrılar için Bulucu uygulamanın kullandığı [CGopherFileFind::FindFile](../../mfc/reference/cgopherfilefind-class.md#findfile) belirli bir bilgi almak için üye işlevi.  
  
##  <a name="getattribute"></a>  CGopherConnection::GetAttribute  
 Gopher sunucusundan bir öğeyle ilgili belirli bir öznitelik bilgileri almak için bu üye işlevini çağırın.  
  
```  
BOOL GetAttribute(
    CGopherLocator& refLocator    CString strRequestedAttributes,  
    CString& strResult,);
```  
  
### <a name="parameters"></a>Parametreler  
 *refLocator*  
 Bir başvuru bir [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) nesne.  
  
 *strRequestedAttributes*  
 İstenen öznitelikleri adlarını belirten boşlukla ayrılmış bir dize.  
  
 *strResult*  
 Bir başvuru bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) , Bulucu türünü alır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa sıfır dışı; Aksi durumda 0. Çağrı başarısız olursa, Win32 işlevini [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) hatanın nedenini belirlemek için çağrılabilir.  
  
##  <a name="openfile"></a>  CGopherConnection::OpenFile  
 Bir gopher sunucusunda bir dosyayı açmak için bu üye işlevini çağırın.  
  
```  
CGopherFile* OpenFile(
    CGopherLocator& refLocator,  
    DWORD dwFlags = 0,  
    LPCTSTR pstrView = NULL,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Parametreler  
 *refLocator*  
 Bir başvuru bir [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) nesne.  
  
 *CertOpenStore*  
 Herhangi bir birleşimini INTERNET_FLAG_ * işaretler. Bkz: [CInternetSession::OpenUrl](../../mfc/reference/cinternetsession-class.md#openurl) INTERNET_FLAG_ ilgili daha fazla bilgi için\* bayrakları.  
  
 *pstrView*  
 Dosya görünümü dizeye bir işaretçi. Dosyanın çeşitli görünümlerini sunucuda mevcutsa, bu parametre hangi dosya görünümü açmak için belirtir. Varsa *pstrView* NULL ise varsayılan dosya görünümüne kullanılır.  
  
 *dwContext*  
 Açılan dosya bağlam kimliği. Bkz: **açıklamalar** hakkında daha fazla bilgi için *dwContext*.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi [CGopherFile](../../mfc/reference/cgopherfile-class.md) açılması için nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçersiz kılma *dwContext* varsayılan bağlamı tanımlayıcısını bir değere ayarlamak için. Bu belirli işlemle ilişkili bağlam tanımlayıcıdır `CGopherConnection` tarafından oluşturulan nesne kendi [Cınternetsession](../../mfc/reference/cinternetsession-class.md) nesne. İçin döndürülen değer [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) ile belirtilen işlem durumu sağlamak için. Makaleye göz atın [Internet ilk adımlar: WinINet](../../mfc/wininet-basics.md) bağlam tanımlayıcısı hakkında daha fazla bilgi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Cınternetconnection sınıfı](../../mfc/reference/cinternetconnection-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CFtpConnection sınıfı](../../mfc/reference/cftpconnection-class.md)   
 [CHttpConnection sınıfı](../../mfc/reference/chttpconnection-class.md)   
 [Cınternetconnection sınıfı](../../mfc/reference/cinternetconnection-class.md)   
 [CGopherLocator sınıfı](../../mfc/reference/cgopherlocator-class.md)   
 [CGopherFile sınıfı](../../mfc/reference/cgopherfile-class.md)   
 [CInternetSession Sınıfı](../../mfc/reference/cinternetsession-class.md)
