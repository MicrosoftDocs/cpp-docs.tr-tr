---
title: CInternetSession Sınıfı
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
ms.openlocfilehash: ddd7ca6676805e6de1b7afb5ebc77733701dfef9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372389"
---
# <a name="cinternetsession-class"></a>CInternetSession Sınıfı

Tek veya birkaç eşzamanlı Internet oturumu oluşturur ve başlatılmasını sağlar ve gerekirse bir proxy sunucusuyla bağlantınızı açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
class CInternetSession : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CinternetSession::CinternetSession](#cinternetsession)|Bir `CInternetSession` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CInternetSession::Kapat](#close)|Internet oturumu sonlandırıldığında Internet bağlantısını kapatır.|
|[CInternetSession::EnableStatusCallback](#enablestatuscallback)|Durum geri arama yordamı kurar.|
|[CInternetSession::GetContext](#getcontext)|Internet oturumu sonlandırıldığında Internet bağlantısını kapatır.|
|[CinternetSession::GetCookie](#getcookie)|Belirtilen URL ve tüm üst URL'leri için çerezleri döndürür.|
|[CinternetSession::GetCookieLength](#getcookielength)|Arabellekte depolanan çerezin uzunluğunu belirten değişkeni alır.|
|[CInternetSession::GetFtpConnection](#getftpconnection)|Bir sunucuyla FTP oturumu açar. Kullanıcıda oturum açar.|
|[CInternetSession::GetGopherConnection](#getgopherconnection)|Bağlantı açmaya çalışan bir uygulama için bir gopher sunucusu açar.|
|[CinternetSession::GetHttpConnection](#gethttpconnection)|Bağlantı açmaya çalışan bir uygulama için bir HTTP sunucusu açar.|
|[CInternetSession::OnStatusCallback](#onstatuscallback)|Durum geri araması etkinleştirildiğinde bir işlemin durumunu güncelleştirir.|
|[CInternetSession::OpenURL](#openurl)|Ayrışır ve bir URL açar.|
|[CInternetSession::SetCookie](#setcookie)|Belirtilen URL için bir çerez ayarlar.|
|[CInternetSession::SetOption](#setoption)|Internet oturumu için seçenekler ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CInternetSession::operatör HINTERNET](#operator_hinternet)|Geçerli Internet oturumunun tutamacı.|

## <a name="remarks"></a>Açıklamalar

İnternet bağlantınızın bir uygulama süresince korunması gerekiyorsa, `CInternetSession` [CWinApp](../../mfc/reference/cwinapp-class.md)sınıfının bir üyesini oluşturabilirsiniz.

Bir Internet oturumu oluşturduktan sonra [OpenURL'yi](#openurl)arayabilirsiniz. `CInternetSession`sonra global fonksiyon [AfxParseURL](internet-url-parsing-globals.md#afxparseurl)çağırarak sizin için URL parses. Protokol türüne bakılmaksızın, `CInternetSession` URL'yi yorumlar ve sizin için yönetir. URL kaynağı "file://" ile tanımlanan yerel dosyalar için istekleriişleyebilir. `OpenURL`geçtiğin ad yerel bir dosyaysa, işaretçiyi [CStdioFile](../../mfc/reference/cstdiofile-class.md) nesnesine döndürür.

Bir Internet sunucusunda bir URL'yi kullanarak `OpenURL`açarsanız, sitedeki bilgileri okuyabilirsiniz. Sunucuda bulunan dosyalarda hizmete özgü (örneğin, HTTP, FTP veya gopher) eylemler gerçekleştirmek istiyorsanız, bu sunucuyla uygun bağlantıyı kurmanız gerekir. Belirli bir hizmete doğrudan bağlantı açmak için aşağıdaki üye işlevlerden birini kullanın:

- [GetGopherConnection](#getgopherconnection) bir gopher hizmetine bağlantı açmak için.

- Bir HTTP hizmetine bağlantı açmak için [GetHttpConnection.](#gethttpconnection)

- Bir FTP hizmetine bağlantı açmak için [FtpConnection'ı alın.](#getftpconnection)

[SetOption,](#setoption) zaman zaman ları, yeniden deneme sayısı ve benzeri oturumunuzu sorgu seçeneklerine ayarlamanızı sağlar.

`CInternetSession`üye işlevler [SetCookie](#setcookie), [GetCookie](#getcookie)ve [GetCookieLength,](#getcookielength) sunucuların ve komut dosyalarının istemci iş istasyonu hakkında durum bilgilerini koruduğu bir Win32 çerez veritabanını yönetmek için araçlar sağlar.

Temel Internet programlama görevleri hakkında daha fazla bilgi için, makale [Internet İlk Adımlar bakın: WinInet](../../mfc/wininet-basics.md). MFC WinInet sınıflarını kullanma hakkında genel bilgi için [WinInet ile Internet Programlama](../../mfc/win32-internet-extensions-wininet.md)makalesine bakın.

> [!NOTE]
> `CInternetSession`desteklenmeyen hizmet türleri için bir [AfxThrowNotSupportedException](exception-processing.md#afxthrownotsupportedexception) atar. Şu anda yalnızca aşağıdaki hizmet türleri desteklenir: FTP, HTTP, gopher ve dosya.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)<br/>
&nbsp;&nbsp;&nbsp;&nbsp;`CInternetSession`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxinet.h

## <a name="cinternetsessioncinternetsession"></a><a name="cinternetsession"></a>CinternetSession::CinternetSession

Bir `CInternetSession` nesne oluşturulduğunda bu üye işlev çağrılır.

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
Internet işlevlerini çağıran uygulama veya varlığın adını tanımlayan bir dize işaretçisi (örneğin, "Microsoft Internet Browser"). *pstrAgent* NULL (varsayılan) ise, çerçeve, bir uygulamanın adını içeren geçersiz bir dize döndüren global işlev [AfxGetAppName'yi](application-information-and-management.md#afxgetappname)çağırır. Bazı protokoller, sunucuya uygulamanızı tanımlamak için bu dizeyi kullanır.

*dwBağlam*<br/>
İşlem için bağlam tanımlayıcısı. *dwContext,* CInternetSession tarafından döndürülen operasyonun durum bilgilerini [tanımlar::OnStatusCallback](#onstatuscallback). Varsayılan değer 1 olarak ayarlanır; ancak, işlem için açıkça belirli bir bağlam kimliği atayabilirsiniz. Nesne ve yaptığı herhangi bir çalışma bu bağlam kimliği ile ilişkilendirilecektir.

*dwAccessType*<br/>
Gereken erişim türü. Bunlardan biri tam olarak sağlanmış olabilecek geçerli değerler şunlardır:

- INTERNET_OPEN_TYPE_PRECONFIG Kayıt defterinde önceden yapılandırılmış ayarları kullanarak bağlanın. Bu erişim türü varsayılan olarak ayarlanır. Bir TIS proxy üzerinden bağlanmak için, bu değere *dwAccessType* ayarlayın; daha sonra kayıt defterini uygun şekilde ayarlarsınız.

- INTERNET_OPEN_TYPE_DIRECT Doğrudan Internet'e bağlanın.

- INTERNET_OPEN_TYPE_PROXY Cern proxy ile bağlanın.

Farklı yakınlık türlerine bağlanma hakkında daha fazla bilgi [için, Tipik FTP İstemci Uygulamasındaki Adımlar'a](../../mfc/steps-in-a-typical-ftp-client-application.md)bakın.

*pstrProxyName*<br/>
*dwAccessType* INTERNET_OPEN_TYPE_PROXY olarak ayarlanmışsa tercih edilen CERN proxy adı. Varsayılan değer NULL'dur.

*pstrProxyBypass*<br/>
İsteğe bağlı sunucu adresleri listesini içeren bir dize işaretçisi. Proxy erişimi kullanırken bu adresler atlanabilir. NULL değeri sağlanırsa, bypass listesi kayıt defterinden okunur. Bu parametre yalnızca *dwAccessType* INTERNET_OPEN_TYPE_PROXY ayarlanırsa anlamlıdır.

*Dwflags*<br/>
Çeşitli önbelleğe alma seçeneklerini gösterir. Varsayılan değer 0 olarak ayarlanır. Olası değerler şöyledir:

- INTERNET_FLAG_DONT_CACHE Verileri yerel olarak veya herhangi bir ağ geçidi sunucusunda önbelleğe alma.

- INTERNET_FLAG_OFFLINE İndirme işlemleri yalnızca kalıcı önbellek aracılığıyla karşılanır. Öğe önbellekte yoksa, uygun bir hata kodu döndürülür. Bu bayrak bitwise **OR** ( **&#124;**) işleci ile birleştirilebilir.

### <a name="remarks"></a>Açıklamalar

`CInternetSession`bir uygulama tarafından çağrılan ilk Internet işlevidir. Dahili veri yapılarını başlatır ve uygulamadan gelecek aramalar için hazırlar.

Internet bağlantısı açılamazsa, `CInternetSession` [AfxThrowInternetException](internet-url-parsing-globals.md#afxthrowinternetexception)atar.

### <a name="example"></a>Örnek

[CFtpFileFind](../../mfc/reference/cftpfilefind-class.md)için örneğe bakın.

## <a name="cinternetsessionclose"></a><a name="close"></a>CInternetSession::Kapat

Uygulamanız `CInternetSession` nesneyi kullanarak tamamlandığında bu üye işlevi arayın.

```cpp
virtual void Close();
```

### <a name="example"></a>Örnek

[CFtpFileFind](../../mfc/reference/cftpfilefind-class.md)için örneğe bakın.

## <a name="cinternetsessionenablestatuscallback"></a><a name="enablestatuscallback"></a>CInternetSession::EnableStatusCallback

Durum geri aramasını etkinleştirmek için bu üye işlevini arayın.

```cpp
BOOL EnableStatusCallback(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parametreler

*bEtkinleştir*<br/>
Geri aramanın etkin veya devre dışı bırakıldığını belirtir. Varsayılan TRUE'dur.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0. Arama başarısız olursa, atılan [CInternetException](../../mfc/reference/cinternetexception-class.md) nesnesini inceleyerek hatanın nedenini belirleyin.

### <a name="remarks"></a>Açıklamalar

Durum geri aramasını işlerken, uygulamanın durum çubuğunda işlemin ilerlemesi (adı netme, sunucuya bağlanma vb.) durumu sağlayabilirsiniz. Operasyon durumunun görüntülenmesi özellikle uzun süreli bir işlem sırasında tercih edilir.

Geri aramalar isteğin işlenmesi sırasında oluştuğundan, uygulamanın ağdaki veri veri girişinin bozulmasını önlemek için geri aramada mümkün olduğunca az zaman harcaması gerekir. Örneğin, bir geri arama da bir iletişim kutusu koymak sunucu isteği sonlandırır böyle uzun bir işlem olabilir.

Durum geri araması, bekleyen geri aramalar olduğu sürece kaldırılamaz.

Herhangi bir işlemi eşzamanlı olarak işlemek için, kendi iş parçacığınızı oluşturmanız veya MFC olmadan WinInet işlevlerini kullanmanız gerekir.

## <a name="cinternetsessiongetcontext"></a><a name="getcontext"></a>CInternetSession::GetContext

Belirli bir uygulama oturumuiçin bağlam değerini almak için bu üye işlevi arayın.

```cpp
DWORD_PTR GetContext() const;
```

### <a name="return-value"></a>Dönüş Değeri

Uygulama tanımlı bağlam Tanımlayıcısı.

### <a name="remarks"></a>Açıklamalar

[OnStatusCallback,](#onstatuscallback) belirli bir `GetContext` uygulamanın durumunu bildirmek için döndürülen bağlam kimliğini kullanır. Örneğin, bir kullanıcı durum bilgilerini döndüren bir Internet isteğini etkinleştirdiğinde, durum geri araması söz konusu isteğin durumunu bildirmek için bağlam kimliğini kullanır. Kullanıcı, her ikisi de durum bilgilerini döndüren `OnStatusCallback` iki ayrı Internet isteklerini etkinleştirirse, ilgili istekleriyle ilgili durumu döndürmek için bağlam tanımlayıcılarını kullanır. Sonuç olarak, bağlam tanımlayıcısı tüm durum geri arama işlemleri için kullanılır ve oturum sona erene kadar oturumla ilişkilidir.

Eşzamanlı işlemler hakkında daha fazla bilgi için [Internet First Steps: WinInet](../../mfc/wininet-basics.md)makalesine bakın.

## <a name="cinternetsessiongetcookie"></a><a name="getcookie"></a>CinternetSession::GetCookie

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 işlevi [InternetGetCookie'nin](/windows/win32/api/wininet/nf-wininet-internetgetcookiew)davranışını uygular.

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
URL içeren bir dize için bir işaretçi.

*pstrCookieName*<br/>
Belirtilen URL için almak için çerez adını içeren bir dize için bir işaretçi.

*pstrCookieData*<br/>
İlk aşırı yüklemede, çerez verilerini alan arabelleğenin adresini içeren bir dize işaretçisi. Bu değer NULL olabilir. İkinci aşırı yüklemede, çerez verilerini almak için [cstring](../../atl-mfc-shared/reference/cstringt-class.md) nesnesine bir başvuru.

*dwBufLen*<br/>
*pstrCookieData* arabelleği boyutunu belirten değişken. İşlev başarılı olursa, arabellek *pstrCookieData* arabelleği kopyalanan veri miktarını alır. *pstrCookieData* NULL ise, bu parametre tüm çerez verilerini kopyalamak için gerekli arabellek boyutunu belirten bir değer alır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı ysa TRUE'yı veya başka türlü FALSE'u döndürür. Arama başarısız olursa, hatanın nedenini belirlemek için Win32 işlevini [GetLastError'ı](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) arayın. Aşağıdaki hata değerleri uygulanır:

- ERROR_NO_MORE_ITEMS Belirtilen URL ve tüm ebeveynleri için çerez yoktur.

- ERROR_INSUFFICIENT_BUFFER *dwBufLen'de* geçirilen değer tüm çerez verilerini kopyalamak için yeterli değildir. *dwBufLen* döndürülen değer, tüm verileri almak için gerekli arabellek boyutudur.

### <a name="remarks"></a>Açıklamalar

İkinci aşırı yüklemede, MFC çerez verilerini sağlanan `CString` nesneye alır.

## <a name="cinternetsessiongetcookielength"></a><a name="getcookielength"></a>CinternetSession::GetCookieLength

Arabellekte depolanan çerezin uzunluğunu almak için bu üye işlevi arayın.

```cpp
static DWORD GetCookieLength(
    LPCTSTR pstrUrl,
    LPCTSTR pstrCookieName);
```

### <a name="parameters"></a>Parametreler

*pstrUrl*<br/>
URL'yi içeren bir dize için işaretçi

*pstrCookieName*<br/>
Çerez adını içeren bir dize için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Arabellekte depolanan çerezin uzunluğunu gösteren bir DWORD değeri. *PstrCookieName* ile gösterilen adı ile hiçbir çerez varsa Sıfır var.

### <a name="remarks"></a>Açıklamalar

Bu değer [GetCookie](#getcookie)tarafından kullanılır.

## <a name="cinternetsessiongetftpconnection"></a><a name="getftpconnection"></a>CInternetSession::GetFtpConnection

FTP bağlantısı kurmak ve bir `CFtpConnection` nesneye işaretçi almak için bu üye işlevi arayın.

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
FTP sunucu adını içeren bir dize için bir işaretçi.

*pstrUserName*<br/>
Oturum açmak için kullanıcının adını belirten null-sonlandırılan dize işaretçi. NULL ise, varsayılan adsızdır.

*pstrPassword*<br/>
Oturum açmak için kullanılacak parolayı belirten, geçersiz sonlandırılmış bir dize için işaretçi. Hem *pstrPassword* hem de *pstrUserName* NULL ise, varsayılan anonim parola kullanıcının e-posta adıdır. *pstrPassword* NULL (veya boş bir dize) ancak *pstrUserName* NULL değilse, boş bir parola kullanılır. Aşağıdaki *tabloda pstrUserName* ve *pstrPassword*dört olası ayarları için davranış açıklanır:

| *pstrUserName*  | *pstrPassword*  | FTP sunucusuna gönderilen kullanıcı adı | FTP sunucusuna gönderilen parola |
|-----------------|-----------------|-----------------------------|-----------------------------|
|   NULL veya " "   |   NULL veya " "   |         "anonim"         |      Kullanıcının e-posta adı      |
| NULL Olmayan Dize |   NULL veya " "   |       *pstrUserName*        |             " "             |
|      NULL       | NULL Olmayan Dize |            HATA            |            HATA            |
| NULL Olmayan Dize | NULL Olmayan Dize |       *pstrUserName*        |       *pstrPassword*        |

*nPort*<br/>
Sunucuda kullanılacak TCP/IP bağlantı noktasını tanımlayan bir sayı.

*bPasif*<br/>
Bu FTP oturumu için pasif veya etkin modu belirtir. TRUE olarak ayarlanırsa, Win32 `dwFlag` API'sini INTERNET_FLAG_PASSIVE ayarlar.

### <a name="return-value"></a>Dönüş Değeri

[CFtpConnection](../../mfc/reference/cftpconnection-class.md) nesnesine işaretçi. Arama başarısız olursa, atılan [CInternetException](../../mfc/reference/cinternetexception-class.md) nesnesini inceleyerek hatanın nedenini belirleyin.

### <a name="remarks"></a>Açıklamalar

`GetFtpConnection`bir FTP sunucusuna bağlanır ve bir işaretçi `CFTPConnection` oluşturur ve bir nesneye döndürür. Sunucuda belirli bir işlem gerçekleştirmez. Örneğin, dosyaları okumak veya yazmak istiyorsanız, bu işlemleri ayrı adımlar olarak gerçekleştirmeniz gerekir. Dosyaları arama, dosyaları açma ve dosyaları okuma veya yazma hakkında bilgi almak için [CFtpConnection](../../mfc/reference/cftpconnection-class.md) ve [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) sınıflarına bakın. Ortak FTP bağlantı görevlerini gerçekleştirmedeki adımlar için [WinInet ile Internet Programming](../../mfc/win32-internet-extensions-wininet.md) makalesine bakın.

### <a name="example"></a>Örnek

[CFtpFileFind](../../mfc/reference/cftpfilefind-class.md)için örneğe bakın.

## <a name="cinternetsessiongetgopherconnection"></a><a name="getgopherconnection"></a>CInternetSession::GetGopherConnection

Yeni bir gopher bağlantısı kurmak ve bir `CGopherConnection` nesneye işaretçi almak için bu üye işlevi arayın.

```cpp
CGopherConnection* GetGopherConnection(
    LPCTSTR pstrServer,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```

### <a name="parameters"></a>Parametreler

*pstrServer*<br/>
Gopher sunucu adını içeren bir dize için bir işaretçi.

*pstrUserName*<br/>
Kullanıcı adını içeren bir dize için işaretçi.

*pstrPassword*<br/>
Erişim parolasını içeren bir dize için işaretçi.

*nPort*<br/>
Sunucuda kullanılacak TCP/IP bağlantı noktasını tanımlayan bir sayı.

### <a name="return-value"></a>Dönüş Değeri

[CGopherConnection](../../mfc/reference/cgopherconnection-class.md) nesnesine işaretçi. Arama başarısız olursa, atılan [CInternetException](../../mfc/reference/cinternetexception-class.md) nesnesini inceleyerek hatanın nedenini belirleyin.

### <a name="remarks"></a>Açıklamalar

`GetGopherConnection`bir gopher sunucusuna bağlanır ve bir işaretçi `CGopherConnection` oluşturur ve bir nesneye bir işaretçi döndürür. Sunucuda belirli bir işlem gerçekleştirmez. Örneğin, veri okumak veya yazmak istiyorsanız, bu işlemleri ayrı adımlar olarak gerçekleştirmeniz gerekir. [CGopherConnection,](../../mfc/reference/cgopherconnection-class.md) [CGopherFile](../../mfc/reference/cgopherfile-class.md)ve [CGopherFile](../../mfc/reference/cgopherfilefind-class.md) Dosyaları arama, dosya açma ve okuma veya dosyalara yazma hakkında bilgi için cgopherConnection sınıflarına bakın. FTP sitesine göz atma hakkında daha fazla bilgi için [OpenURL](#openurl)üye işlevine bakın. Ortak gopher bağlantı görevlerini gerçekleştirmedeki adımlar için [WinInet ile Internet Programming](../../mfc/win32-internet-extensions-wininet.md) makalesine bakın.

## <a name="cinternetsessiongethttpconnection"></a><a name="gethttpconnection"></a>CinternetSession::GetHttpConnection

Bir HTTP bağlantısı kurmak ve bir `CHttpConnection` nesneye işaretçi almak için bu üye işlevi arayın.

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
HTTP sunucu adını içeren bir dize için bir işaretçi.

*nPort*<br/>
Sunucuda kullanılacak TCP/IP bağlantı noktasını tanımlayan bir sayı.

*pstrUserName*<br/>
Kullanıcı adını içeren bir dize için işaretçi.

*pstrPassword*<br/>
Erişim parolasını içeren bir dize için işaretçi.

*Dwflags*<br/>
Bayrakların `INTERNET_FLAG_*` herhangi bir kombinasyonu. [CHttpConnection'ın](../../mfc/reference/chttpconnection-class.md#openrequest) **Açıklamalar** bölümündeki tabloya *bakın:DwFlags* değerlerinin açıklaması için OpenRequest.

### <a name="return-value"></a>Dönüş Değeri

[CHttpConnection](../../mfc/reference/chttpconnection-class.md) nesnesine işaretçi. Arama başarısız olursa, atılan [CInternetException](../../mfc/reference/cinternetexception-class.md) nesnesini inceleyerek hatanın nedenini belirleyin.

### <a name="remarks"></a>Açıklamalar

`GetHttpConnection`bir HTTP sunucusuna bağlanır ve bir işaretçi `CHttpConnection` oluşturur ve bir nesneye bir işaretçi döndürür. Sunucuda belirli bir işlem gerçekleştirmez. Örneğin, bir HTTP üstbilgisini sorgulamayı planlıyorsanız, bu işlemi ayrı bir adım olarak gerçekleştirmeniz gerekir. Bir HTTP sunucusuna bağlantı kullanarak gerçekleştirebileceğiniz işlemler hakkında bilgi almak için [CHttpConnection](../../mfc/reference/chttpconnection-class.md) ve [CHttpFile](../../mfc/reference/chttpfile-class.md) sınıflarına bakın. Bir HTTP sitesine göz atma hakkında daha fazla bilgi için [OpenURL](#openurl)üye işlevine bakın. Ortak HTTP bağlantı görevlerini gerçekleştirmedeki adımlar için [WinInet ile Internet Programlama](../../mfc/win32-internet-extensions-wininet.md) makalesine bakın.

## <a name="cinternetsessiononstatuscallback"></a><a name="onstatuscallback"></a>CInternetSession::OnStatusCallback

Bu üye işlev, durum geri araması etkinleştirildiğinde ve bir işlem beklemede olduğunda durumu güncelleştirmek için çerçeve tarafından çağrılır.

```cpp
virtual void OnStatusCallback(
    DWORD_PTR dwContext,
    DWORD dwInternetStatus,
    LPVOID lpvStatusInformation,
    DWORD dwStatusInformationLength);
```

### <a name="parameters"></a>Parametreler

*dwBağlam*<br/>
Uygulama tarafından sağlanan bağlam değeri.

*dwİnternetDurum*<br/>
Geri aramanın neden yapıldığını gösteren bir durum kodu. Olası değerler tablosu için **Açıklamalar'a** bakın.

*lpvStatusInformation*<br/>
Bu geri aramayla ilgili bilgileri içeren bir arabelleğe işaretçi.

*dwStatusInformationLength*<br/>
*lpvStatusInformation*boyutu .

### <a name="remarks"></a>Açıklamalar

Durum geri aramalarından yararlanmak için önce [EnableStatusCallback'i](#enablestatuscallback) aramalısınız.

*dwInternetStatus* parametresi, işlemin gerçekleştirilildiğini gösterir ve *lpvStatusInformation'un* içeriğinin ne olacağını belirler. *dwStatusInformationLength* *lpvStatusInformation'da*yer alan verilerin uzunluğunu gösterir. *dwInternetStatus* için aşağıdaki durum değerleri aşağıdaki gibi tanımlanır:

|Değer|Anlamı|
|-----------|-------------|
|INTERNET_STATUS_RESOLVING_NAME|*lpvStatusInformation'da*yer alan ismin IP adresine bakmak.|
|INTERNET_STATUS_NAME_RESOLVED|*LpvStatusInformation'da*yer alan ismin IP adresini başarıyla buldu.|
|INTERNET_STATUS_CONNECTING_TO_SERVER|Soket adresine bağlanma ([SOCKADDR](/windows/win32/winsock/sockaddr-2)) *lpvStatusInformation*tarafından işaret.|
|INTERNET_STATUS_CONNECTED_TO_SERVER|Başarıyla *lpvStatusInformation*tarafından işaret soket adresine (SOCKADDR) bağlı.|
|INTERNET_STATUS_SENDING_REQUEST|Bilgi isteğini sunucuya gönderme. *lpvStatusInformation* parametresi NULL'dur.|
|INTERNET_STATUS_ REQUEST_SENT|Bilgi isteğini başarıyla sunucuya gönderdi. *lpvStatusInformation* parametresi NULL'dur.|
|INTERNET_STATUS_RECEIVING_RESPONSE|Sunucunun bir isteğe yanıt vermesi bekleniyor. *lpvStatusInformation* parametresi NULL'dur.|
|INTERNET_STATUS_RESPONSE_RECEIVED|Sunucudan başarıyla yanıt aldı. *lpvStatusInformation* parametresi NULL'dur.|
|INTERNET_STATUS_CLOSING_CONNECTION|Sunucuya bağlantıyı kapatma. *lpvStatusInformation* parametresi NULL'dur.|
|INTERNET_STATUS_CONNECTION_CLOSED|Sunucuya olan bağlantıyı başarıyla kapattı. *lpvStatusInformation* parametresi NULL'dur.|
|INTERNET_STATUS_HANDLE_CREATED|Win32 API işlevi tarafından kullanılan [InternetConnect,](/windows/win32/api/wininet/nf-wininet-internetconnectw) yeni tanıtıcıyı oluşturduğunu gösterir. Bu, bağlantı çok uzun sürüyorsa uygulamanın Win32 işlevini [internetclosehandle'ı](/windows/win32/api/wininet/nf-wininet-internetclosehandle) başka bir iş parçacığından aramasına olanak tanır. Bu işlevler hakkında daha fazla bilgi için Windows SDK'ya bakın.|
|INTERNET_STATUS_HANDLE_CLOSING|Bu işlem değerini başarıyla sonlandırdı.|

Durum geri arama yordamı gerçekleştirilmeden önce bazı eylem gerektirecek şekilde bu üye işlevi geçersiz kılın.

> [!NOTE]
> Durum geri aramalarının iş parçacığı durumu koruması gerekir. Paylaşılan bir kitaplıkta MFC kullanıyorsanız, geçersiz kılmanızın başına aşağıdaki satırı ekleyin:

[!code-cpp[NVC_MFCHtmlHttp#8](../../mfc/reference/codesnippet/cpp/cinternetsession-class_1.cpp)]

Eşzamanlı işlemler hakkında daha fazla bilgi için [Internet First Steps: WinInet](../../mfc/wininet-basics.md)makalesine bakın.

## <a name="cinternetsessionopenurl"></a><a name="openurl"></a>CInternetSession::OpenURL

Belirtilen isteği HTTP sunucusuna göndermek için bu üye işlevini arayın ve istemcinin istekle birlikte göndermek için ek RFC822, MIME veya HTTP üstbilgi belirtmesine izin verin.

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
Okumaya başlamak için URL'nin adına işaretçi. Yalnızca dosya:, ftp:, gopher:veya http ile başlayan URL'ler desteklenir. *pstrURL* NULL ise ileri sürtüner.

*dwBağlam*<br/>
Geri aramada döndürülen tutamaç ile geçirilen uygulama tanımlı değer.

*Dwflags*<br/>
Bu bağlantının nasıl işleyeceğini açıklayan bayraklar. Geçerli bayraklar hakkında daha fazla bilgi için **Açıklamalar'a** bakın. Geçerli bayraklar şunlardır:

- INTERNET_FLAG_TRANSFER_ASCII Varsayılan. Dosyayı ASCII metni olarak aktarın.

- INTERNET_FLAG_TRANSFER_BINARY Dosyayı ikili dosya olarak aktarın.

- INTERNET_FLAG_RELOAD Yerel olarak önbelleğe alınmış olsa bile, verileri kablodan alın.

- INTERNET_FLAG_DONT_CACHE Verileri yerel olarak veya herhangi bir ağ geçidinde önbelleğe alma.

- INTERNET_FLAG_SECURE Bu bayrak yalnızca HTTP istekleri için geçerlidir. Güvenli Soketler Katmanı veya PCT ile tel üzerinde güvenli işlemler talep eder.

- INTERNET_OPEN_FLAG_USE_EXISTING_CONNECT Mümkünse, her bağlantı isteği için yeni bir `OpenUrl` oturum oluşturmak yerine, sunucuya varolan bağlantıları yeniden kullanın.

- INTERNET_FLAG_PASSIVE FTP sitesi için kullanılır. Pasif FTP semantikkullanır. [CInternetConnection](../../mfc/reference/cinternetconnection-class.md) ile `OpenURL`kullanılır.

*pstrHeaders*<br/>
HTTP sunucusuna gönderilecek üstbilgi içeren bir dize için bir işaretçi.

*dwHeadersUzunluk*<br/>
Ek üstbilginin karakterleri uzunluğunda. Bu -1L ise ve *pstrHeaders* NULL olmayan ise, o zaman *pstrHeaders* sıfır sonlandırıldı ve uzunluğu hesaplanır kabul edilir.

### <a name="return-value"></a>Dönüş Değeri

Yalnızca FTP, GOPHER, HTTP ve FILE türü Internet hizmetleri için bir dosya tanıtıcısı döndürür. Ayrışma başarısız olduysa NULL'u döndürür.

Döndüren `OpenURL` işaretçi *pstrURL'nin*hizmet türüne bağlıdır. Aşağıdaki tabloda olası işaretçilerin `OpenURL` dönebileceği gösterilmektedir.

|URL türü|Döndürür|
|--------------|-------------|
|`file://`|`CStdioFile*`|
|`http://`|`CHttpFile*`|
|`gopher://`|`CGopherFile*`|
|`ftp://`|`CInternetFile*`|

### <a name="remarks"></a>Açıklamalar

*DwFlags* parametresi INTERNET_FLAG_TRANSFER_ASCII veya INTERNET_FLAG_TRANSFER_BINARY içermelidir, ancak her ikisini birden içermemelidir. Kalan bayraklar bitwise **OR** işleci **(&#124;) **ile birleştirilebilir.

`OpenURL`, Win32 işlevini `InternetOpenURL`sarar , yalnızca indirme, alma ve bir Internet sunucusundan veri okuma sağlar. `OpenURL`uzak bir konumda dosya işlemeizine izin verir, bu nedenle [CInternetConnection](../../mfc/reference/cinternetconnection-class.md) nesnesi gerektirmez.

Bir dosyaya yazma gibi bağlantıya özgü (yani protokole özgü) işlevleri kullanmak için bir oturumu açmanız, ardından belirli bir tür bağlantı açmanız ve ardından bu bağlantıyı kullanarak bir dosyayı istenilen modda açmanız gerekir. Bağlantıya özgü işlevler hakkında daha fazla bilgi için bkz. `CInternetConnection`

## <a name="cinternetsessionoperator-hinternet"></a><a name="operator_hinternet"></a>CInternetSession::operatör HINTERNET

Geçerli Internet oturumu için Windows tanıtıcısını almak için bu işleci kullanın.

```cpp
operator HINTERNET() const;
```

## <a name="cinternetsessionsetcookie"></a><a name="setcookie"></a>CInternetSession::SetCookie

Belirtilen URL için bir çerez ayarlar.

```cpp
static BOOL SetCookie(
    LPCTSTR pstrUrl,
    LPCTSTR pstrCookieName,
    LPCTSTR pstrCookieData);
```

### <a name="parameters"></a>Parametreler

*pstrUrl*<br/>
Çerezin ayarlandığı URL'yi belirten, geçersiz sonlandırılmış bir dize için işaretçi.

*pstrCookieName*<br/>
Çerez adını içeren bir dize için bir işaretçi.

*pstrCookieData*<br/>
URL ile ilişkilendirmek için gerçek dize verilerini içeren bir dize işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı ysa TRUE'yı veya başka türlü FALSE'u döndürür. Belirli hata kodunu almak için,`GetLastError.`

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi Win32 iletisi [InternetSetCookie](/windows/win32/api/wininet/nf-wininet-internetsetcookiew)davranışını uygular.

## <a name="cinternetsessionsetoption"></a><a name="setoption"></a>CInternetSession::SetOption

Internet oturumu için seçenekler ayarlamak için bu üye işlevini arayın.

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
Ayarlanan Internet seçeneği. Olası seçeneklerin listesi için Windows SDK'daki [Seçenek Bayrakları'na](/windows/win32/WinInet/option-flags) bakın.

*lpBuffer*<br/>
Seçenek ayarı içeren bir arabellek.

*dwBufferLength*<br/>
*lpBuffer* uzunluğu veya *dwValue*boyutu.

*dwDeğer*<br/>
Seçenek ayarını içeren bir DWORD.

*Dwflags*<br/>
Çeşitli önbelleğe alma seçeneklerini gösterir. Varsayılan değer 0 olarak ayarlanır. Olası değerler şöyledir:

- INTERNET_FLAG_DONT_CACHE Verileri yerel olarak veya herhangi bir ağ geçidi sunucusunda önbelleğe alma.

- INTERNET_FLAG_OFFLINE İndirme işlemleri yalnızca kalıcı önbellek aracılığıyla karşılanır. Öğe önbellekte yoksa, uygun bir hata kodu döndürülür. Bu bayrak bitwise **OR** ( **&#124;**) işleci ile birleştirilebilir.

### <a name="return-value"></a>Dönüş Değeri

İşlem başarılı olduysa, TRUE değeri döndürülür. Bir hata oluştuysa, FALSE değeri döndürülür. Arama başarısız olursa, hatanın nedenini belirlemek için Win32 işlevi [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) çağrılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CInternetConnection Sınıfı](../../mfc/reference/cinternetconnection-class.md)<br/>
[ChttpConnection Sınıfı](../../mfc/reference/chttpconnection-class.md)<br/>
[CFtpConnection Sınıfı](../../mfc/reference/cftpconnection-class.md)<br/>
[CGopherConnection Sınıfı](../../mfc/reference/cgopherconnection-class.md)
