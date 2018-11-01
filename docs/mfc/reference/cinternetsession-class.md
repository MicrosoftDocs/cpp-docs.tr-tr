---
title: Cınternetsession sınıfı
ms.date: 06/20/2018
f1_keywords:
- CInternetSession
- AFXINET/CInternetSession
- AFXINET/CInternetSession::CInternetSession
- AFXINET/CInternetSession::Close
- AFXINET/CInternetSession::EnableStatusCallback
- AFXINET/CInternetSession::GetContext
- AFXINET/CInternetSession::GetCookie
- AFXINET/CInternetSession::GetCookieLength
- AFXINET/CInternetSession::GetFtpConnection
- AFXINET/CInternetSession::GetGopherConnection
- AFXINET/CInternetSession::GetHttpConnection
- AFXINET/CInternetSession::OnStatusCallback
- AFXINET/CInternetSession::OpenURL
- AFXINET/CInternetSession::SetCookie
- AFXINET/CInternetSession::SetOption
helpviewer_keywords:
- CInternetSession [MFC], CInternetSession
- CInternetSession [MFC], Close
- CInternetSession [MFC], EnableStatusCallback
- CInternetSession [MFC], GetContext
- CInternetSession [MFC], GetCookie
- CInternetSession [MFC], GetCookieLength
- CInternetSession [MFC], GetFtpConnection
- CInternetSession [MFC], GetGopherConnection
- CInternetSession [MFC], GetHttpConnection
- CInternetSession [MFC], OnStatusCallback
- CInternetSession [MFC], OpenURL
- CInternetSession [MFC], SetCookie
- CInternetSession [MFC], SetOption
ms.assetid: ef54feb4-9d0f-4e65-a45d-7a4cf6c40e51
ms.openlocfilehash: a3acc035a1781bd67cfc3b5561eb6dbdef41de72
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50586338"
---
# <a name="cinternetsession-class"></a>Cınternetsession sınıfı

Oluşturur ve tek bir veya birden çok eşzamanlı Internet oturumu başlatır ve gerekirse bağlantınızı bir ara sunucuya tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
class CInternetSession : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CInternetSession::CInternetSession](#cinternetsession)|Oluşturur bir `CInternetSession` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CInternetSession::Close](#close)|Internet oturumu sonlandırıldığında Internet bağlantıyı kapatır.|
|[CInternetSession::EnableStatusCallback](#enablestatuscallback)|Durumu geri çağırma yordamı oluşturur.|
|[CInternetSession::GetContext](#getcontext)|Internet oturumu sonlandırıldığında Internet bağlantıyı kapatır.|
|[CInternetSession::GetCookie](#getcookie)|Tanımlama bilgileri, belirtilen URL'yi ve tüm üst için URL'leri döndürür.|
|[CInternetSession::GetCookieLength](#getcookielength)|Arabellekteki depolanan bir tanımlama bilgisi uzunluğunu belirten değişken alır.|
|[CInternetSession::GetFtpConnection](#getftpconnection)|Sunucusu ile FTP oturumu açılır. Kullanıcı günlüğe kaydeder.|
|[CInternetSession::GetGopherConnection](#getgopherconnection)|Bir bağlantı açmaya çalışırken bir uygulama için bir gopher sunucusu açılır.|
|[CInternetSession::GetHttpConnection](#gethttpconnection)|Bir bağlantı açmaya çalışırken bir uygulama için bir HTTP sunucusu açılır.|
|[CInternetSession::OnStatusCallback](#onstatuscallback)|Durum geri çağırması etkin olduğunda, bir işlemin durumunu güncelleştirir.|
|[CInternetSession::OpenURL](#openurl)|Ayrıştırır ve bir URL açılır.|
|[CInternetSession::SetCookie](#setcookie)|Belirtilen URL için bir tanımlama bilgisi ayarlar.|
|[CInternetSession::SetOption](#setoption)|Seçenekler Internet oturumu için ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CInternetSession::operator HINTERNET](#operator_hinternet)|Geçerli Internet oturumu için bir tanıtıcı.|

## <a name="remarks"></a>Açıklamalar

Bir uygulama süresi boyunca Internet bağlantınızın tutulması gereken, oluşturabileceğiniz bir `CInternetSession` sınıfının üyesi [CWinApp](../../mfc/reference/cwinapp-class.md).

Bir Internet oturumu kurduktan sonra çağırabilirsiniz [OpenURL](#openurl). `CInternetSession` ardından URL'yi sizin için genel bir işlev çağırarak ayrıştırır [AfxParseURL](internet-url-parsing-globals.md#afxparseurl). Kendi protokol türü ne olursa olsun `CInternetSession` URL yorumlar ve sizin yerinize yönetir. Bu URL kaynağının "file://" ile tanımlanan yerel dosyalarla ilgili istekleri işleyebilir. `OpenURL` bir işaretçi döndürür bir [CStdioFile](../../mfc/reference/cstdiofile-class.md) adı geçirdiğiniz nesne yerel bir dosyasıdır.

Bir URL kullanarak bir Internet sunucusu üzerinde açarsanız `OpenURL`, site veritabanından bilgi edinebilirsiniz. Bir sunucuda bulunan dosya çubuğunda (örneğin, HTTP, FTP veya gopher için) hizmete özgü eylemleri gerçekleştirmek istiyorsanız, o sunucuda uygun bir bağlantı oluşturmanız gerekir. Belirli bir doğrudan belirli bir hizmet bağlantı türünü açmak için aşağıdaki üye işlevleri birini kullanın:

- [GetGopherConnection](#getgopherconnection) bir gopher hizmetine bir bağlantı açmak için.

- [GetHttpConnection](#gethttpconnection) HTTP hizmetine bir bağlantı açmak için.

- [GetFtpConnection](#getftpconnection) FTP hizmetine bir bağlantı açmak için.

[SetOption](#setoption) sayıda yeniden deneme zaman aşımı değerlerini gibi oturumunuz sorgu seçenekleri ayarlama ve benzeri olanak tanır.

`CInternetSession` üye işlevleri [SetCookie](#setcookie), [GetCookie](#getcookie), ve [GetCookieLength](#getcookielength) , sunucuları ve betikleri bakımını bir Win32 tanımlama bilgisi veritabanını yönetmek için bir yöntem sağlar istemci iş istasyonu ile ilgili durum bilgisini.

Temel Internet programlama görevleri hakkında daha fazla bilgi için bkz [Internet ilk adımlar: WinINet](../../mfc/wininet-basics.md). MFC WinINet sınıfları kullanarak hakkında genel bilgi için bkz [Winınet'in Internet programlama](../../mfc/win32-internet-extensions-wininet.md).

> [!NOTE]
> `CInternetSession` oluşturur bir [AfxThrowNotSupportedException](exception-processing.md#afxthrownotsupportedexception) desteklenmeyen hizmet türleri için. Yalnızca şu hizmet türleri şu anda desteklenen: FTP, HTTP, gopher ve dosya.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)<br/>
&nbsp;&nbsp;&nbsp;&nbsp;`CInternetSession`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxinet.h

## <a name="cinternetsession"></a> CInternetSession::CInternetSession

Bu üye işlevi aldığında çağrılan bir `CInternetSession` nesnesi oluşturulur.

```cpp
CInternetSession(
    LPCTSTR pstrAgent = NULL,
    DWORD_PTR dwContext = 1,
    DWORD dwAccessType = PRE_CONFIG_INTERNET_ACCESS,
    LPCTSTR pstrProxyName = NULL,
    LPCTSTR pstrProxyBypass = NULL,
    DWORD dwFlags = 0);
```

### <a name="parameters"></a>Parametreler

*pstrAgent*<br/>
Uygulama veya Internet işlevleri (örneğin, "Microsoft Internet tarayıcısı") çağırma varlık adını tanımlayan bir dize işaretçisi. Varsa *pstrAgent* (varsayılan), framework çağrıları genel işlev null [AfxGetAppName](application-information-and-management.md#afxgetappname), bir uygulamanın adını içeren null ile sonlandırılmış bir dize döndürür. Bazı protokoller, uygulamanızı sunucuya tanımlamak için şu dizeyi kullanın.

*dwContext*<br/>
İşlem bağlamı tanımlayıcısı. *dwContext* tarafından döndürülen işlem durumu bilgilerini tanımlayan [CInternetSession::OnStatusCallback](#onstatuscallback). Varsayılan değer 1 olarak ayarlanır; Ancak, belirli bir bağlam kimliği işlemi için açıkça atayabilirsiniz. Nesne ve mevcut herhangi bir iş, bir bağlam kimliği ile ilişkilendirilecek

*dwAccessType*<br/>
Gerekli erişim türü. Bunlardan biri sağlanacak geçerli değerler şunlardır:

- INTERNET_OPEN_TYPE_PRECONFIG Connect kullanarak kayıt defteri ayarları önceden yapılandırılmış. Bu erişim türü varsayılan olarak ayarlanır. TIS proxy üzerinden bağlanması ayarı *dwAccessType* bu değere; ardından kayıt defteri uygun şekilde ayarlayın.

- INTERNET_OPEN_TYPE_DIRECT doğrudan Internet'e bağlanın.

- INTERNET_OPEN_TYPE_PROXY CERN proxy'si aracılığıyla bağlanın.

Farklı türde proxy ile bağlanma hakkında daha fazla bilgi için bkz. [tipik bir FTP istemci uygulamasında adımları](../../mfc/steps-in-a-typical-ftp-client-application.md).

*pstrProxyName*<br/>
Tercih edilen CERN proxy adını, *dwAccessType* INTERNET_OPEN_TYPE_PROXY ayarlanır. Varsayılan NULL olur.

*pstrProxyBypass*<br/>
İsteğe bağlı bir sunucu adresleri listesi içeren bir dize işaretçisi. Proxy erişimi kullanırken bu adresleri atlanmasına. Bir NULL değer sağlanmazsa, atlama listesi kayıt defterinden okunacak. Bu parametre anlamlı yalnızca *dwAccessType* INTERNET_OPEN_TYPE_PROXY için ayarlanır.

*CertOpenStore*<br/>
Çeşitli önbellek seçeneklerini gösterir. Varsayılan değer 0 olarak ayarlanır. Olası değerler şunlardır:

- INTERNET_FLAG_DONT_CACHE önbelleğe almaz verileri yerel olarak veya herhangi bir ağ geçidi sunucusu.

- INTERNET_FLAG_OFFLINE indirme işlemleri yalnızca kalıcı önbellek aracılığıyla karşılanır. Öğeyi önbellekte mevcut değilse, uygun hata kodu döndürülür. Bu bayrak bit düzeyinde ile birleştirilebilir **veya** ( **&#124;**) işleci.

### <a name="remarks"></a>Açıklamalar

`CInternetSession` ilk Internet işlevi, bir uygulama tarafından çağrılır. İç veri yapılarını başlatır ve uygulamasından sonraki çağrılarda hazırlar.

Internet bağlantısı yok açmış olsaydık `CInternetSession` oluşturur bir [Afxthrowınternetexception](internet-url-parsing-globals.md#afxthrowinternetexception).

### <a name="example"></a>Örnek

Örneğin bakın [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md).

## <a name="close"></a>  CInternetSession::Close

Uygulamanızı kullanarak tamamladığınızda bu üye işlevi çağrısı `CInternetSession` nesne.

```cpp
virtual void Close();
```

### <a name="example"></a>Örnek

Örneğin bakın [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md).

## <a name="enablestatuscallback"></a>  CInternetSession::EnableStatusCallback

Durum geri çağırması etkinleştirmek için bu üye işlevini çağırın.

```cpp
BOOL EnableStatusCallback(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parametreler

*bSistemlerde*<br/>
Geri çağırma etkin mi yoksa devre dışı mı olduğunu belirtir. Varsayılan değer True'dur.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0. Oluşturulan inceleyerek çağrı başarısız olursa hatanın nedenini belirlemek [Cınternetexception](../../mfc/reference/cinternetexception-class.md) nesne.

### <a name="remarks"></a>Açıklamalar

Durum geri çağırması işlenirken, uygulama durum çubuğunda (örneğin, ad çözümleme, bağlama sunucu ve benzeri) işleminin ilerleme durumunu sağlayabilirsiniz. İşlem durumunu görüntüleme uzun süreli bir işlemi sırasında özellikle önerilir.

Uygulama, geri çağırmaları isteğin işleme süresince ortaya çıkan çünkü geri çağırma ağ veri aktarım hızı performansında önlemek için mümkün olduğunca en az zaman ayırın. Örneğin, bir geri çağırma iletişim kutusunda'kurmak koyarak sunucu isteği sonlandırır gibi uzun bir işlem olabilir.

Durum geri çağırması bekleyen herhangi bir geri çağırmaları sürece kaldırılamaz.

Herhangi bir işlem zaman uyumsuz olarak işlemek için kendi iş parçacığı oluşturma veya MFC olmadan WinINet işlevler gerekir.

## <a name="getcontext"></a>  CInternetSession::GetContext

Belirli uygulama oturumu için bağlam değeri almak için bu üye işlevini çağırın.

```cpp
DWORD_PTR GetContext() const;
```

### <a name="return-value"></a>Dönüş Değeri

Uygulama tanımlı içerik tanımlayıcısı.

### <a name="remarks"></a>Açıklamalar

[OnStatusCallback](#onstatuscallback) tarafından döndürülen bağlam Kimliğini kullanan `GetContext` belirli bir uygulama durumunu bildirmek için. Örneğin, kullanıcı durum bilgilerini döndürmek içeren bir Internet isteği etkinleştirirken, durum geri çağırması belirli bu isteği için durumu rapor edebilmiş bağlam Kimliğini kullanır. İki ayrı kullanıcı etkinleştirir, Internet isteklerini hem de ilgili durum bilgilerini döndürmek `OnStatusCallback` karşılık gelen isteklerin durumunu döndürmek için bağlam tanımlayıcıları kullanır. Sonuç olarak, bağlam tanımlayıcı tüm durumu geri çağırma işlemleri için kullanılır ve oturumu sonlanana oturumu ile ilişkilidir.

Zaman uyumsuz işlemler hakkında daha fazla bilgi için bkz [Internet ilk adımlar: WinINet](../../mfc/wininet-basics.md).

## <a name="getcookie"></a>  CInternetSession::GetCookie

Bu üye işlevi Win32 işlevinin davranışı uygulayan [InternetGetCookie](/windows/desktop/api/wininet/nf-wininet-internetgetcookiea)Windows SDK içinde açıklandığı gibi.

```cpp
static BOOL GetCookie(
    LPCTSTR pstrUrl,
    LPCTSTR pstrCookieName,
    LPTSTR pstrCookieData,
    DWORD dwBufLen);

static BOOL GetCookie(
    LPCTSTR pstrUrl,
    LPCTSTR pstrCookieName,
    CString& strCookieData);
```

### <a name="parameters"></a>Parametreler

*pstrUrl*<br/>
URL içeren bir dize işaretçisi.

*pstrCookieName*<br/>
Belirtilen URL'ye almak için tanımlama bilgisi adını içeren bir dize işaretçisi.

*pstrCookieData*<br/>
İlk aşırı, tanımlama bilgisi verileri alan arabellek adresi içeren bir dize işaretçisi. Bu değer NULL olabilir. İkinci aşırı yükleme, bir başvuru olarak bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) tanımlama bilgisi verisi almak için nesne.

*dwBufLen*<br/>
Boyutun belirtmek değişkeni *pstrCookieData* arabellek. İşlev başarılı olursa, arabellek kopyalanan verileri miktarını alır *pstrCookieData* arabellek. Varsa *pstrCookieData* NULL ise bu parametre tanımlama bilgisi verileri kopyalamak gerekli arabellek boyutunu belirten bir değeri alır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa TRUE veya FALSE döndürür. Çağrı başarısız olursa Win32 işlevini çağırmak [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) hatanın nedenini belirlemek için. Aşağıdaki hata değerler geçerlidir:

- ERROR_NO_MORE_ITEMS belirtilen URL için tanımlama bilgisi ve tüm üst öğelerinden yoktur.

- Geçirilen değere ERROR_INSUFFICIENT_BUFFER *dwBufLen* tüm tanımlama bilgisi verileri kopyalamak için yeterli değil. Döndürülen değer *dwBufLen* arabellek boyutu, tüm verileri almak gereklidir.

### <a name="remarks"></a>Açıklamalar

İkinci aşırı yükleme MFC tanımlama bilgisi verisi sağlanan alır `CString` nesne.

## <a name="getcookielength"></a>  CInternetSession::GetCookieLength

Arabellekteki depolanan bir tanımlama bilgisi uzunluğunu almak için bu üye işlevini çağırın.

```cpp
static DWORD GetCookieLength(
    LPCTSTR pstrUrl,
    LPCTSTR pstrCookieName);
```

### <a name="parameters"></a>Parametreler

*pstrUrl*<br/>
URL içeren bir dize işaretçisi

*pstrCookieName*<br/>
Tanımlama bilgisinin adını içeren bir dize işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Tanımlama bilgisi uzunluğunu belirten bir DWORD değeri arabellekteki depolanır. Tarafından belirtilen ada sahip tanımlama bilgisi varsa sıfır *pstrCookieName* bulunmaktadır.

### <a name="remarks"></a>Açıklamalar

Bu değer tarafından kullanılan [GetCookie](#getcookie).

## <a name="getftpconnection"></a>  CInternetSession::GetFtpConnection

FTP bağlantısı kurmak ve işaretçi almak için bu üye işlevi çağrısı bir `CFtpConnection` nesne.

```cpp
CFtpConnection* GetFtpConnection(
    LPCTSTR pstrServer,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    BOOL bPassive = FALSE);
```

### <a name="parameters"></a>Parametreler

*pstrServer*<br/>
FTP sunucusu adını içeren bir dize işaretçisi.

*pstrUserName*<br/>
Oturum açmak için kullanıcı adını belirten bir null ile sonlandırılmış dize işaretçisi. NULL ise, anonim bir varsayılandır.

*pstrPassword*<br/>
Oturum açmak için kullanılacak parolayı belirten bir boş sonlandırılmış dizeye bir işaretçi. Her iki *pstrPassword* ve *pstrUserName* NULL, varsayılan anonim kullanıcı e-posta adını paroladır. Varsa *pstrPassword* boş (veya boş bir dize) ancak *pstrUserName* NULL değil boş bir parola kullanılır. Aşağıdaki tabloda dört olası ayarlarını davranışını açıklar *pstrUserName* ve *pstrPassword*:

|*pstrUserName*|*pstrPassword*|FTP sunucusuna gönderilen kullanıcı adı|FTP sunucusuna gönderilen parola|
|--------------------|--------------------|---------------------------------|---------------------------------|
|NULL veya ""|NULL veya ""|"anonim"|Kullanıcının e-posta adı|
|BOŞ olmayan bir dize|NULL veya ""|*pstrUserName*|" "|
|NULL|BOŞ olmayan bir dize|HATA|HATA||
|BOŞ olmayan bir dize|BOŞ olmayan bir dize|*pstrUserName*|*pstrPassword*|

*nbağlantı noktası*<br/>
Sunucu üzerinde kullanılacak TCP/IP bağlantı noktasını tanımlayan bir sayı.

*bPassive*<br/>
Bu FTP oturumu için pasif veya etkin modunu belirtir. TRUE olarak ayarlanırsa, Win32 API kümelerini `dwFlag` INTERNET_FLAG_PASSIVE için.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir [CFtpConnection](../../mfc/reference/cftpconnection-class.md) nesne. Oluşturulan inceleyerek çağrı başarısız olursa hatanın nedenini belirlemek [Cınternetexception](../../mfc/reference/cinternetexception-class.md) nesne.

### <a name="remarks"></a>Açıklamalar

`GetFtpConnection` bir FTP sunucusuna bağlanır ve oluşturur ve bir işaretçi döndüren bir `CFTPConnection` nesne. Sunucudaki belirli herhangi bir işlem gerçekleştirmez. Örneğin, okumak veya dosyalara yazmak istiyorsanız, bu işlemleri ayrı adımları gerçekleştirmeniz gerekir. Sınıfları görmek [CFtpConnection](../../mfc/reference/cftpconnection-class.md) ve [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) dosyalarını aramaya hakkında daha fazla bilgi için dosyaları açma ve okuma ya da dosyalara yazma. Makaleye göz atın [Winınet'in Internet programlama](../../mfc/win32-internet-extensions-wininet.md) ortak FTP bağlantı görevleri gerçekleştirme adımları için.

### <a name="example"></a>Örnek

Örneğin bakın [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md).

## <a name="getgopherconnection"></a>  CInternetSession::GetGopherConnection

Yeni bir gopher bağlantı kurmak ve işaretçi almak için bu üye işlevi çağrısı bir `CGopherConnection` nesne.

```cpp
CGopherConnection* GetGopherConnection(
    LPCTSTR pstrServer,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```

### <a name="parameters"></a>Parametreler

*pstrServer*<br/>
Gopher sunucu adını içeren bir dize işaretçisi.

*pstrUserName*<br/>
Kullanıcı adını içeren bir dize işaretçisi.

*pstrPassword*<br/>
Erişim parola içeren bir dize işaretçisi.

*nbağlantı noktası*<br/>
Sunucu üzerinde kullanılacak TCP/IP bağlantı noktasını tanımlayan bir sayı.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) nesne. Oluşturulan inceleyerek çağrı başarısız olursa hatanın nedenini belirlemek [Cınternetexception](../../mfc/reference/cinternetexception-class.md) nesne.

### <a name="remarks"></a>Açıklamalar

`GetGopherConnection` bir gopher sunucusuna bağlanır ve oluşturur ve bir işaretçi döndüren bir `CGopherConnection` nesne. Sunucudaki belirli herhangi bir işlem gerçekleştirmez. Örneğin, verileri okuma veya yazma yapmak istiyorsanız, bu işlemleri ayrı adımları gerçekleştirmeniz gerekir. Sınıfları görmek [CGopherConnection](../../mfc/reference/cgopherconnection-class.md), [CGopherFile](../../mfc/reference/cgopherfile-class.md), ve [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) dosyalarını aramaya hakkında daha fazla bilgi için dosyaları açma ve okuma ya da dosyalara yazma. Üye işlevi bir FTP sitesi gözatma hakkında daha fazla bilgi için bkz. [OpenURL](#openurl). Makaleye göz atın [Winınet'in Internet programlama](../../mfc/win32-internet-extensions-wininet.md) ortak gopher bağlantı görevleri gerçekleştirme adımları için.

## <a name="gethttpconnection"></a>  CInternetSession::GetHttpConnection

Bir HTTP bağlantısı kurmak ve işaretçi almak için bu üye işlevi çağrısı bir `CHttpConnection` nesne.

```cpp
CHttpConnection* GetHttpConnection(
    LPCTSTR pstrServer,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL);

CHttpConnection* GetHttpConnection(
    LPCTSTR pstrServer,
    DWORD dwFlags,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL);
```

### <a name="parameters"></a>Parametreler

*pstrServer*<br/>
HTTP sunucu adını içeren bir dize işaretçisi.

*nbağlantı noktası*<br/>
Sunucu üzerinde kullanılacak TCP/IP bağlantı noktasını tanımlayan bir sayı.

*pstrUserName*<br/>
Kullanıcı adını içeren bir dize işaretçisi.

*pstrPassword*<br/>
Erişim parola içeren bir dize işaretçisi.

*CertOpenStore*<br/>
Herhangi bir birleşimini `INTERNET_FLAG_*` bayrakları. Bölümündeki tabloya bakın **açıklamalar** bölümünü [CHttpConnection::OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest) açıklamasını *CertOpenStore* değerleri.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir [CHttpConnection](../../mfc/reference/chttpconnection-class.md) nesne. Oluşturulan inceleyerek çağrı başarısız olursa hatanın nedenini belirlemek [Cınternetexception](../../mfc/reference/cinternetexception-class.md) nesne.

### <a name="remarks"></a>Açıklamalar

`GetHttpConnection` bir HTTP sunucusuna bağlanır ve oluşturur ve bir işaretçi döndüren bir `CHttpConnection` nesne. Sunucudaki belirli herhangi bir işlem gerçekleştirmez. Örneğin, bir HTTP üst bilgisi sorgulamak istiyorsanız, bu işlemi ayrı bir adım gerçekleştirmeniz gerekir. Sınıfları görmek [CHttpConnection](../../mfc/reference/chttpconnection-class.md) ve [CHttpFile](../../mfc/reference/chttpfile-class.md) HTTP sunucusuyla bir bağlantı kullanarak gerçekleştirebileceğiniz işlemleri hakkında bilgi için. Üye işlevi bir HTTP site gözatma hakkında daha fazla bilgi için bkz. [OpenURL](#openurl). Makaleye göz atın [Winınet'in Internet programlama](../../mfc/win32-internet-extensions-wininet.md) ortak HTTP bağlantı görevleri gerçekleştirme adımları için.

## <a name="onstatuscallback"></a>  CInternetSession::OnStatusCallback

Bu üye işlevi durum geri çağırması etkin olduğunda ve bir işlem beklemede durumu güncelleştirmek için framework tarafından çağırılır.

```cpp
virtual void OnStatusCallback(
    DWORD_PTR dwContext,
    DWORD dwInternetStatus,
    LPVOID lpvStatusInformation,
    DWORD dwStatusInformationLength);
```

### <a name="parameters"></a>Parametreler

*dwContext*<br/>
Uygulama tarafından sağlanan içerik değeri.

*dwInternetStatus*<br/>
Geri çağırma neden yapıldığı gösteren bir durum kodu. Bkz: **açıklamalar** için olası değerler tablosu.

*lpvStatusInformation*<br/>
Bu geri çağırma için testlerinizle ilgili olabilecek bilgilere içeren arabellek için işaretçi.

*dwStatusInformationLength*<br/>
Boyutu *lpvStatusInformation*.

### <a name="remarks"></a>Açıklamalar

İlk çağırmalıdır [EnableStatusCallback](#enablestatuscallback) durum geri çağırması yararlanmak için.

*DwInternetStatus* parametresi gerçekleştirilmekte olan işlemin gösterir ve hangi içeriğini belirleyen *lpvStatusInformation* olacaktır. *dwStatusInformationLength* dahil veri uzunluğunu gösterir *lpvStatusInformation*. Aşağıdaki durum değerleri *dwInternetStatus* şu şekilde tanımlanır:

|Değer|Açıklama|
|-----------|-------------|
|INTERNET_STATUS_RESOLVING_NAME|IP adresi yer alan adının bakarak *lpvStatusInformation*.|
|INTERNET_STATUS_NAME_RESOLVED|Yer alan adı, IP adresi başarıyla bulundu *lpvStatusInformation*.|
|INTERNET_STATUS_CONNECTING_TO_SERVER|Yuva adresine bağlanan ([SOCKADDR](../../mfc/reference/sockaddr-structure.md)) işaret ettiği *lpvStatusInformation*.|
|INTERNET_STATUS_CONNECTED_TO_SERVER|İşaret ettiği yuva adresine (SOCKADDR) başarıyla bağlandı *lpvStatusInformation*.|
|INTERNET_STATUS_SENDING_REQUEST|Bilgi isteği sunucuya gönderiliyor. *LpvStatusInformation* parametredir NULL.|
|INTERNET_STATUS_ REQUEST_SENT|Sunucuya bilgi isteği gönderildi. *LpvStatusInformation* parametredir NULL.|
|INTERNET_STATUS_RECEIVING_RESPONSE|Sunucunun bir istek için yanıt vermesi bekleniyor. *LpvStatusInformation* parametredir NULL.|
|INTERNET_STATUS_RESPONSE_RECEIVED|Başarıyla sunucusundan bir yanıt aldı. *LpvStatusInformation* parametredir NULL.|
|INTERNET_STATUS_CLOSING_CONNECTION|Sunucuya bağlantı kesiliyor. *LpvStatusInformation* parametredir NULL.|
|INTERNET_STATUS_CONNECTION_CLOSED|Sunucu bağlantısı başarıyla kapatıldı. *LpvStatusInformation* parametredir NULL.|
|INTERNET_STATUS_HANDLE_CREATED|Win32 API işlev tarafından kullanılan [InternetConnect](/windows/desktop/api/wininet/nf-wininet-internetconnecta) yeni işleyici oluşturduğunu göstermek için. Bu uygulama arama Win32 işlevini sağlar [InternetCloseHandle](/windows/desktop/api/wininet/nf-wininet-internetclosehandle) Bağlan çok uzun sürüyorsa, başka bir iş parçacığından. Windows SDKfor, bu işlevler hakkında daha fazla bilgi.|
|INTERNET_STATUS_HANDLE_CLOSING|Bu işleyici değeri başarıyla sonlandırıldı.|

Durumu geri çağırma yordamı gerçekleştirilmeden önce bazı eylemler zorunlu tutmak için bu üye işlevini geçersiz kılar.

> [!NOTE]
> Durum geri çağırmaları iş parçacığı durumu koruması gerekir. MFC içinde paylaşılan bir kitaplık kullanıyorsanız, geçersiz kılma başlangıcına aşağıdaki satırı ekleyin:

[!code-cpp[NVC_MFCHtmlHttp#8](../../mfc/reference/codesnippet/cpp/cinternetsession-class_1.cpp)]

Zaman uyumsuz işlemler hakkında daha fazla bilgi için bkz [Internet ilk adımlar: WinINet](../../mfc/wininet-basics.md).

## <a name="openurl"></a>  CInternetSession::OpenURL

Bu üye işlevi, belirtilen istek için HTTP sunucusu gönderip ek RFC822 belirtmek istemci izin MIME veya birlikte bir istek göndermek için HTTP üst bilgilerini çağırın.

```cpp
CStdioFile* OpenURL(
    LPCTSTR pstrURL,
    DWORD_PTR dwContext = 1,
    DWORD dwFlags = INTERNET_FLAG_TRANSFER_ASCII,
    LPCTSTR pstrHeaders = NULL,
    DWORD dwHeadersLength = 0);
```

### <a name="parameters"></a>Parametreler

*pstrURL*<br/>
Okumanın başlatılacağı URL adı için bir işaretçi. Yalnızca URL'lere dosya ile başlayan:, ftp:, gopher:, veya http: desteklenir. Varsa onaylar *pstrURL* null.

*dwContext*<br/>
Geri döndürülen tutamacın ile uygulama tanımlı bir değer geçirildi.

*CertOpenStore*<br/>
Bu bağlantı ne yapılacağını tanımlayan bayraklar. Bkz: **açıklamalar** geçerli bayrakları hakkında daha fazla bilgi. Geçerli bayraklar:

- Varsayılan INTERNET_FLAG_TRANSFER_ASCII. Dosya ASCII metni olarak aktarın.

- INTERNET_FLAG_TRANSFER_BINARY aktarım dosyası bir ikili dosya olarak.

- INTERNET_FLAG_RELOAD veri alma hattan bile yerel olarak önbelleğe alınır.

- INTERNET_FLAG_DONT_CACHE önbelleğe almaz verileri yerel olarak veya herhangi bir ağ geçidi.

- INTERNET_FLAG_SECURE bu bayrağı yalnızca HTTP istekleri için geçerlidir. Güvenli Yuva Katmanı veya yüzdesi Tel üzerinde güvenli işlemler istekleri

- Sunucu tarafından oluşturulan yeni istekler için var olan bağlantıları INTERNET_OPEN_FLAG_USE_EXISTING_CONNECT gerçekleştirilemiyorsa yeniden `OpenUrl` her bağlantı isteği için yeni bir oturumu oluşturmak yerine.

- INTERNET_FLAG_PASSIVE bir FTP sitesi için kullanılır. Pasif FTP semantiğini kullanıyor. İle kullanılan [Cınternetconnection](../../mfc/reference/cinternetconnection-class.md) , `OpenURL`.

*pstrHeaders*<br/>
HTTP sunucusuna gönderilmesi gereken üstbilgileri içeren bir dize işaretçisi.

*dwHeadersLength*<br/>
Ek üst karakter cinsinden uzunluğu. Bu,-1 L ise ve *pstrHeaders* NULL olmayan, ise *pstrHeaders* sona sıfır olmalıdır ve uzunluğu hesaplanan kabul edilir.

### <a name="return-value"></a>Dönüş Değeri

FTP, GOPHER, HTTP ve dosya türü Internet Hizmetleri için bir dosya tanıtıcısını döndürür. Ayrıştırma işlemi başarısız olursa NULL döndürür.

İşaretçiyi, `OpenURL` döndürür bağlıdır *pstrURL*ın hizmetin türü. Aşağıdaki tabloda olası işaretçileri gösterilmiştir `OpenURL` döndürebilir.

|URL türü|Döndürür|
|--------------|-------------|
|File://|`CStdioFile*`|
|http://|`CHttpFile*`|
|Gopher://|`CGopherFile*`|
|FTP: / /|`CInternetFile*`|

### <a name="remarks"></a>Açıklamalar

Parametre *CertOpenStore* INTERNET_FLAG_TRANSFER_ASCII veya INTERNET_FLAG_TRANSFER_BINARY ancak ikisini birden içermelidir. Kalan bayrak bit düzeyinde ile birleştirilebilir **veya** işleci ( **&#124;**).

`OpenURL`, Win32 işlevini sarmalayan `InternetOpenURL`, yalnızca indiriliyor, alma ve bir Internet sunucusundan verileri okumasını sağlar. `OpenURL` Hayır gerektirir böylece uzak bir konumdaki hiçbir dosya işlenmesine izin verir. [Cınternetconnection](../../mfc/reference/cinternetconnection-class.md) nesne.

Bağlantıya özgü kullanmak için (diğer bir deyişle, protokole özgü) işlevleri, bir dosyaya yazmak gibi oturum açın, ardından belirli bir bağlantı türünü açın, ardından gerekir istenen modda bir dosyayı açmak için bu bağlantıyı kullanın. Bkz: `CInternetConnection` bağlantıya özgü işlevleri hakkında daha fazla bilgi.

## <a name="operator_hinternet"></a>  CInternetSession::operator HINTERNET

Windows tanıtıcı için geçerli Internet oturumu almak için bu işleci kullanın.

```cpp
operator HINTERNET() const;
```

## <a name="setcookie"></a>  CInternetSession::SetCookie

Belirtilen URL için bir tanımlama bilgisi ayarlar.

```cpp
static BOOL SetCookie(
    LPCTSTR pstrUrl,
    LPCTSTR pstrCookieName,
    LPCTSTR pstrCookieData);
```

### <a name="parameters"></a>Parametreler

*pstrUrl*<br/>
Tanımlama bilgisi ayarlanmalıdır URL'sini belirtir bir null ile sonlandırılmış dizeye bir işaretçi.

*pstrCookieName*<br/>
Tanımlama bilgisinin adını içeren bir dize işaretçisi.

*pstrCookieData*<br/>
URL ile ilişkilendirilecek gerçek dize verileri içeren bir dize işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa TRUE veya FALSE döndürür. Söz konusu hata kodunu almak için çağırın `GetLastError.`

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışı uygulayan [InternetSetCookie](/windows/desktop/api/wininet/nf-wininet-internetsetcookiea)Windows SDK içinde açıklandığı gibi.

## <a name="setoption"></a>  CInternetSession::SetOption

Internet oturumu için seçeneklerini ayarlamak için bu üye işlevini çağırın.

```cpp
BOOL SetOption(
    DWORD dwOption,
    LPVOID lpBuffer,
    DWORD dwBufferLength,
    DWORD dwFlags = 0);

BOOL SetOption(
    DWORD dwOption,
    DWORD dwValue,
    DWORD dwFlags = 0);
```

### <a name="parameters"></a>Parametreler

*dwOption*<br/>
Ayarlanacak Internet seçeneği. Bkz: [seçeneği bayrakları](/windows/desktop/WinInet/option-flags) içinde Windows SDKfor olası seçeneklerin bir listesi.

*lpBuffer*<br/>
Seçenek ayarı içeren bir arabelleği.

*dwBufferLength*<br/>
Uzunluğunu *lpBuffer* veya boyutunu *dwValue*.

*dwValue*<br/>
Seçenek ayarları içeren bir DWORD.

*CertOpenStore*<br/>
Çeşitli önbellek seçeneklerini gösterir. Varsayılan değer 0 olarak ayarlanır. Olası değerler şunlardır:

- INTERNET_FLAG_DONT_CACHE önbelleğe almaz verileri yerel olarak veya herhangi bir ağ geçidi sunucusu.

- INTERNET_FLAG_OFFLINE indirme işlemleri yalnızca kalıcı önbellek aracılığıyla karşılanır. Öğeyi önbellekte mevcut değilse, uygun hata kodu döndürülür. Bu bayrak bit düzeyinde ile birleştirilebilir **veya** ( **&#124;**) işleci.

### <a name="return-value"></a>Dönüş Değeri

İşlem başarılı olursa TRUE değeri döndürülür. Bir hata oluştu, FALSE değeri döndürülür. Çağrı başarısız olursa, Win32 işlevini [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) hatanın nedenini belirlemek için çağrılabilir.

## <a name="see-also"></a>Ayrıca Bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CInternetConnection Sınıfı](../../mfc/reference/cinternetconnection-class.md)<br/>
[CHttpConnection Sınıfı](../../mfc/reference/chttpconnection-class.md)<br/>
[CFtpConnection Sınıfı](../../mfc/reference/cftpconnection-class.md)<br/>
[CGopherConnection Sınıfı](../../mfc/reference/cgopherconnection-class.md)
