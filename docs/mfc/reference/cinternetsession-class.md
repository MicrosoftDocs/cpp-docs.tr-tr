---
title: CInternetSession sınıfı
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
ms.openlocfilehash: c9b8eaf51820dfcd08c1390c8645978fa403931d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505839"
---
# <a name="cinternetsession-class"></a>CInternetSession sınıfı

Tek veya birkaç eşzamanlı Internet oturumu oluşturur ve başlatır ve gerekirse bir ara sunucu bağlantısını açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
class CInternetSession : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CInternetSession:: CInternetSession](#cinternetsession)|Bir `CInternetSession` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CInternetSession:: Close](#close)|Internet oturumu sonlandırıldığı zaman Internet bağlantısını kapatır.|
|[CInternetSession:: EnableStatusCallback](#enablestatuscallback)|Bir durum geri çağırma yordamı oluşturur.|
|[CInternetSession:: GetContext](#getcontext)|Internet oturumu sonlandırıldığı zaman Internet bağlantısını kapatır.|
|[CInternetSession:: GetCookie](#getcookie)|Belirtilen URL ve tüm üst URL 'Leri için tanımlama bilgilerini döndürür.|
|[CInternetSession:: Getbir ıelength](#getcookielength)|Arabellekte depolanan tanımlama bilgisinin uzunluğunu belirten değişkeni alır.|
|[CInternetSession:: GetFtpConnection](#getftpconnection)|Sunucu ile bir FTP oturumu açar. Kullanıcı günlükleri.|
|[CInternetSession:: GetGopherConnection](#getgopherconnection)|Bir bağlantıyı açmaya çalışan bir uygulama için Gopher sunucusunu açar.|
|[CInternetSession:: GetHttpConnection](#gethttpconnection)|Bir bağlantıyı açmaya çalışan bir uygulama için HTTP sunucusu açar.|
|[CInternetSession:: OnStatusCallback](#onstatuscallback)|Durum geri araması etkinleştirildiğinde bir işlemin durumunu güncelleştirir.|
|[CInternetSession:: OpenURL](#openurl)|Bir URL ayrıştırır ve açar.|
|[CInternetSession:: SetCookie](#setcookie)|Belirtilen URL için bir tanımlama bilgisi ayarlar.|
|[CInternetSession:: SetOption](#setoption)|Internet oturumunun seçeneklerini ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CInternetSession:: operator HıNTERNET](#operator_hinternet)|Geçerli Internet oturumuna yönelik bir tanıtıcı.|

## <a name="remarks"></a>Açıklamalar

Internet bağlantınızın bir uygulama süresince tutulması gerekiyorsa, `CInternetSession` [CWinApp](../../mfc/reference/cwinapp-class.md)sınıfının bir üyesini oluşturabilirsiniz.

Bir Internet oturumu kurduktan sonra [OpenURL](#openurl)'yi çağırabilirsiniz. `CInternetSession`daha sonra, [AfxParseURL](internet-url-parsing-globals.md#afxparseurl)genel işlevini çağırarak URL 'yi sizin için ayrıştırır. Protokol türünden bağımsız olarak, `CInternetSession` URL 'yi Yorumlar ve sizin için yönetir. "File://" URL kaynağıyla tanımlanan yerel dosyalar için istekleri işleyebilir. `OpenURL`, geçirdiğiniz ad yerel bir dosya ise, [CStdioFile](../../mfc/reference/cstdiofile-class.md) nesnesine bir işaretçi döndürür.

Kullanarak `OpenURL`bir Internet sunucusunda bir URL açarsanız, siteden bilgileri okuyabilirsiniz. Sunucuda bulunan dosyalar üzerinde hizmete özgü (örneğin, HTTP, FTP veya Gopher) eylemler gerçekleştirmek istiyorsanız, bu sunucuyla uygun bağlantıyı kurmanız gerekir. Belirli bir hizmete doğrudan belirli bir bağlantı türünü açmak için aşağıdaki üye işlevlerden birini kullanın:

- [GetGopherConnection](#getgopherconnection) bir Gopher hizmetine bağlantı açmak için.

- HTTP hizmetine bir bağlantı açmak için [GetHttpConnection](#gethttpconnection) .

- FTP hizmetine bir bağlantı açmak için [GetFtpConnection](#getftpconnection) .

[SetOption](#setoption) , oturumunuzun, zaman aşımı değerleri, yeniden deneme sayısı gibi sorgu seçeneklerini ayarlamanıza olanak sağlar.

`CInternetSession`[SetCookie](#setcookie), [GetCookie](#getcookie)ve [gettanýmlama ıelength](#getcookielength) üye işlevleri, istemci iş istasyonuyla ilgili durum bilgilerini hangi sunucular ve betikler ile korumakta bir Win32 tanımlama bilgisi veritabanını yönetme araçlarını sağlar.

Temel Internet programlama görevleri hakkında daha fazla bilgi için Internet ilk adımları [makalesine bakın: WinInet](../../mfc/wininet-basics.md). MFC WinInet sınıflarını kullanma hakkında genel bilgi için bkz. [Winınet Ile Internet programlama](../../mfc/win32-internet-extensions-wininet.md)makalesi.

> [!NOTE]
> `CInternetSession`, desteklenmeyen hizmet türleri için bir [AfxThrowNotSupportedException](exception-processing.md#afxthrownotsupportedexception) oluşturur. Şu anda yalnızca aşağıdaki hizmet türleri desteklenir: FTP, HTTP, gopher ve dosya.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)<br/>
&nbsp;&nbsp;&nbsp;&nbsp;`CInternetSession`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFXINET. h

## <a name="cinternetsession"></a>CInternetSession:: CInternetSession

Bu üye işlevi, bir `CInternetSession` nesne oluşturulduğunda çağrılır.

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
Internet işlevlerini çağıran uygulamanın veya varlığın adını tanımlayan bir dize işaretçisi (örneğin, "Microsoft Internet browser"). *PstrAgent* null ise (varsayılan), çerçeve, bir uygulamanın adını içeren null ile sonlandırılmış bir dize döndüren [AfxGetAppName](application-information-and-management.md#afxgetappname)genel işlevini çağırır. Bazı protokoller uygulamanızı sunucuya tanıtmak için bu dizeyi kullanır.

*dwContext*<br/>
İşlemin bağlam tanımlayıcısı. *dwContext* , [CInternetSession:: OnStatusCallback](#onstatuscallback)tarafından döndürülen işlemin durum bilgilerini tanımlar. Varsayılan değer 1 ' e ayarlanır; Ancak, işlem için özel bir bağlam KIMLIĞINI açıkça atayabilirsiniz. Nesne ve onun yaptığı herhangi bir iş, bu bağlam KIMLIĞIYLE ilişkilendirilecektir.

*dwAccessType*<br/>
Gerekli erişim türü. Aşağıda, tam olarak bir tane sağlanabilecek geçerli değerler verilmiştir:

- INTERNET_OPEN_TYPE_PRECONFIG kayıt defterindeki önceden yapılandırılmış ayarları kullanarak bağlanın. Bu erişim türü varsayılan olarak ayarlanır. Bir ara sunucu üzerinden bağlanmak için *dwAccessType* değerini bu değere ayarlayın; ardından kayıt defterini uygun şekilde ayarlarsınız.

- INTERNET_OPEN_TYPE_DIRECT doğrudan Internet 'e bağlanın.

- INTERNET_OPEN_TYPE_PROXY bir CERN proxy üzerinden bağlanır.

Farklı türlerde proxy 'ler ile bağlantı kurma hakkında daha fazla bilgi için bkz. [tipik BIR FTP Istemci uygulamasındaki adımlar](../../mfc/steps-in-a-typical-ftp-client-application.md).

*pstrProxyName*<br/>
*DwAccessType* öğesi INTERNET_OPEN_TYPE_PROXY olarak ayarlandıysa, tercıh edilen CERN proxy 'nin adı. Varsayılan değer NULL.

*pstrProxyBypass*<br/>
Sunucu adreslerinin isteğe bağlı bir listesini içeren bir dize işaretçisi. Bu adresler, proxy erişimi kullanılırken atlanabilir. NULL değer sağlanırsa, atlama listesi kayıt defterinden okunacaktır. Bu parametre yalnızca *dwAccessType* INTERNET_OPEN_TYPE_PROXY olarak ayarlandıysa anlamlıdır.

*dwFlags*<br/>
Çeşitli önbelleğe alma seçeneklerini gösterir. Varsayılan değer 0 ' dır. Olası değerler şöyledir:

- INTERNET_FLAG_DONT_CACHE, yerel olarak veya herhangi bir ağ geçidi sunucusunda verileri önbelleğe almaz.

- INTERNET_FLAG_OFFLINE Indirme işlemleri yalnızca kalıcı önbellek aracılığıyla karşılanır. Öğe önbellekte yoksa, uygun bir hata kodu döndürülür. Bu bayrak, bit düzeyinde **or** ( **&#124;** ) işleciyle birleştirilebilir.

### <a name="remarks"></a>Açıklamalar

`CInternetSession`, bir uygulama tarafından çağrılan ilk Internet işlevidir. İç veri yapılarını başlatır ve bundan sonraki çağrılar için uygulamayı hazırlar.

Internet bağlantısı açılamadığı takdirde, `CInternetSession` bir [AfxThrowInternetException](internet-url-parsing-globals.md#afxthrowinternetexception)oluşturur.

### <a name="example"></a>Örnek

[CFtpFileFind](../../mfc/reference/cftpfilefind-class.md)örneğine bakın.

## <a name="close"></a>CInternetSession:: Close

Uygulamanız `CInternetSession` nesneyi kullanmayı bitirdiğinde Bu üye işlevi çağırın.

```cpp
virtual void Close();
```

### <a name="example"></a>Örnek

[CFtpFileFind](../../mfc/reference/cftpfilefind-class.md)örneğine bakın.

## <a name="enablestatuscallback"></a>CInternetSession:: EnableStatusCallback

Durum geri aramasını etkinleştirmek için bu üye işlevini çağırın.

```cpp
BOOL EnableStatusCallback(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parametreler

*bEnable*<br/>
Geri aramanın etkin veya devre dışı olduğunu belirtir. Varsayılan değer TRUE 'dur.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0. Çağrı başarısız olursa, oluşturulan [CInternetException](../../mfc/reference/cinternetexception-class.md) nesnesini inceleyerek hatanın nedenini saptayın.

### <a name="remarks"></a>Açıklamalar

Durum geri çağırma işlemini gerçekleştirirken, uygulamanın durum çubuğunda işlemin ilerleme durumu (adı çözme, sunucuya bağlanma vb.) hakkında durum sağlayabilirsiniz. İşlem durumunu görüntüleme, özellikle uzun süreli bir işlem sırasında istenir.

İsteğin işlenmesi sırasında geri aramalar yapıldığından, ağ üzerinde veri işleme düşüşünü engellemek için uygulamanın geri aramada mümkün olduğunca az zaman harcaması gerekir. Örneğin, bir geri çağrıda bir iletişim kutusunun yerleştirilmesi, sunucunun isteği sonlandırmakta olduğu uzun bir işlem olabilir.

Geri çağırmalar bekleyen olduğu sürece durum geri çağırması kaldırılamaz.

Herhangi bir işlemi zaman uyumsuz olarak işlemek için kendi iş parçacığını oluşturmanız ya da WinInet işlevlerini MFC olmadan kullanmanız gerekir.

## <a name="getcontext"></a>CInternetSession:: GetContext

Belirli bir uygulama oturumunun bağlam değerini almak için bu üye işlevi çağırın.

```cpp
DWORD_PTR GetContext() const;
```

### <a name="return-value"></a>Dönüş Değeri

Uygulama tanımlı bağlam tanımlayıcısı.

### <a name="remarks"></a>Açıklamalar

[OnStatusCallback](#onstatuscallback) , belirli bir uygulamanın durumunu raporlamak `GetContext` için tarafından döndürülen bağlam kimliğini kullanır. Örneğin, bir kullanıcı durum bilgilerini döndürmeyle ilgili bir Internet isteği etkinleştirdiğinde, durum geri çağırması bu belirli istek üzerindeki durumu raporlamak için bağlam KIMLIĞINI kullanır. Kullanıcı durum bilgilerini döndüren iki ayrı Internet isteğini etkinleştirdiğinde, `OnStatusCallback` karşılık gelen istekleri hakkında durumu döndürmek için bağlam tanımlayıcılarını kullanır. Sonuç olarak, tüm durum geri çağırma işlemleri için bağlam tanımlayıcısı kullanılır ve oturum sonlanana kadar oturum ile ilişkilendirilir.

Zaman uyumsuz işlemler hakkında daha fazla bilgi için Internet ilk [adımları makalesine bakın: WinInet](../../mfc/wininet-basics.md).

## <a name="getcookie"></a>CInternetSession:: GetCookie

Bu üye işlevi, Windows SDK ' de açıklandığı gibi, [InternetGetCookie](/windows/win32/api/wininet/nf-wininet-internetgetcookiew)Win32 işlevinin davranışını uygular.

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
URL 'YI içeren bir dize işaretçisi.

*Pstrtanımlama bilgisi adı*<br/>
Belirtilen URL için alınacak tanımlama bilgisinin adını içeren bir dize işaretçisi.

*Pstrtarif ıedata*<br/>
İlk aşırı yüklemede, tanımlama bilgisi verilerini alan arabelleğin adresini içeren bir dize işaretçisi. Bu değer NULL olabilir. İkinci aşırı yüklemede, tanımlama bilgisi verilerini almak için bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesine başvuru.

*dwBufLen*<br/>
*PSTR, ıedata* arabelleğinin boyutunu belirten değişken. İşlev başarılı olursa, arabellek, *Pstrpişiriedata* arabelleğine kopyalanmış veri miktarını alır. *Pstrcookie ıedata* null ise, bu parametre tüm tanımlama bilgisi verilerini kopyalamak için gereken arabellek boyutunu belirten bir değer alır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa TRUE, aksi takdirde FALSE döndürür. Çağrı başarısız olursa hatanın nedenini öğrenmek için WIN32 [](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) işlevini çağırın. Aşağıdaki hata değerleri geçerlidir:

- ERROR_NO_MORE_ITEMS belirtilen URL ve tüm üst öğeleri için tanımlama bilgisi yok.

- ERROR_INSUFFICIENT_BUFFER *dwBufLen* içinde geçirilen değer tüm tanımlama bilgisi verilerini kopyalamak için yeterli değil. *DwBufLen* içinde döndürülen değer, tüm verileri almak için gereken arabelleğin boyutudur.

### <a name="remarks"></a>Açıklamalar

İkinci aşırı yüklemede, MFC tanımlama bilgisi verilerini sağlanan `CString` nesneye alır.

## <a name="getcookielength"></a>CInternetSession:: Getbir ıelength

Arabellekte depolanan tanımlama bilgisinin uzunluğunu almak için bu üye işlevi çağırın.

```cpp
static DWORD GetCookieLength(
    LPCTSTR pstrUrl,
    LPCTSTR pstrCookieName);
```

### <a name="parameters"></a>Parametreler

*pstrUrl*<br/>
URL içeren bir dizeye yönelik işaretçi

*Pstrtanımlama bilgisi adı*<br/>
Tanımlama bilgisinin adını içeren bir dize işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Arabellekte depolanan tanımlama bilgisinin uzunluğunu gösteren bir DWORD değeri. *Pstrcookie ENAME* ile belirtilen adda bir tanımlama bilgisi yoksa sıfır.

### <a name="remarks"></a>Açıklamalar

Bu değer [GetCookie](#getcookie)tarafından kullanılır.

## <a name="getftpconnection"></a>CInternetSession:: GetFtpConnection

Bir FTP bağlantısı kurmak ve bir `CFtpConnection` nesnenin işaretçisini almak için bu üye işlevi çağırın.

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
FTP sunucu adını içeren bir dize işaretçisi.

*pstrUserName*<br/>
Oturum açmak için kullanıcının adını belirten, null ile sonlandırılmış bir dize işaretçisi. NULL ise, varsayılan olarak anonim olur.

*pstrPassword*<br/>
Oturum açmak için kullanılacak parolayı belirten, null ile sonlandırılmış bir dize işaretçisi. Hem *pstrPassword* hem de *PSTRUSERNAME* null ise, varsayılan Anonim parola kullanıcının e-posta adıdır. *PstrPassword* null (veya boş bir dize) ise, ancak *pstrUserName* null değilse boş bir parola kullanılır. Aşağıdaki tabloda *pstrUserName* ve *pstrPassword*öğesinin dört olası ayarlarının davranışı açıklanmaktadır:

| *pstrUserName*  | *pstrPassword*  | FTP sunucusuna gönderilen Kullanıcı adı | FTP sunucusuna parola gönderildi |
|-----------------|-----------------|-----------------------------|-----------------------------|
|   NULL veya ""   |   NULL veya ""   |         deðeri         |      Kullanıcının e-posta adı      |
| NULL olmayan dize |   NULL veya ""   |       *pstrUserName*        |             " "             |
|      NULL       | NULL olmayan dize |            HATA            |            HATA            |
| NULL olmayan dize | NULL olmayan dize |       *pstrUserName*        |       *pstrPassword*        |

*nPort*<br/>
Sunucuda kullanılacak TCP/IP bağlantı noktasını belirleyen bir sayı.

*Bpasif*<br/>
Bu FTP oturumu için pasif veya etkin modu belirtir. TRUE olarak ayarlanırsa, Win32 API `dwFlag` INTERNET_FLAG_PASSIVE olarak ayarlar.

### <a name="return-value"></a>Dönüş Değeri

[CFtpConnection](../../mfc/reference/cftpconnection-class.md) nesnesine yönelik bir işaretçi. Çağrı başarısız olursa, oluşturulan [CInternetException](../../mfc/reference/cinternetexception-class.md) nesnesini inceleyerek hatanın nedenini saptayın.

### <a name="remarks"></a>Açıklamalar

`GetFtpConnection`bir FTP sunucusuna bağlanır ve bir `CFTPConnection` nesnenin işaretçisini oluşturur ve döndürür. Sunucuda belirli bir işlem gerçekleştirmez. Örneğin, dosyaları okumak veya yazmak istiyorsanız bu işlemleri ayrı adımlar olarak gerçekleştirmeniz gerekir. Dosyaları arama, dosyaları açma ve dosyaları okuma veya yazma hakkında bilgi edinmek için [CFtpConnection](../../mfc/reference/cftpconnection-class.md) ve [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) sınıflarını inceleyin. Ortak FTP bağlantı görevlerini gerçekleştirme adımları için bkz. [Winınet Ile Internet programlama](../../mfc/win32-internet-extensions-wininet.md) makalesi.

### <a name="example"></a>Örnek

[CFtpFileFind](../../mfc/reference/cftpfilefind-class.md)örneğine bakın.

## <a name="getgopherconnection"></a>CInternetSession:: GetGopherConnection

Yeni bir Gopher bağlantısı kurmak ve bir `CGopherConnection` nesnenin işaretçisini almak için bu üye işlevi çağırın.

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
Erişim parolasını içeren bir dize işaretçisi.

*nPort*<br/>
Sunucuda kullanılacak TCP/IP bağlantı noktasını belirleyen bir sayı.

### <a name="return-value"></a>Dönüş Değeri

[CGopherConnection](../../mfc/reference/cgopherconnection-class.md) nesnesine yönelik bir işaretçi. Çağrı başarısız olursa, oluşturulan [CInternetException](../../mfc/reference/cinternetexception-class.md) nesnesini inceleyerek hatanın nedenini saptayın.

### <a name="remarks"></a>Açıklamalar

`GetGopherConnection`Bir gopher sunucusuna bağlanır ve bir `CGopherConnection` nesnenin işaretçisini oluşturur ve döndürür. Sunucuda belirli bir işlem gerçekleştirmez. Örneğin, verileri okumak veya yazmak istiyorsanız, bu işlemleri ayrı adımlar olarak gerçekleştirmeniz gerekir. Dosyaları arama, dosyaları açma ve dosyaları okuma veya yazma hakkında bilgi için bkz. [CGopherConnection](../../mfc/reference/cgopherconnection-class.md), [CGopherFile](../../mfc/reference/cgopherfile-class.md)ve [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) sınıfları. FTP sitesine göz atma hakkında daha fazla bilgi için bkz. [OpenURL](#openurl)üye işlevi. Ortak Gopher bağlantı görevlerini gerçekleştirmeye yönelik adımlar için bkz. [Winınet Ile Internet programlama](../../mfc/win32-internet-extensions-wininet.md) makalesi.

## <a name="gethttpconnection"></a>CInternetSession:: GetHttpConnection

Bir http bağlantısı kurmak ve bir `CHttpConnection` nesnenin işaretçisini almak için bu üye işlevi çağırın.

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

*nPort*<br/>
Sunucuda kullanılacak TCP/IP bağlantı noktasını belirleyen bir sayı.

*pstrUserName*<br/>
Kullanıcı adını içeren bir dize işaretçisi.

*pstrPassword*<br/>
Erişim parolasını içeren bir dize işaretçisi.

*dwFlags*<br/>
`INTERNET_FLAG_*` Bayrakların herhangi bir birleşimi. *DwFlags* değerlerinin açıklaması için [CHttpConnection:: OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest) konusunun **açıklamalar** bölümünde bulunan tabloya bakın.

### <a name="return-value"></a>Dönüş Değeri

[CHttpConnection](../../mfc/reference/chttpconnection-class.md) nesnesine yönelik bir işaretçi. Çağrı başarısız olursa, oluşturulan [CInternetException](../../mfc/reference/cinternetexception-class.md) nesnesini inceleyerek hatanın nedenini saptayın.

### <a name="remarks"></a>Açıklamalar

`GetHttpConnection`bir http sunucusuna bağlanır ve bir `CHttpConnection` nesnenin işaretçisini oluşturur ve döndürür. Sunucuda belirli bir işlem gerçekleştirmez. Örneğin, bir HTTP üst bilgisini sorgulamak istiyorsanız, bu işlemi ayrı bir adım olarak gerçekleştirmeniz gerekir. HTTP sunucusuna bağlantı kullanarak gerçekleştirebileceğiniz işlemler hakkında bilgi için bkz. [CHttpConnection](../../mfc/reference/chttpconnection-class.md) ve [CHttpFile](../../mfc/reference/chttpfile-class.md) sınıfları. Bir HTTP sitesine göz atma hakkında daha fazla bilgi için bkz. [OpenURL](#openurl)üye işlevi. Ortak HTTP bağlantı görevlerini gerçekleştirme adımları için bkz. [Winınet Ile Internet programlama](../../mfc/win32-internet-extensions-wininet.md) makalesi.

## <a name="onstatuscallback"></a>CInternetSession:: OnStatusCallback

Bu üye işlevi, durum geri araması etkinleştirildiğinde ve bir işlem beklendiğinde durumu güncelleştirmek için Framework tarafından çağırılır.

```cpp
virtual void OnStatusCallback(
    DWORD_PTR dwContext,
    DWORD dwInternetStatus,
    LPVOID lpvStatusInformation,
    DWORD dwStatusInformationLength);
```

### <a name="parameters"></a>Parametreler

*dwContext*<br/>
Uygulama tarafından sağlanan bağlam değeri.

*dwInternetStatus*<br/>
Geri aramanın neden yapıldığını belirten bir durum kodu. Olası değerler tablosu için bkz. **açıklamalar** .

*lpvStatusInformation*<br/>
Bu geri çağırmada ilgili bilgileri içeren bir arabelleğin işaretçisi.

*Dwstatusınformationlength*<br/>
*LpvStatusInformation*boyutu.

### <a name="remarks"></a>Açıklamalar

Durum geri çağrısının avantajlarından yararlanmak için önce [EnableStatusCallback](#enablestatuscallback) çağrısı yapmanız gerekir.

*DwInternetStatus* parametresi, gerçekleştirilen işlemi belirtir ve *lpvStatusInformation* içeriğinin ne olacağını belirler. *Dwstatusınformationlength* , *lpvStatusInformation*içine eklenen verilerin uzunluğunu gösterir. *Dwinternetstatus* için aşağıdaki durum değerleri aşağıdaki gibi tanımlanır:

|Değer|Açıklama|
|-----------|-------------|
|INTERNET_STATUS_RESOLVING_NAME|*LpvStatusInformation*içinde bulunan adın IP adresi aranıyor.|
|INTERNET_STATUS_NAME_RESOLVED|*LpvStatusInformation*içinde bulunan adın IP adresi başarıyla bulundu.|
|INTERNET_STATUS_CONNECTING_TO_SERVER|*LpvStatusInformation*tarafından işaret edilen yuva adresine ([sockaddr](/windows/win32/winsock/sockaddr-2)) bağlanma.|
|INTERNET_STATUS_CONNECTED_TO_SERVER|*LpvStatusInformation*tarafından işaret edilen yuva ADRESINE (sockaddr) başarıyla bağlanıldı.|
|INTERNET_STATUS_SENDING_REQUEST|Bilgi isteği sunucuya gönderiliyor. *LpvStatusInformation* parametresi null.|
|INTERNET_STATUS_ REQUEST_SENT|Bilgi isteği sunucuya başarıyla gönderildi. *LpvStatusInformation* parametresi null.|
|INTERNET_STATUS_RECEIVING_RESPONSE|Sunucunun bir isteğe yanıt vermesi bekleniyor. *LpvStatusInformation* parametresi null.|
|INTERNET_STATUS_RESPONSE_RECEIVED|Sunucudan başarıyla yanıt alındı. *LpvStatusInformation* parametresi null.|
|INTERNET_STATUS_CLOSING_CONNECTION|Sunucu bağlantısı kapatılıyor. *LpvStatusInformation* parametresi null.|
|INTERNET_STATUS_CONNECTION_CLOSED|Sunucu bağlantısı başarıyla kapatıldı. *LpvStatusInformation* parametresi null.|
|INTERNET_STATUS_HANDLE_CREATED|Yeni tanıtıcıyı oluşturduğunu göstermek için [ınternetconnect](/windows/win32/api/wininet/nf-wininet-internetconnectw) Win32 API işlevi tarafından kullanılır. Bu, uygulamanın çok uzun sürüyorsa başka bir iş parçacığından [InternetClosehandle](/windows/win32/api/wininet/nf-wininet-internetclosehandle) Win32 işlevini çağırmasını sağlar. Bu işlevler hakkında daha fazla bilgi Için bkz. Windows SDK.|
|INTERNET_STATUS_HANDLE_CLOSING|Bu tanıtıcı değeri başarıyla sonlandırıldı.|

Bir durum geri çağırma yordamı gerçekleştirilmeden önce bazı eylemler gerektirmek için bu üye işlevini geçersiz kılın.

> [!NOTE]
> Durum geri çağırmaları iş parçacığı durumu korumasına gerek duyuyor. MFC 'yi paylaşılan bir kitaplıkta kullanıyorsanız, geçersiz kılmanın başlangıcına aşağıdaki satırı ekleyin:

[!code-cpp[NVC_MFCHtmlHttp#8](../../mfc/reference/codesnippet/cpp/cinternetsession-class_1.cpp)]

Zaman uyumsuz işlemler hakkında daha fazla bilgi için Internet ilk [adımları makalesine bakın: WinInet](../../mfc/wininet-basics.md).

## <a name="openurl"></a>CInternetSession:: OpenURL

Belirtilen isteği HTTP sunucusuna göndermek ve istemcinin istekle birlikte göndermek üzere ek RFC822, MIME veya HTTP üst bilgileri belirtmesini sağlamak için bu üye işlevi çağırın.

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
Okumaya başlamak için URL 'nin adı işaretçisi. Yalnızca şu dosya ile başlayan URL 'Ler:, FTP:, Gopher: veya http: desteklenir. *Pstrurl* null ise onaylar.

*dwContext*<br/>
Geri çağırmada döndürülen tanıtıcıyla birlikte uygulama tanımlı bir değer geçirildi.

*dwFlags*<br/>
Bu bağlantının nasıl işleneceğini açıklayan bayraklar. Geçerli bayraklar hakkında daha fazla bilgi için bkz. **açıklamalar** . Geçerli bayraklar şunlardır:

- Varsayılan INTERNET_FLAG_TRANSFER_ASCII. Dosyayı ASCII metin olarak aktarın.

- INTERNET_FLAG_TRANSFER_BINARY dosyayı ikili dosya olarak aktarır.

- INTERNET_FLAG_RELOAD yerel olarak önbelleğe alınmış olsa bile verileri iletişimden alın.

- INTERNET_FLAG_DONT_CACHE, yerel olarak veya herhangi bir ağ geçidi içinde verileri önbelleğe almaz.

- INTERNET_FLAG_SECURE bu bayrak yalnızca HTTP istekleri için geçerlidir. Güvenli Yuva Katmanı veya PCT ile tel karşı güvenli işlemler ister.

- INTERNET_OPEN_FLAG_USE_EXISTING_CONNECT mümkünse, her bağlantı isteği için yeni bir oturum oluşturmak yerine tarafından `OpenUrl` oluşturulan yeni istekler için sunucu bağlantılarını yeniden kullanın.

- FTP sitesi için kullanılan INTERNET_FLAG_PASSIVE. Pasif FTP semantiğini kullanır. [CInternetConnection](../../mfc/reference/cinternetconnection-class.md) `OpenURL`ile kullanılır.

*pstrHeaders*<br/>
HTTP sunucusuna gönderilecek üst bilgileri içeren bir dize işaretçisi.

*Dwheadersuzunluğu*<br/>
Ek üstbilgilerin karakter cinsinden uzunluğu. Bu-1L ve *PSTRHEADERS* null değilse, *pstrHeaders* 'nin sıfır sonlandırıldığını ve uzunluğunun hesaplandığını kabul edilir.

### <a name="return-value"></a>Dönüş Değeri

FTP, GOPHER, HTTP ve yalnızca dosya türü Internet Hizmetleri için bir dosya tanıtıcısı döndürür. Ayrıştırma başarısız olduysa NULL değerini döndürür.

`OpenURL` Döndüren işaretçi *pstrurl*'nin hizmet türüne bağlıdır. Aşağıdaki tabloda, olası işaretçiler `OpenURL` dönebileceği gösterilmektedir.

|URL türü|Döndürür|
|--------------|-------------|
|file://|`CStdioFile*`|
|http://|`CHttpFile*`|
|gopher://|`CGopherFile*`|
|ftp://|`CInternetFile*`|

### <a name="remarks"></a>Açıklamalar

*DwFlags* parametresi INTERNET_FLAG_TRANSFER_ASCII veya INTERNET_FLAG_TRANSFER_BINARY içermelidir, ancak her ikisini de içermemelidir. Kalan bayraklar bit düzeyinde **or** işleci ( **&#124;** ) ile birleştirilebilir.

`OpenURL`Win32 işlevini `InternetOpenURL`sarmalayan, yalnızca bir Internet sunucusundan verileri indirmeye, almaya ve okumasına izin verir. `OpenURL`uzak bir konumda dosya düzenlemesi yapılmasına izin vermez, bu nedenle [CInternetConnection](../../mfc/reference/cinternetconnection-class.md) nesnesi gerektirmez.

Bir dosyaya yazma gibi bağlantıya özgü (protokolüne özgü) işlevler kullanmak için bir oturum açmalı, sonra belirli bir bağlantı türü açmanız ve ardından bu bağlantıyı kullanarak istediğiniz modda bir dosya açmanız gerekir. Bağlantıya `CInternetConnection` özgü işlevler hakkında daha fazla bilgi için bkz.

## <a name="operator_hinternet"></a>CInternetSession:: operator HıNTERNET

Geçerli Internet oturumu için Windows tanıtıcısını almak üzere bu işleci kullanın.

```cpp
operator HINTERNET() const;
```

## <a name="setcookie"></a>CInternetSession:: SetCookie

Belirtilen URL için bir tanımlama bilgisi ayarlar.

```cpp
static BOOL SetCookie(
    LPCTSTR pstrUrl,
    LPCTSTR pstrCookieName,
    LPCTSTR pstrCookieData);
```

### <a name="parameters"></a>Parametreler

*pstrUrl*<br/>
Tanımlama bilgisinin ayarlanması gereken URL 'YI belirten, null ile sonlandırılmış bir dize işaretçisi.

*Pstrtanımlama bilgisi adı*<br/>
Tanımlama bilgisinin adını içeren bir dize işaretçisi.

*Pstrtarif ıedata*<br/>
URL ile ilişkilendirilecek gerçek dize verilerini içeren bir dize işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa TRUE, aksi takdirde FALSE döndürür. Belirli hata kodunu almak için çağrısı yapın`GetLastError.`

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK ' de açıklandığı gibi, Win32 iletisinin, [InternetSetCookie](/windows/win32/api/wininet/nf-wininet-internetsetcookiew)davranışını uygular.

## <a name="setoption"></a>CInternetSession:: SetOption

Internet oturumu seçeneklerini ayarlamak için bu üye işlevini çağırın.

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
Ayarlanacak Internet seçeneği. Olası seçeneklerin listesi Için bkz. Windows SDK 'daki [seçenek bayrakları](/windows/win32/WinInet/option-flags) .

*lpBuffer*<br/>
Seçenek ayarını içeren bir arabellek.

*dwBufferLength*<br/>
*LpBuffer* uzunluğu veya *dwValue*boyutu.

*dwValue*<br/>
Seçenek ayarını içeren bir DWORD.

*dwFlags*<br/>
Çeşitli önbelleğe alma seçeneklerini gösterir. Varsayılan değer 0 ' dır. Olası değerler şöyledir:

- INTERNET_FLAG_DONT_CACHE, yerel olarak veya herhangi bir ağ geçidi sunucusunda verileri önbelleğe almaz.

- INTERNET_FLAG_OFFLINE Indirme işlemleri yalnızca kalıcı önbellek aracılığıyla karşılanır. Öğe önbellekte yoksa, uygun bir hata kodu döndürülür. Bu bayrak, bit düzeyinde **or** ( **&#124;** ) işleciyle birleştirilebilir.

### <a name="return-value"></a>Dönüş Değeri

İşlem başarılı olduysa, TRUE değeri döndürülür. Bir hata oluştuysa, FALSE değeri döndürülür. Çağrı başarısız olursa, hatanın nedenini öğrenmek için [](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) WIN32 Win32 işlevi çağrılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CInternetConnection Sınıfı](../../mfc/reference/cinternetconnection-class.md)<br/>
[CHttpConnection Sınıfı](../../mfc/reference/chttpconnection-class.md)<br/>
[CFtpConnection Sınıfı](../../mfc/reference/cftpconnection-class.md)<br/>
[CGopherConnection Sınıfı](../../mfc/reference/cgopherconnection-class.md)
