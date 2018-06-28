---
title: CInternetSession sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 06/20/2018
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 648d295af6ca767eb0291f1eb8f0cd172d0717cc
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37041116"
---
# <a name="cinternetsession-class"></a>CInternetSession sınıfı

Oluşturur ve tek bir veya birkaç eşzamanlı Internet oturum başlatır ve gerekiyorsa, proxy sunucusuna bağlantınız açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
class CInternetSession : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CInternetSession::CInternetSession](#cinternetsession)|Oluşturan bir `CInternetSession` nesnesi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CInternetSession::Close](#close)|Internet oturumu sonlandırıldığında Internet bağlantıyı kapatır.|
|[CInternetSession::EnableStatusCallback](#enablestatuscallback)|Durum geri arama yordamı oluşturur.|
|[CInternetSession::GetContext](#getcontext)|Internet oturumu sonlandırıldığında Internet bağlantıyı kapatır.|
|[CInternetSession::GetCookie](#getcookie)|Tanımlama bilgileri, belirtilen URL'yi ve tüm üst için URL'leri döndürür.|
|[CInternetSession::GetCookieLength](#getcookielength)|Arabellekte depolanan tanımlama bilgisi uzunluğu belirtme değişkeni alır.|
|[CInternetSession::GetFtpConnection](#getftpconnection)|Bir FTP oturumunun bir sunucu ile açılır. Kullanıcıya günlüğe kaydeder.|
|[CInternetSession::GetGopherConnection](#getgopherconnection)|Bir bağlantı açmak için çalışan bir uygulama için bir gopher sunucusu açar.|
|[CInternetSession::GetHttpConnection](#gethttpconnection)|Bir bağlantı açmak için çalışan bir uygulama için bir HTTP sunucusu açar.|
|[CInternetSession::OnStatusCallback](#onstatuscallback)|Durum geri araması etkinleştirildiğinde, bir işlemin durumunu güncelleştirir.|
|[CInternetSession::OpenURL](#openurl)|Ayrıştırır ve bir URL açar.|
|[CInternetSession::SetCookie](#setcookie)|Belirtilen URL için bir tanımlama bilgisi ayarlar.|
|[CInternetSession::SetOption](#setoption)|Seçenekler Internet oturumu için ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CInternetSession::operator HINTERNET](#operator_hinternet)|Geçerli Internet oturumu için bir tanıtıcı.|

## <a name="remarks"></a>Açıklamalar

Internet bağlantınız için bir uygulama süresi korunmalıdır, oluşturabileceğiniz bir `CInternetSession` sınıf üyesi [CWinApp](../../mfc/reference/cwinapp-class.md).

Bir Internet oturumu kurduktan sonra çağırabilirsiniz [OpenURL](#openurl). `CInternetSession` ardından URL sizin için genel işlevini çağırarak ayrıştırır [AfxParseURL](internet-url-parsing-globals.md#afxparseurl). Kendi protokol türü ne olursa olsun `CInternetSession` URL yorumlar ve sizin için yönetir. URL kaynak "file://" tanımlanan yerel dosyaları için istekleri işleyebilir. `OpenURL` bir işaretçi döndürülecek bir [CStdioFile](../../mfc/reference/cstdiofile-class.md) adı geçirdiğiniz nesne yerel bir dosyasıdır.

Kullanarak bir Internet sunucusu üzerinde bir URL açarsanız `OpenURL`, site veritabanından bilgi edinebilirsiniz. Bir sunucuda bulunan dosyaları (örneğin, HTTP, FTP veya gopher için) hizmete özgü eylemleri gerçekleştirmek istiyorsanız, o sunucuda uygun bir bağlantı oluşturmanız gerekir. Doğrudan belirli bir hizmet bağlantı belirli bir tür açmak için aşağıdaki üye işlevleri birini kullanın:

- [GetGopherConnection](#getgopherconnection) gopher hizmetine bir bağlantı açmak için.

- [GetHttpConnection](#gethttpconnection) bir HTTP hizmetine bir bağlantı açmak için.

- [GetFtpConnection](#getftpconnection) bir FTP hizmetine bir bağlantı açmak için.

[SetOption](#setoption) zaman aşımı değerlerini, yeniden deneme sayısı, gibi oturumunuz sorgu seçenekleri ayarlama ve benzeri olanak tanır.

`CInternetSession` üye işlevleri [SetCookie](#setcookie), [GetCookie](#getcookie), ve [GetCookieLength](#getcookielength) üzerinden sunucuları ve komut dosyaları korumak Win32 tanımlama bilgisi veritabanını yönetmek için bir yol sağlar istemci iş istasyonunun hakkında durum bilgisi.

Temel Internet programlama görevleri hakkında daha fazla bilgi için bkz: [Internet ilk adımlar: WinINet](../../mfc/wininet-basics.md). MFC WinINet sınıfları kullanma hakkında genel bilgi için bkz: [Internet programlama WinINet ile](../../mfc/win32-internet-extensions-wininet.md).

> [!NOTE]
> `CInternetSession` özel durum oluşturacak bir [AfxThrowNotSupportedException](exception-processing.md#afxthrownotsupportedexception) desteklenmeyen hizmet türleri için. Yalnızca aşağıdaki hizmet türleri şu anda desteklenen: FTP, HTTP, gopher ve dosya.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)  
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

*pstrAgent*  
Uygulama veya Internet işlevleri (örneğin, "Microsoft Internet tarayıcısı") çağırma varlık adını tanımlayan bir dize için bir işaretçi. Varsa *pstrAgent* olan **NULL** (varsayılan), framework genel işlevini çağırması [AfxGetAppName](application-information-and-management.md#afxgetappname), bir uygulamanın içeren null ile sonlandırılmış bir dize döndürür adı. Bazı protokoller, uygulamanızı sunucuya tanımlamak için bu dizeyi kullanın.

*dwContext*  
İşlem bağlamı tanımlayıcısı. *dwContext* tarafından döndürülen işlem durumu bilgileri tanımlayan [CInternetSession::OnStatusCallback](#onstatuscallback). Varsayılan değer 1 olarak ayarlanır; Ancak, belirli bir bağlam kimliği işlemi için açıkça atayabilirsiniz. Nesne ve mevcut herhangi bir iş, içerik kimliği ile ilişkilendirilecek

*dwAccessType*  
Gerekli erişim türü. Tam olarak biri sağlanacak geçerli değerler şunlardır:

- `INTERNET_OPEN_TYPE_PRECONFIG` Önceden yapılandırılmış ayarları kayıt defterine kullanarak bağlanır. Bu erişim türü varsayılan olarak ayarlanır. TIS proxy üzerinden bağlanmak için *dwAccessType* bu değerine; ardından kayıt defteri uygun şekilde ayarlayın.

- `INTERNET_OPEN_TYPE_DIRECT` Doğrudan Internet'e bağlanın.

- `INTERNET_OPEN_TYPE_PROXY` CERN proxy üzerinden bağlanır.

Farklı proxy ile bağlanma hakkında daha fazla bilgi için bkz: [tipik bir FTP istemci uygulamasında adımları](../../mfc/steps-in-a-typical-ftp-client-application.md).

*pstrProxyName*  
Tercih edilen CERN proxy adını, *dwAccessType* olarak ayarlanmış olan `INTERNET_OPEN_TYPE_PROXY`. Varsayılan değer **NULL**.

*pstrProxyBypass*  
İsteğe bağlı bir sunucu adresleri listesi içeren bir dize için bir işaretçi. Bu adresleri proxy erişimi kullanırken atlanmasına. Varsa bir **NULL** sağlanan değeri, atlama listesi kayıt defterinden okunacak. Bu parametre anlamlıdır yalnızca *dwAccessType* ayarlanır `INTERNET_OPEN_TYPE_PROXY`.

*dwFlags*  
Çeşitli önbellek seçeneklerini gösterir. Varsayılan değer 0 olarak ayarlanır. Olası değerler şunlardır:

- `INTERNET_FLAG_DONT_CACHE` Verileri yerel olarak veya herhangi bir ağ geçidi sunucu önbelleğe almaz.

- `INTERNET_FLAG_OFFLINE` Karşıdan yükleme işlemleri yalnızca kalıcı önbellek aracılığıyla memnunsunuz. Öğe önbellekte yok uygun hata kodu döndürülür. Bu bayrak Bitsel ile birleştirilebilir `OR` ( **&#124;**) işleci.

### <a name="remarks"></a>Açıklamalar

`CInternetSession` ilk Internet işlevi bir uygulama tarafından çağrılır. İç veri yapılarını başlatır ve uygulamasından sonraki çağrılar için hazırlar.

Internet bağlantısı yok açılabiliyorsa `CInternetSession` oluşturur bir [Afxthrowınternetexception](internet-url-parsing-globals.md#afxthrowinternetexception).

### <a name="example"></a>Örnek

Örneğin bkz [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md).

## <a name="close"></a>  CInternetSession::Close

Uygulamanızı kullanarak tamamladığınızda bu üye işlevini çağırın `CInternetSession` nesnesi.

```cpp
virtual void Close();
```

### <a name="example"></a>Örnek

Örneğin bkz [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md).

## <a name="enablestatuscallback"></a>  CInternetSession::EnableStatusCallback

Durum geri çağırma etkinleştirmek için bu üye işlevini çağırın.

```cpp
BOOL EnableStatusCallback(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parametreler

*bSistemlerde*  
Geri çağırma etkin mi yoksa devre dışı mı olduğunu belirtir. Varsayılan değer **doğru**.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır olmayan; Aksi takdirde 0. Çağrı başarısız olursa, atılmış inceleyerek hatanın nedenini belirleyin [CInternetException](../../mfc/reference/cinternetexception-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

Durum geri araması işleme, uygulama durum çubuğunda (örneğin, ad çözümleme, sunucu ve benzeri) işlemi ilerleme durumu hakkında durum sağlayabilir. İşlem durumunu görüntüleme uzun vadeli bir işlemi sırasında özellikle önerilir.

Geri aramalar isteğin işlenirken meydana geldiği için uygulama ağa veri sn'ye düşüşünü önlemek üzere geri arama olabildiğince en az süre beklemesini. Örneğin, bir geri çağırma iletişim kutusunda koyma, sunucunun isteği sonlandırır gibi uzun bir işlem olabilir.

Tüm geri çağırmaları bekleyen sürece durum geri çağırma kaldırılamaz.

Herhangi bir işlem zaman uyumsuz olarak işlemek için kendi iş parçacığı oluşturma veya MFC olmadan WinINet işlevlerini kullanın.

## <a name="getcontext"></a>  CInternetSession::GetContext

Belirli bir uygulamayı oturum açmak için içerik değeri almak için bu üye işlevini çağırın.

```cpp
DWORD_PTR GetContext() const;
```

### <a name="return-value"></a>Dönüş Değeri

Uygulama tanımlı bağlam tanımlayıcısı.

### <a name="remarks"></a>Açıklamalar

[OnStatusCallback](#onstatuscallback) tarafından döndürülen bağlam Kimliğini kullanır `GetContext` belirli bir uygulamanın durumunu bildirmek için. Örneğin, bir kullanıcı durumu bilgilerini döndürme içerir bir Internet isteği etkinleştirdiğinde, durum geri çağırma durumu raporlamak context ID belirli bu isteği kullanır. İki ayrı kullanıcı etkinleştirir, Internet istekleri hem de ilgili durum bilgilerini döndürme `OnStatusCallback` bunların karşılık gelen istekler hakkında durumuna döndürmek için içerik tanımlayıcıları kullanır. Sonuç olarak, bağlam tanımlayıcı tüm durum geri çağırma işlemleri için kullanılır ve oturum sona kadar oturum ile ilişkilendirilir.

Zaman uyumsuz işlemleri hakkında daha fazla bilgi için bkz: [Internet ilk adımlar: WinINet](../../mfc/wininet-basics.md).

## <a name="getcookie"></a>  CInternetSession::GetCookie

Bu üye işlevi Win32 işlevi davranışını uygulayan [InternetGetCookie](http://msdn.microsoft.com/library/windows/desktop/aa384710), Windows SDK'ın açıklandığı gibi.

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

*pstrUrl*  
URL içeren bir dize için bir işaretçi.

*pstrCookieName*  
Belirtilen URL'ye almak için tanımlama bilgisinin adını içeren bir dize için bir işaretçi.

*pstrCookieData*  
İlk aşırı, tanımlama bilgisi verileri alan arabellek adresini içeren bir dize için bir işaretçi. Bu değer **NULL**. Bir başvuru ikinci aşırı yüklemesi içinde bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) tanımlama bilgisi verileri almak için nesne.

*dwBufLen*  
Boyutunu belirtme değişkeni *pstrCookieData* arabellek. İşlev başarılı olursa, arabellek kopyalanmasını veri miktarını alır *pstrCookieData* arabellek. Varsa *pstrCookieData* olan **NULL**, bu parametre tanımlama bilgisi verileri kopyalamak gerekli arabellek boyutunu belirleyen bir değer alır.

### <a name="return-value"></a>Dönüş Değeri

Döndürür **TRUE** başarılı olursa ya da **FALSE** Aksi takdirde. Çağrı başarısız olursa, Win32 işlevi çağrısı [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) hatanın nedenini belirlemek için. Aşağıdaki hata değerler geçerlidir:

- `ERROR_NO_MORE_ITEMS` Belirtilen URL için tanımlama bilgisi ve tüm üst öğelerinden yoktur.

- `ERROR_INSUFFICIENT_BUFFER` Geçirilen değer *dwBufLen* tüm tanımlama bilgisi verileri kopyalamak için yeterli değil. Döndürülen değerin *dwBufLen* arabellek boyutu tüm verileri almak gereklidir.

### <a name="remarks"></a>Açıklamalar

İkinci aşırı yüklemesi MFC tanımlama bilgisi verileri sağlanan alır `CString` nesnesi.

## <a name="getcookielength"></a>  CInternetSession::GetCookieLength

Arabellekte depolanan tanımlama bilgisi uzunluğu almak için bu üye işlevini çağırın.

```cpp
static DWORD GetCookieLength(
    LPCTSTR pstrUrl,
    LPCTSTR pstrCookieName);
```

### <a name="parameters"></a>Parametreler

*pstrUrl*  
URL içeren bir dize için bir işaretçi

*pstrCookieName*  
Tanımlama bilgisinin adını içeren bir dize için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

A `DWORD` arabellekte depolanan tanımlama bilgisi uzunluğu belirten değer. Belirtilen ada sahip tanımlama bilgisi varsa sıfır *pstrCookieName* bulunmaktadır.

### <a name="remarks"></a>Açıklamalar

Bu değer tarafından kullanılan [GetCookie](#getcookie).

## <a name="getftpconnection"></a>  CInternetSession::GetFtpConnection

Bir FTP bağlantısı kurmak ve bir işaretçi almak için bu üye işlevini çağırın bir `CFtpConnection` nesnesi.

```cpp
CFtpConnection* GetFtpConnection(
    LPCTSTR pstrServer,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    BOOL bPassive = FALSE);
```

### <a name="parameters"></a>Parametreler

*pstrServer*  
FTP sunucusu adını içeren bir dize için bir işaretçi.

*pstrUserName*  
İşaretçi null ile sonlandırılmış dizeye oturum açmak için kullanıcı adını belirtir. Varsa **NULL**, anonim varsayılandır.

*pstrPassword*  
Oturum açmak için kullanılacak parolayı belirten null ile sonlandırılmış bir dize için bir işaretçi. Her iki *pstrPassword* ve *pstrUserName* olan **NULL**, varsayılan anonim parola kullanıcının e-posta adıdır. Varsa *pstrPassword* olan **NULL** (veya boş bir dize) ancak *pstrUserName* değil **NULL**, boş bir parola kullanılır. Aşağıdaki tabloda dört olası ayarlarını davranışını açıklanmaktadır *pstrUserName* ve *pstrPassword*:

|*pstrUserName*|*pstrPassword*|FTP sunucusuna gönderilen kullanıcı adı|FTP sunucusuna gönderilen parola|
|--------------------|--------------------|---------------------------------|---------------------------------|
|**NULL** veya ""|**NULL** veya ""|"anonim"|Kullanıcının e-posta adı|
|Olmayan-**NULL** dize|**NULL** veya ""|*pstrUserName*|" "|
|**NULL**|Olmayan-**NULL** dize|**HATA**|**HATA**||
|Olmayan-**NULL** dize|Olmayan-**NULL** dize|*pstrUserName*|*pstrPassword*|

*nbağlantı noktası*  
Sunucuda kullanmak için TCP/IP bağlantı noktası tanımlayan bir sayı.

*bPassive*  
Bu FTP oturumu için etkin veya Pasif modu belirtir. Varsa kümesine **TRUE**, Win32 API ayarlar `dwFlag` için `INTERNET_FLAG_PASSIVE`.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir [CFtpConnection](../../mfc/reference/cftpconnection-class.md) nesnesi. Çağrı başarısız olursa, atılmış inceleyerek hatanın nedenini belirleyin [CInternetException](../../mfc/reference/cinternetexception-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

`GetFtpConnection` bir FTP sunucusuna bağlanır ve oluşturur ve bir işaretçi döndüren bir `CFTPConnection` nesnesi. Sunucu üzerindeki herhangi bir özel işlem gerçekleştirmez. Örneğin, okumak veya dosyaya yazmak istiyorsanız, o işlemler ayrı adımları gerçekleştirmeniz gerekir. Sınıfları görmek [CFtpConnection](../../mfc/reference/cftpconnection-class.md) ve [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) dosya arama hakkında daha fazla bilgi için dosyaları açma ve okuma ya da dosyalara yazma. Makalesine bakın [Internet programlama WinINet ile](../../mfc/win32-internet-extensions-wininet.md) ortak FTP bağlantı görevleri gerçekleştirme adımları için.

### <a name="example"></a>Örnek

Örneğin bkz [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md).

## <a name="getgopherconnection"></a>  CInternetSession::GetGopherConnection

Yeni bir gopher bağlantı kurmak ve bir işaretçi almak için bu üye işlevini çağırın bir `CGopherConnection` nesnesi.

```cpp
CGopherConnection* GetGopherConnection(
    LPCTSTR pstrServer,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```

### <a name="parameters"></a>Parametreler

*pstrServer*  
Gopher sunucu adını içeren bir dize için bir işaretçi.

*pstrUserName*  
Kullanıcı adını içeren bir dize için bir işaretçi.

*pstrPassword*  
Erişim parolasını içeren bir dize için bir işaretçi.

*nbağlantı noktası*  
Sunucuda kullanmak için TCP/IP bağlantı noktası tanımlayan bir sayı.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) nesnesi. Çağrı başarısız olursa, atılmış inceleyerek hatanın nedenini belirleyin [CInternetException](../../mfc/reference/cinternetexception-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

`GetGopherConnection` gopher sunucusuna bağlanır ve oluşturur ve bir işaretçi döndüren bir `CGopherConnection` nesnesi. Sunucu üzerindeki herhangi bir özel işlem gerçekleştirmez. Örneğin, veri okumaya veya yazmaya yapmak istiyorsanız, o işlemler ayrı adımları gerçekleştirmeniz gerekir. Sınıfları görmek [CGopherConnection](../../mfc/reference/cgopherconnection-class.md), [CGopherFile](../../mfc/reference/cgopherfile-class.md), ve [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) dosya arama hakkında daha fazla bilgi için dosyaları açma ve okuma ya da dosyalara yazma. Üye işlevi bir FTP sitesi gözatma hakkında daha fazla bilgi için bkz [OpenURL](#openurl). Makalesine bakın [Internet programlama WinINet ile](../../mfc/win32-internet-extensions-wininet.md) ortak gopher bağlantı görevleri gerçekleştirme adımları için.

## <a name="gethttpconnection"></a>  CInternetSession::GetHttpConnection

Bir işaretçi almak ve bir HTTP bağlantısı kurmak için bu üye işlevini çağırın bir `CHttpConnection` nesnesi.

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

*pstrServer*  
HTTP sunucusu adını içeren bir dize için bir işaretçi.

*nbağlantı noktası*  
Sunucuda kullanmak için TCP/IP bağlantı noktası tanımlayan bir sayı.

*pstrUserName*  
Kullanıcı adını içeren bir dize için bir işaretçi.

*pstrPassword*  
Erişim parolasını içeren bir dize için bir işaretçi.

*dwflags*  
Herhangi bir bileşimini `INTERNET_FLAG_*` bayrakları. Bölümündeki tabloya bakın **açıklamalar** bölümünü [CHttpConnection::OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest) bir açıklaması için *dwFlags* değerleri.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir [CHttpConnection](../../mfc/reference/chttpconnection-class.md) nesnesi. Çağrı başarısız olursa, atılmış inceleyerek hatanın nedenini belirleyin [CInternetException](../../mfc/reference/cinternetexception-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

`GetHttpConnection` bir HTTP sunucusuna bağlanır ve oluşturur ve bir işaretçi döndürür bir `CHttpConnection` nesnesi. Sunucu üzerindeki herhangi bir özel işlem gerçekleştirmez. Örneğin, bir HTTP üstbilgisi sorgulamak istiyorsanız, ayrı bir adım olarak bu işlemi gerçekleştirmeniz gerekir. Sınıfları görmek [CHttpConnection](../../mfc/reference/chttpconnection-class.md) ve [CHttpFile](../../mfc/reference/chttpfile-class.md) işlemleri hakkında bilgi için bir HTTP sunucusuna bir bağlantı kullanarak gerçekleştirebilirsiniz. Üye işlevi bir HTTP site gözatma hakkında daha fazla bilgi için bkz [OpenURL](#openurl). Makalesine bakın [Internet programlama WinINet ile](../../mfc/win32-internet-extensions-wininet.md) ortak HTTP bağlantı görevleri gerçekleştirme adımları için.

## <a name="onstatuscallback"></a>  CInternetSession::OnStatusCallback

Bu üye işlev durumu geri çağırma etkin olduğunda ve bir işlemi bekliyor durumunu güncelleştirmek için çerçevesi tarafından çağrılır.

```cpp
virtual void OnStatusCallback(
    DWORD_PTR dwContext,
    DWORD dwInternetStatus,
    LPVOID lpvStatusInformation,
    DWORD dwStatusInformationLength);
```

### <a name="parameters"></a>Parametreler

*dwContext*  
Uygulama tarafından sağlanan içerik değeri.

*dwInternetStatus*  
Geri çağırma neden yapılıyor gösteren bir durum kodu. Bkz: **açıklamalar** için olası değerler tablosu.

*lpvStatusInformation*  
Bu geri çağırma ilgili bilgileri içeren bir arabellek için bir işaretçi.

*dwStatusInformationLength*  
Boyutunu *lpvStatusInformation*.

### <a name="remarks"></a>Açıklamalar

İlk çağırmalısınız [EnableStatusCallback](#enablestatuscallback) durum geri çağırma yararlanmak için.

*DwInternetStatus* parametresi gerçekleştirilmekte olan işlemin gösterir ve hangi içeriğini belirler *lpvStatusInformation* olacaktır. *dwStatusInformationLength* dahil veri uzunluğunu gösterir *lpvStatusInformation*. Aşağıdaki durum değerleri *dwInternetStatus* şu şekilde tanımlanır:

|Değer|Açıklama|
|-----------|-------------|
|`INTERNET_STATUS_RESOLVING_NAME`|İçinde yer alan adının IP adresini bakarak *lpvStatusInformation*.|
|`INTERNET_STATUS_NAME_RESOLVED`|İçinde yer alan adı, IP adresi başarıyla bulunmadı *lpvStatusInformation*.|
|`INTERNET_STATUS_CONNECTING_TO_SERVER`|Yuva adresine bağlanan ([SOCKADDR](../../mfc/reference/sockaddr-structure.md)) gösterdiği *lpvStatusInformation*.|
|`INTERNET_STATUS_CONNECTED_TO_SERVER`|Yuva adresine başarıyla bağlandı (`SOCKADDR`) gösterdiği *lpvStatusInformation*.|
|`INTERNET_STATUS_SENDING_REQUEST`|Sunucuya bilgi isteği gönderiliyor. *LpvStatusInformation* parametresi **NULL**.|
|`INTERNET_STATUS_ REQUEST_SENT`|Sunucuya bilgi isteği gönderildi. *LpvStatusInformation* parametresi **NULL**.|
|`INTERNET_STATUS_RECEIVING_RESPONSE`|Sunucunun bir isteğine yanıt vermesi bekleniyor. *LpvStatusInformation* parametresi **NULL**.|
|`INTERNET_STATUS_RESPONSE_RECEIVED`|Başarıyla sunucusundan bir yanıt aldı. *LpvStatusInformation* parametresi **NULL**.|
|`INTERNET_STATUS_CLOSING_CONNECTION`|Sunucuya bağlantı kesiliyor. *LpvStatusInformation* parametresi **NULL**.|
|`INTERNET_STATUS_CONNECTION_CLOSED`|Sunucu bağlantısı başarıyla kapatıldı. *LpvStatusInformation* parametresi **NULL**.|
|`INTERNET_STATUS_HANDLE_CREATED`|Win32 API işlevi tarafından kullanılan [InternetConnect](http://msdn.microsoft.com/library/windows/desktop/aa384363) yeni tutamacı oluşturdu belirtmek için. Bu uygulama çağrısı Win32 işlevi sağlar [InternetCloseHandle](http://msdn.microsoft.com/library/windows/desktop/aa384350) Bağlan çok uzun sürüyorsa, başka bir iş parçacığından. Windows SDKfor bu işlevler hakkında daha fazla bilgi bakın.|
|`INTERNET_STATUS_HANDLE_CLOSING`|Bu işleyici değer başarıyla sonlandırıldı.|

Durum geri arama yordamı gerçekleştirilmeden önce bazı eylemleri gerektirecek şekilde bu üye işlevi geçersiz kılar.

> [!NOTE]
> Durum geri aramalar iş parçacığı durumu koruması gerekir. MFC paylaşılan bir kitaplık kullanıyorsanız, aşağıdaki satırı geçersiz kılma başlangıcına ekleyin:

 [!code-cpp[NVC_MFCHtmlHttp#8](../../mfc/reference/codesnippet/cpp/cinternetsession-class_1.cpp)]

Zaman uyumsuz işlemleri hakkında daha fazla bilgi için bkz: [Internet ilk adımlar: WinINet](../../mfc/wininet-basics.md).

## <a name="openurl"></a>  CInternetSession::OpenURL

Bu üye, belirtilen İstek HTTP sunucusuna göndermek ve ek RFC822 belirtmek istemcinin izin MIME işlevini veya istekle birlikte göndermek için HTTP üstbilgileri çağırın.

```cpp
CStdioFile* OpenURL(
    LPCTSTR pstrURL,
    DWORD_PTR dwContext = 1,
    DWORD dwFlags = INTERNET_FLAG_TRANSFER_ASCII,
    LPCTSTR pstrHeaders = NULL,
    DWORD dwHeadersLength = 0);
```

### <a name="parameters"></a>Parametreler

*pstrURL*  
Okumanın başlatılacağı URL adı için bir işaretçi. Yalnızca URL'leri dosya ile başlayan:, ftp:, gopher:, veya http: desteklenir. Varsa onaylar *pstrURL* olan **NULL**.

*dwContext*  
Geri döndürülen işleyiciyi ile uygulama tanımlı bir değer geçirildi.

*dwFlags*  
Bu bağlantı ne yapılacağını açıklayan bayrakları. Bkz: **açıklamalar** geçerli bayrakları hakkında daha fazla bilgi. Geçerli bayraklar şunlardır:

- `INTERNET_FLAG_TRANSFER_ASCII` Varsayılan. Dosya ASCII metni olarak aktarın.

- `INTERNET_FLAG_TRANSFER_BINARY` Dosya bir ikili dosya olarak aktarın.

- `INTERNET_FLAG_RELOAD` Yerel olarak önbelleğe olsa bile hattan verileri alın.

- `INTERNET_FLAG_DONT_CACHE` Verileri yerel olarak veya herhangi bir ağ geçidi önbelleğe almaz.

- `INTERNET_FLAG_SECURE` Bu bayrak, yalnızca HTTP istekleri için geçerlidir. Güvenli Yuva Katmanı veya yüzdesi hattaki güvenli işlemler istekleri

- `INTERNET_OPEN_FLAG_USE_EXISTING_CONNECT` Mümkünse, sunucu tarafından oluşturulan yeni istekler için var olan bağlantılara yeniden `OpenUrl` her bağlantı isteği için yeni bir oturumu oluşturmak yerine.

- `INTERNET_FLAG_PASSIVE` Bir FTP sitesi için kullanılır. Edilgen FTP semantiğini kullanır. İle kullanılan [CInternetConnection](../../mfc/reference/cinternetconnection-class.md) , `OpenURL`.

*pstrHeaders*  
HTTP sunucusu gönderilmesi gereken üstbilgileri içeren bir dize için bir işaretçi.

*dwHeadersLength*  
Ek üstbilgilerinin karakter cinsinden uzunluğu. Bu-1 M ise ve *pstrHeaders* olan olmayan**NULL**, ardından *pstrHeaders* sıfır olacak şekilde sonlandı ve uzunluğu hesaplanması varsayılır.

### <a name="return-value"></a>Dönüş Değeri

Yalnızca FTP, GOPHER, HTTP ve dosya türünü Internet Hizmetleri için bir dosya tanıtıcısı döndürür. Döndürür **NULL** ayrıştırma başarısız olursa.

İşaretçinin, `OpenURL` döndürür bağımlı *pstrURL*'s hizmetin türü. Aşağıdaki tabloda olası işaretçileri gösterilmiştir `OpenURL` geri dönebilirsiniz.

|URL türü|Döndürür|
|--------------|-------------|
|File://|`CStdioFile*`|
|http://|`CHttpFile*`|
|Gopher://|`CGopherFile*`|
|FTP: / /|`CInternetFile*`|

### <a name="remarks"></a>Açıklamalar

Parametre *dwFlags* ya da içermelidir `INTERNET_FLAG_TRANSFER_ASCII` veya `INTERNET_FLAG_TRANSFER_BINARY`, ancak ikisini birden değil. Kalan bayrakları Bitsel ile birleştirilebilir `OR` işleci ( **&#124;**).

`OpenURL`, Win32 işlevi sarmalar `InternetOpenURL`, yalnızca yükleme, alma ve Internet sunucusundan verileri okuma sağlar. `OpenURL` Hayır gerektiren hiçbir dosya işleme uzak bir konumdaki sağladığından [CInternetConnection](../../mfc/reference/cinternetconnection-class.md) nesnesi.

Bağlantıya özgü kullanmak için (diğer bir deyişle, protokole özgü) işlevleri, bir dosyaya yazmak gibi gerekir bir oturumu açın, sonra belirli bir bağlantı türünü açın, ardından istenen modda bir dosyayı açmak için bu bağlantıyı kullanın. Bkz: `CInternetConnection` bağlantıya özgü işlevleri hakkında daha fazla bilgi için.

## <a name="operator_hinternet"></a>  CInternetSession::operator HINTERNET

Windows tanıtıcı geçerli Internet oturumu için almak için bu işleci kullanın.

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

*pstrUrl*  
Tanımlama bilgisinin ayarlanmalıdır URL'sini belirten null ile sonlandırılmış bir dize için bir işaretçi.

*pstrCookieName*  
Tanımlama bilgisinin adını içeren bir dize için bir işaretçi.

*pstrCookieData*  
URL ile ilişkilendirmek için gerçek dize verilerini içeren bir dize için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Döndürür **TRUE** başarılı olursa ya da **FALSE** Aksi takdirde. Özel hata kodu almak için arama **GetLastError.**

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi Win32 ileti davranışını uygulayan [InternetSetCookie](http://msdn.microsoft.com/library/windows/desktop/aa385107), Windows SDK'ın açıklandığı gibi.

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

*dwOption*  
Ayarlamak için Internet seçeneği. Bkz: [seçeneği bayrakları](http://msdn.microsoft.com/library/windows/desktop/aa385328) Windows SDKfor olası seçeneklerin bir listesini içinde.

*lpBuffer*  
Seçenek ayarı içeren bir arabellek.

*dwBufferLength*  
Uzunluğu *lpBuffer* veya sütunların boyutunu *dwValue*.

*dwValue*  
A `DWORD` seçeneği ayarı içerir.

*dwFlags*  
Çeşitli önbellek seçeneklerini gösterir. Varsayılan değer 0 olarak ayarlanır. Olası değerler şunlardır:

- `INTERNET_FLAG_DONT_CACHE` Verileri yerel olarak veya herhangi bir ağ geçidi sunucu önbelleğe almaz.

- `INTERNET_FLAG_OFFLINE` Karşıdan yükleme işlemleri yalnızca kalıcı önbellek aracılığıyla memnunsunuz. Öğe önbellekte yok uygun hata kodu döndürülür. Bu bayrak Bitsel ile birleştirilebilir `OR` ( **&#124;**) işleci.

### <a name="return-value"></a>Dönüş Değeri

İşlem başarılı olursa değerini **TRUE** döndürülür. Bir hata oluştuysa, değerini **FALSE** döndürülür. Çağrı başarısız olursa, Win32 işlevi [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) hatanın nedenini belirlemek için çağrılabilir.

## <a name="see-also"></a>Ayrıca Bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)  
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)  
[CInternetConnection Sınıfı](../../mfc/reference/cinternetconnection-class.md)  
[CHttpConnection Sınıfı](../../mfc/reference/chttpconnection-class.md)  
[CFtpConnection Sınıfı](../../mfc/reference/cftpconnection-class.md)  
[CGopherConnection Sınıfı](../../mfc/reference/cgopherconnection-class.md)  
