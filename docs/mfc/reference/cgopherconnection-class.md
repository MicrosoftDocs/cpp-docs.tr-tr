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
ms.openlocfilehash: d3dc5dae7758c77d335cf6e1255d8caba28df9f9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cgopherconnection-class"></a>CGopherConnection sınıfı
Gopher Internet sunucusu bağlantınız yönetir.  
  
> [!NOTE]
>  Sınıfları `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` ve üyeleri Windows XP platformunda çalışmaz, ancak daha önceki platformlar üzerinde çalışmaya devam edecek kullanım dışı bırakıldı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CGopherConnection : public CInternetConnection  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CGopherConnection::CGopherConnection](#cgopherconnection)|Oluşturan bir `CGopherConnection` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CGopherConnection::CreateLocator](#createlocator)|Oluşturur bir [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) bir gopher sunucusundaki dosyaları bulunacak nesne.|  
|[CGopherConnection::GetAttribute](#getattribute)|Gopher nesne özniteliği bilgilerini alır.|  
|[CGopherConnection::OpenFile](#openfile)|Gopher dosyasını açar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Gopher hizmeti tarafından MFC WinINet sınıfları tanınır üç Internet services biridir.  
  
 Sınıf `CGopherConnection` bir oluşturucu ve gopher hizmet yöneten üç ek üye işlevlerini içerir: [OpenFile](#openfile), [CreateLocator](#createlocator), ve [GetAttribute](#getattribute).  
  
 Gopher Internet sunucusu ile iletişim kurmak için önce bir örneğini oluşturmanız gerekir [CInternetSession](../../mfc/reference/cinternetsession-class.md)ve ardından arama [CInternetSession::GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection), oluşturan `CGopherConnection` Nesne ve bir işaretçi döndürür. Hiçbir zaman oluşturduğunuz bir `CGopherConnection` doğrudan nesne.  
  
 Hakkında daha fazla bilgi için `CGopherConnection` diğer MFC Internet sınıfları ile works başlıklı makaleye bakın [Internet programlama WinINet ile](../../mfc/win32-internet-extensions-wininet.md). Internet Hizmetleri diğer iki kullanma hakkında daha fazla bilgi desteklenen, FTP ve HTTP sınıfları Bkz [CHttpConnection](../../mfc/reference/chttpconnection-class.md) ve [CFtpConnection](../../mfc/reference/cftpconnection-class.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)  
  
 `CGopherConnection`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxinet.h  
  
##  <a name="cgopherconnection"></a>  CGopherConnection::CGopherConnection  
 Bu üye işlevi oluşturmak için çağrılan bir `CGopherConnection` nesnesi.  
  
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
 `pSession`  
 Bir işaretçi ilgili [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesi.  
  
 `hConnected`  
 Windows tanıtıcı geçerli Internet oturumunun.  
  
 `pstrServer`  
 FTP sunucusu adını içeren bir dize için bir işaretçi.  
  
 `dwContext`  
 İşlem bağlamı tanımlayıcısı. `dwContext` işlem durumu bilgileri tarafından döndürülen tanımlayan [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback). Varsayılan değer 1 olarak ayarlanır; Ancak, belirli bir bağlam kimliği işlemi için açıkça atayabilirsiniz. Nesne ve mevcut herhangi bir iş, içerik kimliği ile ilişkilendirilecek  
  
 `pstrUserName`  
 İşaretçi null ile sonlandırılmış dizeye oturum açmak için kullanıcı adını belirtir. Varsa **NULL**, anonim varsayılandır.  
  
 `pstrPassword`  
 Oturum açmak için kullanılacak parolayı belirten null ile sonlandırılmış bir dize için bir işaretçi. Her iki `pstrPassword` ve `pstrUserName` olan **NULL**, varsayılan anonim parola kullanıcının e-posta adıdır. Varsa `pstrPassword` olan **NULL** (veya boş bir dize) ancak `pstrUserName` değil **NULL**, boş bir parola kullanılır. Aşağıdaki tabloda dört olası ayarlarını davranışını açıklanmaktadır `pstrUserName` ve `pstrPassword`:  
  
|`pstrUserName`|`pstrPassword`|FTP sunucusuna gönderilen kullanıcı adı|FTP sunucusuna gönderilen parola|  
|--------------------|--------------------|---------------------------------|---------------------------------|  
|**NULL** veya ""|**NULL** veya ""|"anonim"|Kullanıcının e-posta adı|  
|Olmayan- **NULL** dize|**NULL** veya ""|`pstrUserName`|" "|  
|**NULL** olmayan **NULL** dize|**HATA**|**HATA**||  
|Olmayan- **NULL** dize|Olmayan- **NULL** dize|`pstrUserName`|`pstrPassword`|  
  
 `nPort`  
 Sunucuda kullanmak için TCP/IP bağlantı noktası tanımlayan bir sayı.  
  
### <a name="remarks"></a>Açıklamalar  
 Hiçbir zaman oluşturduğunuz bir `CGopherConnection` doğrudan. Bunun yerine, çağrı [CInternetSession::GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection), oluşturan bir `CGopherConnection` nesne ve bir işaretçi döndürür.  
  
##  <a name="createlocator"></a>  CGopherConnection::CreateLocator  
 Bulunamadı veya bir dosyayı bir gopher sunucuda tanımlamak gopher Bulucusu oluşturmak için bu üye işlevini çağırın.  
  
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
 `pstrDisplayString`  
 Gopher belge ya da alınacak dizinin adını içeren bir dize için bir işaretçi. Varsa `pstrDisplayString` parametresi **NULL**, gopher sunucunun varsayılan dizini döndürülür.  
  
 `pstrSelectorString`  
 Bir öğeyi geri almak için gopher sunucuya gönderilecek Seçici dizesi için bir işaretçi. `pstrSelectorString` olabilir **NULL**.  
  
 *dwGopherType*  
 Bu belirtir olup olmadığını `pstrSelectorString` bir dizin veya belge başvuruyor ve istek gopher veya gopher + olup. Yapısı için öznitelik [GOPHER_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa384215) Windows SDK'sındaki.  
  
 `pstrLocator`  
 Açmak için dosyaya tanımlayan bir dize için bir işaretçi. Genellikle, bu dize çağrısından döndürülen [CGopherFileFind::GetLocator](../../mfc/reference/cgopherfilefind-class.md#getlocator).  
  
 *pstrServerName*  
 Gopher sunucu adını içeren bir dize için bir işaretçi.  
  
 `nPort`  
 Bu bağlantı için Internet bağlantı noktası tanımlama numarası.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini statik sürümü bağlantı nesnesi sunucu adından statik olmayan sürümü kullanıyor, ancak bir sunucu belirtmenizi gerektirir.  
  
 Gopher sunucudan bilgi almak için uygulamanın önce bir gopher Bulucu almanız gerekir. Uygulama sonra Konumlandırıcı opak belirteci olarak ele almanız gerekir (diğer bir deyişle, uygulama Bulucu ancak doğrudan yönetmek veya kullanabilirsiniz Bu karşılaştırın). Normalde, çağrılar için Bulucu uygulamanın kullandığı [CGopherFileFind::FindFile](../../mfc/reference/cgopherfilefind-class.md#findfile) belirli bir bilgiyi almak için üye işlevi.  
  
##  <a name="getattribute"></a>  CGopherConnection::GetAttribute  
 Gopher sunucudan bir öğesiyle ilgili belirli öznitelik bilgileri almak için bu üye işlevini çağırın.  
  
```  
BOOL GetAttribute(
    CGopherLocator& refLocator    CString strRequestedAttributes,  
    CString& strResult,);
```  
  
### <a name="parameters"></a>Parametreler  
 `refLocator`  
 Bir başvuru bir [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) nesnesi.  
  
 *strRequestedAttributes*  
 İstenen özniteliklerin adlarıyla belirten boşlukla ayrılmış bir dize.  
  
 `strResult`  
 Bir başvuru bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) Bulucu türünü alır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0. Çağrı başarısız olursa, Win32 işlevi [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) hatanın nedenini belirlemek için çağrılabilir.  
  
##  <a name="openfile"></a>  CGopherConnection::OpenFile  
 Gopher sunucusunda bir dosyayı açmak için bu üye işlevini çağırın.  
  
```  
CGopherFile* OpenFile(
    CGopherLocator& refLocator,  
    DWORD dwFlags = 0,  
    LPCTSTR pstrView = NULL,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Parametreler  
 `refLocator`  
 Bir başvuru bir [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) nesnesi.  
  
 `dwFlags`  
 Herhangi bir bileşimini INTERNET_FLAG_ * işaretler. Bkz: [CInternetSession::OpenUrl](../../mfc/reference/cinternetsession-class.md#openurl) INTERNET_FLAG_ ilgili daha fazla bilgi için\* bayrakları.  
  
 `pstrView`  
 Bir dosya görünümü dize için bir işaretçi. Birkaç görünüm dosyasının sunucuda varsa, bu parametre hangi dosya görünümü açmak için belirtir. Varsa `pstrView` olan **NULL**, varsayılan dosya görünümü kullanılır.  
  
 `dwContext`  
 Açılmakta dosya bağlam kimliği. Bkz: **açıklamalar** hakkında daha fazla bilgi için `dwContext`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi [CGopherFile](../../mfc/reference/cgopherfile-class.md) açılması için nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçersiz kılma `dwContext` varsayılan bağlam tanımlayıcı bir değerine ayarlayın. Bağlam tanıtıcısı belirli bu işlemle ilişkili `CGopherConnection` tarafından oluşturulan nesne kendi [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesi. İçin döndürülen değer [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) sahip belirtilen işlem durumu sağlamak için. Makalesine bakın [Internet ilk adımlar: WinINet](../../mfc/wininet-basics.md) bağlamı tanımlayıcısı hakkında daha fazla bilgi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CInternetConnection sınıfı](../../mfc/reference/cinternetconnection-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CFtpConnection sınıfı](../../mfc/reference/cftpconnection-class.md)   
 [CHttpConnection sınıfı](../../mfc/reference/chttpconnection-class.md)   
 [CInternetConnection sınıfı](../../mfc/reference/cinternetconnection-class.md)   
 [CGopherLocator sınıfı](../../mfc/reference/cgopherlocator-class.md)   
 [CGopherFile sınıfı](../../mfc/reference/cgopherfile-class.md)   
 [CInternetSession Sınıfı](../../mfc/reference/cinternetsession-class.md)
