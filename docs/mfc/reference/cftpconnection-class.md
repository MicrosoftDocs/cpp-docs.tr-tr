---
title: CFtpConnection sınıfı
ms.date: 08/29/2019
f1_keywords:
- CFtpConnection
- AFXINET/CFtpConnection
- AFXINET/CFtpConnection::CFtpConnection
- AFXINET/CFtpConnection::Command
- AFXINET/CFtpConnection::CreateDirectory
- AFXINET/CFtpConnection::GetCurrentDirectory
- AFXINET/CFtpConnection::GetCurrentDirectoryAsURL
- AFXINET/CFtpConnection::GetFile
- AFXINET/CFtpConnection::OpenFile
- AFXINET/CFtpConnection::PutFile
- AFXINET/CFtpConnection::Remove
- AFXINET/CFtpConnection::RemoveDirectory
- AFXINET/CFtpConnection::Rename
- AFXINET/CFtpConnection::SetCurrentDirectory
helpviewer_keywords:
- CFtpConnection [MFC], CFtpConnection
- CFtpConnection [MFC], Command
- CFtpConnection [MFC], CreateDirectory
- CFtpConnection [MFC], GetCurrentDirectory
- CFtpConnection [MFC], GetCurrentDirectoryAsURL
- CFtpConnection [MFC], GetFile
- CFtpConnection [MFC], OpenFile
- CFtpConnection [MFC], PutFile
- CFtpConnection [MFC], Remove
- CFtpConnection [MFC], RemoveDirectory
- CFtpConnection [MFC], Rename
- CFtpConnection [MFC], SetCurrentDirectory
ms.assetid: 5e3a0501-8893-49cf-a3d5-0628d8d6b936
ms.openlocfilehash: 94ee4cb938ee061470282eb2f08a94d83c908805
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78890808"
---
# <a name="cftpconnection-class"></a>CFtpConnection sınıfı

Bir Internet sunucusuyla FTP bağlantınızı yönetir ve bu sunucudaki dizinlerin ve dosyaların doğrudan işlemesini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CFtpConnection : public CInternetConnection
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Name|Açıklama|
|----------|-----------------|
|[CFtpConnection:: CFtpConnection](#cftpconnection)|`CFtpConnection` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Name|Açıklama|
|----------|-----------------|
|[CFtpConnection:: komutu](#command)|Bir FTP sunucusuna doğrudan bir komut gönderir.|
|[CFtpConnection:: CreateDirectory](#createdirectory)|Sunucuda bir dizin oluşturur.|
|[CFtpConnection:: GetCurrentDirectory](#getcurrentdirectory)|Bu bağlantının geçerli dizinini alır.|
|[CFtpConnection:: GetCurrentDirectoryAsURL](#getcurrentdirectoryasurl)|Bu bağlantının geçerli dizinini URL olarak alır.|
|[CFtpConnection:: GetFile](#getfile)|Bağlı sunucudan bir dosya alır|
|[CFtpConnection:: OpenFile](#openfile)|Bağlı sunucuda bir dosya açar.|
|[CFtpConnection::P utFile](#putfile)|Sunucuya bir dosya koyar.|
|[CFtpConnection:: Remove](#remove)|Bir dosyayı sunucudan kaldırır.|
|[CFtpConnection:: RemoveDirectory](#removedirectory)|Belirtilen dizini sunucudan kaldırır.|
|[CFtpConnection:: Rename](#rename)|Sunucudaki bir dosyayı yeniden adlandırır.|
|[CFtpConnection:: SetCurrentDirectory](#setcurrentdirectory)|Geçerli FTP dizinini ayarlar.|

## <a name="remarks"></a>Açıklamalar

FTP, MFC WinInet sınıfları tarafından tanınan üç Internet hizmetinden biridir.

Bir FTP Internet sunucusuyla iletişim kurmak için, önce bir [CInternetSession](../../mfc/reference/cinternetsession-class.md)örneği oluşturmanız ve ardından bir `CFtpConnection` nesnesi oluşturmanız gerekir. Hiçbir daha `CFtpConnection` nesnesini doğrudan oluşturmamanız gerekir; Bunun yerine, `CFtpConnection` nesnesini oluşturan ve ona bir işaretçi döndüren [CInternetSession:: GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)öğesini çağırın.

`CFtpConnection` diğer MFC Internet sınıflarıyla nasıl çalıştığı hakkında daha fazla bilgi edinmek için bkz. [Winınet Ile Internet programlama](../../mfc/win32-internet-extensions-wininet.md)makalesi. Desteklenen diğer iki hizmet, HTTP ve gopher ile iletişim kurma hakkında daha fazla bilgi için [CHttpConnection](../../mfc/reference/chttpconnection-class.md) ve [CGopherConnection](../../mfc/reference/cgopherconnection-class.md)sınıflarını inceleyin.

## <a name="example"></a>Örnek

  [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) sınıfına genel bakış bölümündeki örneğe bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CInternetConnection](../../mfc/reference/cinternetconnection-class.md)

`CFtpConnection`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFXINET. h

##  <a name="cftpconnection"></a>CFtpConnection:: CFtpConnection

Bu üye işlevi bir `CFtpConnection` nesnesi oluşturmak için çağırılır.

```
CFtpConnection(
    CInternetSession* pSession,
    HINTERNET hConnected,
    LPCTSTR pstrServer,
    DWORD_PTR dwContext);

CFtpConnection(
    CInternetSession* pSession,
    LPCTSTR pstrServer,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    DWORD_PTR dwContext = 0,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    BOOL bPassive = FALSE);
```

### <a name="parameters"></a>Parametreler

*pSession*<br/>
İlgili [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesine yönelik bir işaretçi.

*hConnected*<br/>
Geçerli Internet oturumunun Windows tanıtıcısı.

*pstrServer*<br/>
FTP sunucu adını içeren bir dize işaretçisi.

*dwContext*<br/>
İşlemin bağlam tanımlayıcısı. *dwContext* , [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)tarafından döndürülen işlemin durum bilgilerini tanımlar. Varsayılan değer 1 ' e ayarlanır; Ancak, işlem için özel bir bağlam KIMLIĞINI açıkça atayabilirsiniz. Nesne ve onun yaptığı herhangi bir iş, bu bağlam KIMLIĞIYLE ilişkilendirilecektir.

*pstrUserName*<br/>
Oturum açmak için kullanıcının adını belirten, null ile sonlandırılmış bir dize işaretçisi. NULL ise, varsayılan olarak anonim olur.

*pstrPassword*<br/>
Oturum açmak için kullanılacak parolayı belirten, null ile sonlandırılmış bir dize işaretçisi. Hem *pstrPassword* hem de *PSTRUSERNAME* null ise, varsayılan Anonim parola kullanıcının e-posta adıdır. *PstrPassword* null (veya boş bir dize) ise, ancak *pstrUserName* null değilse boş bir parola kullanılır. Aşağıdaki tabloda *pstrUserName* ve *pstrPassword*öğesinin dört olası ayarlarının davranışı açıklanmaktadır:

|*pstrUserName*|*pstrPassword*|FTP sunucusuna gönderilen Kullanıcı adı|FTP sunucusuna parola gönderildi|
|--------------------|--------------------|---------------------------------|---------------------------------|
|NULL veya ""|NULL veya ""|deðeri|Kullanıcının e-posta adı|
|NULL olmayan dize|NULL veya ""|*pstrUserName*|" "|
|Null olmayan boş dize|HATA|HATA||
|NULL olmayan dize|NULL olmayan dize|*pstrUserName*|*pstrPassword*|

*nPort*<br/>
Sunucuda kullanılacak TCP/IP bağlantı noktasını belirleyen bir sayı.

*Bpasif*<br/>
Bu FTP oturumu için pasif veya etkin modu belirtir. TRUE olarak ayarlanırsa, Win32 API *dwFlag* öğesini INTERNET_FLAG_PASSIVE olarak ayarlar.

### <a name="remarks"></a>Açıklamalar

Hiçbir daha `CFtpConnection` nesnesini doğrudan oluşturmamanız gerekir. Bunun yerine, `CFptConnection` nesnesini oluşturan [CInternetSession:: GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)öğesini çağırın.

##  <a name="command"></a>CFtpConnection:: komutu

Bir FTP sunucusuna doğrudan bir komut gönderir.

```
CInternetFile* Command(
    LPCTSTR pszCommand,
    CmdResponseType eResponse = CmdRespNone,
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Parametreler

*pszCommand*<br/>
Gönderilecek komutu içeren bir dize işaretçisi.

*eResponse*<br/>
FTP sunucusundan bir yanıtın beklenip beklenmediğini belirtir. Aşağıdaki değerlerden biri olabilir:

- Yanıt beklenmez `CmdRespNone`.
- Yanıt `CmdRespRead` bekleniyor.
- `CmdRespWrite` kullanılmıyor.

CmdResponseType, *AFXINET. h*Içinde tanımlanan CFtpConnection öğesinin bir üyesidir.

*dwFlags*<br/>
Bu işlevi denetleyen bayrakları içeren bir değer. Tüm liste için bkz. [Ftpkomutu](/windows/win32/api/wininet/nf-wininet-ftpcommandw).

*dwContext*<br/>
Geri çağırmalar içinde uygulama bağlamını tanımlamak için kullanılan uygulama tanımlı değeri içeren bir değere yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK bölümünde açıklandığı gibi [Ftpkomut](/windows/win32/api/wininet/nf-wininet-ftpcommandw) işlevinin işlevselliğine öykünür.

Bir hata oluşursa, MFC [CInternetException](../../mfc/reference/cinternetexception-class.md)türünde bir özel durum oluşturur.

##  <a name="createdirectory"></a>CFtpConnection:: CreateDirectory

Bağlı sunucuda bir dizin oluşturmak için bu üye işlevi çağırın.

```
BOOL CreateDirectory(LPCTSTR pstrDirName);
```

### <a name="parameters"></a>Parametreler

*pstrDirName*<br/>
Oluşturulacak dizinin adını içeren bir dize işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0. Çağrı başarısız olursa, hatanın nedenini öğrenmek için Windows işlevi [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) çağrılabilir.

### <a name="remarks"></a>Açıklamalar

Sunucu bağlantısı için geçerli çalışma dizinini öğrenmek üzere `GetCurrentDirectory` kullanın. Uzak sistemin sizi kök dizine bağladığını varsayın.

`pstrDirName` parametresi, geçerli dizine göre kısmen veya tam nitelenmiş bir dosya adı olabilir. Bir ters eğik çizgi (\\) veya eğik çizgi (/), her iki ad için de dizin ayırıcı olarak kullanılabilir. `CreateDirectory`, dizin adı ayırıcıları kullanılmadan önce uygun karakterlere çevirir.

##  <a name="getcurrentdirectory"></a>CFtpConnection:: GetCurrentDirectory

Geçerli dizinin adını almak için bu üye işlevini çağırın.

```
BOOL GetCurrentDirectory(CString& strDirName) const;

BOOL GetCurrentDirectory(
    LPTSTR pstrDirName,
    LPDWORD lpdwLen) const;
```

### <a name="parameters"></a>Parametreler

*strDirName*<br/>
Dizinin adını alacak bir dizeye başvuru.

*pstrDirName*<br/>
Dizinin adını alacak dize için bir işaretçi.

*lpdwLen*<br/>
Aşağıdaki bilgileri içeren bir DWORD işaretçisi işaretçisi:

|||
|-|-|
|Girişte|*PstrDirName*tarafından başvurulan arabelleğin boyutu.|
|Dönüşte|*PstrDirName*öğesine depolanan karakterlerin sayısı. Üye işlevi başarısız olursa ve ERROR_INSUFFICIENT_BUFFER döndürülürse, *lpdwLen* , uygulamanın dizeyi almak için ayırabilmesi gereken bayt sayısını içerir.|

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0. Çağrı başarısız olursa, hatanın nedenini öğrenmek için WIN32 [Win32 işlevi çağrılabilir](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) .

### <a name="remarks"></a>Açıklamalar

Bunun yerine dizin adını bir URL olarak almak için, [GetCurrentDirectoryAsURL](#getcurrentdirectoryasurl)çağırın.

*PstrDirName* veya *strDirName* parametreleri, geçerli dizine göre kısmen nitelenmiş dosya adları veya tam nitelikli olabilir. Bir ters eğik çizgi (\\) veya eğik çizgi (/), her iki ad için de dizin ayırıcı olarak kullanılabilir. `GetCurrentDirectory`, dizin adı ayırıcıları kullanılmadan önce uygun karakterlere çevirir.

##  <a name="getcurrentdirectoryasurl"></a>CFtpConnection:: GetCurrentDirectoryAsURL

Geçerli dizinin adını bir URL olarak almak için bu üye işlevi çağırın.

```
BOOL GetCurrentDirectoryAsURL(CString& strDirName) const;

BOOL GetCurrentDirectoryAsURL(
    LPTSTR pstrName,
    LPDWORD lpdwLen) const;
```

### <a name="parameters"></a>Parametreler

*strDirName*<br/>
Dizinin adını alacak bir dizeye başvuru.

*pstrDirName*<br/>
Dizinin adını alacak dize için bir işaretçi.

*lpdwLen*<br/>
Aşağıdaki bilgileri içeren bir DWORD işaretçisi işaretçisi:

|||
|-|-|
|Girişte|*PstrDirName*tarafından başvurulan arabelleğin boyutu.|
|Dönüşte|*PstrDirName*öğesine depolanan karakterlerin sayısı. Üye işlevi başarısız olursa ve ERROR_INSUFFICIENT_BUFFER döndürülürse, *lpdwLen* , uygulamanın dizeyi almak için ayırabilmesi gereken bayt sayısını içerir.|

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0. Çağrı başarısız olursa, hatanın nedenini öğrenmek için WIN32 [Win32 işlevi çağrılabilir](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) .

### <a name="remarks"></a>Açıklamalar

`GetCurrentDirectoryAsURL`, [GetCurrentDirectory](#getcurrentdirectory) ile aynı şekilde davranır

*StrDirName* parametresi, geçerli dizine göre kısmen nitelenmiş dosya adları veya tam nitelikli olabilir. Bir ters eğik çizgi (\\) veya eğik çizgi (/), her iki ad için de dizin ayırıcı olarak kullanılabilir. `GetCurrentDirectoryAsURL`, dizin adı ayırıcıları kullanılmadan önce uygun karakterlere çevirir.

##  <a name="getfile"></a>CFtpConnection:: GetFile

FTP sunucusundan bir dosya almak ve bunu yerel makinede depolamak için bu üye işlevi çağırın.

```
BOOL GetFile(
    LPCTSTR pstrRemoteFile,
    LPCTSTR pstrLocalFile,
    BOOL bFailIfExists = TRUE,
    DWORD dwAttributes = FILE_ATTRIBUTE_NORMAL,
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Parametreler

*Pstryereldosya*<br/>
FTP sunucusundan alınacak bir dosyanın adını içeren, null ile sonlandırılmış bir dize işaretçisi.

*Pstryereldosya*<br/>
Yerel sistemde oluşturulacak dosyanın adını içeren, null ile sonlandırılmış bir dize işaretçisi.

*bFailIfExists*<br/>
Dosya adının zaten var olan bir dosya tarafından kullanılıp kullanılamayacağını gösterir. Yerel dosya adı zaten varsa ve bu parametre TRUE ise, `GetFile` başarısız olur. Aksi takdirde, `GetFile` dosyanın varolan kopyasını silecek.

*dwAttributes*<br/>
Dosyanın özniteliklerini gösterir. Bu, aşağıdaki FILE_ATTRIBUTE_ * bayraklarının herhangi bir birleşimi olabilir.

- FILE_ATTRIBUTE_ARCHIVE dosya bir arşiv dosyasıdır. Uygulamalar, dosyaları yedekleme veya kaldırma için işaretlemek üzere bu özniteliği kullanır.

- FILE_ATTRIBUTE_COMPRESSED dosya veya dizin sıkıştırılmış. Bir dosya için sıkıştırma, dosyadaki tüm verilerin sıkıştırıldığı anlamına gelir. Bir dizin için sıkıştırma, yeni oluşturulan dosyalar ve alt dizinler için varsayılandır.

- Dosya bir dizin FILE_ATTRIBUTE_DIRECTORY.

- FILE_ATTRIBUTE_NORMAL dosyanın başka bir öznitelik ayarlanmamış. Bu öznitelik yalnızca tek başına kullanıldığında geçerlidir. Diğer tüm dosya özniteliklerinin FILE_ATTRIBUTE_NORMAL geçersiz kılar:

- FILE_ATTRIBUTE_HIDDEN dosya gizli. Sıradan bir dizin listesine dahil edilmez.

- FILE_ATTRIBUTE_READONLY dosya salt okunurdur. Uygulamalar dosyayı okuyabilir, ancak yazamaz veya silemez.

- Dosyanın bir parçası olan veya yalnızca işletim sistemi tarafından kullanılan FILE_ATTRIBUTE_SYSTEM.

- FILE_ATTRIBUTE_TEMPORARY dosya geçici depolama için kullanılıyor. Uygulamalar yalnızca kesinlikle gerekli olduğunda dosyaya yazmalıdır. Dosya yakında silineceğinden, dosyanın verilerinin çoğu medyaya boşaltılmadan bellekte kalır.

*dwFlags*<br/>
Aktarmanın gerçekleştiği koşulları belirtir. Bu parametre, Windows SDK [FtpGetFile](/windows/win32/api/wininet/nf-wininet-ftpgetfilew) bölümünde açıklanan *dwFlags* değerlerinden herhangi biri olabilir.

*dwContext*<br/>
Dosya alımı için bağlam tanımlayıcısı. *DwContext*hakkında daha fazla bilgi için bkz. **açıklamalar** .

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0. Çağrı başarısız olursa, hatanın nedenini öğrenmek için WIN32 [Win32 işlevi çağrılabilir](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) .

### <a name="remarks"></a>Açıklamalar

`GetFile`, bir FTP sunucusundan dosya okuma ve yerel olarak depolama ile ilişkili tüm ek yükü işleyen üst düzey bir yordamdır. Yalnızca dosya verilerini alan veya dosya aktarımı üzerinde yakın denetim gerektiren uygulamalar, bunun yerine `OpenFile` ve [CInternetFile:: Read](../../mfc/reference/cinternetfile-class.md#read) kullanmalıdır.

*DwFlags* FILE_TRANSFER_TYPE_ASCII, dosya verisi çevirisi de denetim ve biçimlendirme karakterlerini Windows eşdeğerlerine dönüştürür. Varsayılan aktarım, dosyanın sunucuda depolandıkları biçimde indirileceği ikili moddur.

Hem *Pstryereldosya* hem de *pstryereldosya* , geçerli dizine göre kısmen nitelenmiş dosya adları veya tam nitelikli olabilir. Bir ters eğik çizgi (\\) veya eğik çizgi (/), her iki ad için de dizin ayırıcı olarak kullanılabilir. `GetFile`, dizin adı ayırıcıları kullanılmadan önce uygun karakterlere çevirir.

Bağlam tanımlayıcısını seçtiğiniz bir değere ayarlamak için *dwContext* varsayılanını geçersiz kılın. Bağlam tanımlayıcısı, [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesi tarafından oluşturulan `CFtpConnection` nesnesinin bu özel işlemiyle ilişkili. Değer, tanımlandıkları işlemde durum sağlamak için [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) değerine döndürülür. Bağlam tanımlayıcısı hakkında daha fazla bilgi için [Internet Ilk adımlar: WinINet](../../mfc/wininet-basics.md) makalesine bakın.

##  <a name="openfile"></a>CFtpConnection:: OpenFile

Okuma veya yazma için FTP sunucusunda bulunan bir dosyayı açmak için bu üye işlevi çağırın.

```
CInternetFile* OpenFile(
    LPCTSTR pstrFileName,
    DWORD dwAccess = GENERIC_READ,
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Parametreler

*pstrFileName*<br/>
Açılacak dosyanın adını içeren bir dize işaretçisi.

*dwAccess*<br/>
Dosyaya nasıl erişileceğini belirler. GENERIC_READ veya GENERIC_WRITE olabilir, ancak ikisi birden olamaz.

*dwFlags*<br/>
Sonraki aktarımların oluştuğu koşulları belirtir. Bu, aşağıdaki FTP_TRANSFER_ * sabitlerinden herhangi biri olabilir:

- FTP ASCII (tür A) aktarım yöntemi kullanarak dosya aktarımlarını FTP_TRANSFER_TYPE_ASCII. Denetim ve biçimlendirme bilgilerini yerel eşdeğerlerine dönüştürür.

- FTP 'nin Image (Type I) aktarma yöntemi kullanılarak dosya aktarımı verileri FTP_TRANSFER_TYPE_BINARY. Dosya, verileri tam olarak bulunduğu gibi, hiçbir değişiklik olmadan aktarır. Bu, varsayılan aktarım yöntemidir.

*dwContext*<br/>
Dosyayı açmaya yönelik bağlam tanımlayıcısı. *DwContext*hakkında daha fazla bilgi için bkz. **açıklamalar** .

### <a name="return-value"></a>Dönüş Değeri

[CInternetFile](../../mfc/reference/cinternetfile-class.md) nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`OpenFile` aşağıdaki durumlarda kullanılmalıdır:

- Bir uygulamanın, gönderilmesi ve FTP sunucusunda bir dosya olarak oluşturulması gereken verileri vardır, ancak bu veriler yerel bir dosyada yer alır. `OpenFile` bir dosyayı açtığında, uygulama, FTP dosya verilerini sunucuya göndermek için [CInternetFile:: Write](../../mfc/reference/cinternetfile-class.md#write) kullanır.

- Bir uygulamanın sunucudan bir dosya alması ve uygulamayı diske yazmak yerine uygulama denetimli belleğe yerleştirmeli. Uygulama, dosyayı açmak için `OpenFile` kullandıktan sonra [CInternetFile:: Read](../../mfc/reference/cinternetfile-class.md#read) öğesini kullanır.

- Bir uygulama, bir dosya aktarımı üzerinde ince denetim düzeyine ihtiyaç duyuyor. Örneğin, uygulama bir işlem denetimini bir dosya indirilirken dosya aktarım durumunun ilerlemesini göstermek isteyebilir.

`OpenFile` çağrıldıktan ve `CInternetConnection::Close`çağrıldıktan sonra, uygulama yalnızca [CInternetFile:: Read](../../mfc/reference/cinternetfile-class.md#read), [CInternetFile:: Write](../../mfc/reference/cinternetfile-class.md#write), `CInternetConnection::Close`veya [CFtpFileFind:: FindFile](../../mfc/reference/cftpfilefind-class.md#findfile)çağırabilir. Aynı FTP oturumu için diğer FTP işlevlerine yapılan çağrılar başarısız olur ve hata kodunu FTP_ETRANSFER_IN_PROGRESS olarak ayarlar.

*PstrFileName* parametresi, geçerli dizine göre kısmen nitelenmiş bir dosya adı veya tam nitelikli bir dosya adı olabilir. Bir ters eğik çizgi (\\) veya eğik çizgi (/), her iki ad için de dizin ayırıcı olarak kullanılabilir. `OpenFile`, dizin adı ayırıcıları kullanmadan önce uygun karakterlere çevirir.

Bağlam tanımlayıcısını seçtiğiniz bir değere ayarlamak için *dwContext* varsayılanını geçersiz kılın. Bağlam tanımlayıcısı, [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesi tarafından oluşturulan `CFtpConnection` nesnesinin bu özel işlemiyle ilişkili. Değer, tanımlandıkları işlemde durum sağlamak için [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) değerine döndürülür. Bağlam tanımlayıcısı hakkında daha fazla bilgi için [Internet Ilk adımlar: WinINet](../../mfc/wininet-basics.md) makalesine bakın.

##  <a name="putfile"></a>CFtpConnection::P utFile

FTP sunucusunda bir dosyayı depolamak için bu üye işlevi çağırın.

```
BOOL PutFile(
    LPCTSTR pstrLocalFile,
    LPCTSTR pstrRemoteFile,
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Parametreler

*Pstryereldosya*<br/>
Yerel sistemden gönderilmek üzere dosyanın adını içeren bir dize işaretçisi.

*Pstryereldosya*<br/>
FTP sunucusunda oluşturulacak dosyanın adını içeren bir dize işaretçisi.

*dwFlags*<br/>
Dosya aktarımının gerçekleştiği koşulları belirtir. [OpenFile](#openfile)içinde açıklanan FTP_TRANSFER_ * sabitlerinden herhangi biri olabilir.

*dwContext*<br/>
Dosyayı yerleştirmek için bağlam tanımlayıcısı. *DwContext*hakkında daha fazla bilgi için bkz. **açıklamalar** .

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0. Çağrı başarısız olursa, hatanın nedenini öğrenmek için WIN32 [Win32 işlevi çağrılabilir](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) .

### <a name="remarks"></a>Açıklamalar

`PutFile`, bir dosyayı FTP sunucusunda depolarla ilişkili tüm işlemleri işleyen üst düzey bir yordamdır. Yalnızca veri gönderen veya dosya aktarımı üzerinde daha yakından denetim gerektiren uygulamalar [OpenFile](#openfile) ve [CInternetFile:: Write](../../mfc/reference/cinternetfile-class.md#write)kullanmalıdır.

Bağlam tanımlayıcısını seçtiğiniz bir değere ayarlamak için `dwContext` varsayılan değeri geçersiz kılın. Bağlam tanımlayıcısı, [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesi tarafından oluşturulan `CFtpConnection` nesnesinin bu özel işlemiyle ilişkili. Değer, tanımlandıkları işlemde durum sağlamak için [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) değerine döndürülür. Bağlam tanımlayıcısı hakkında daha fazla bilgi için [Internet Ilk adımlar: WinINet](../../mfc/wininet-basics.md) makalesine bakın.

##  <a name="remove"></a>CFtpConnection:: Remove

Belirtilen dosyayı bağlı sunucudan silmek için bu üye işlevini çağırın.

```
BOOL Remove(LPCTSTR pstrFileName);
```

### <a name="parameters"></a>Parametreler

*pstrFileName*<br/>
Kaldırılacak dosya adını içeren bir dize işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0. Çağrı başarısız olursa, hatanın nedenini öğrenmek için WIN32 [Win32 işlevi çağrılabilir](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) .

### <a name="remarks"></a>Açıklamalar

*PstrFileName* parametresi, geçerli dizine göre kısmen nitelenmiş bir dosya adı veya tam nitelikli bir dosya adı olabilir. Bir ters eğik çizgi (\\) veya eğik çizgi (/), her iki ad için de dizin ayırıcı olarak kullanılabilir. `Remove` işlevi, dizin adı ayırıcıları kullanılmadan önce uygun karakterlere çevirir.

##  <a name="removedirectory"></a>CFtpConnection:: RemoveDirectory

Belirtilen dizini bağlı sunucudan kaldırmak için bu üye işlevini çağırın.

```
BOOL RemoveDirectory(LPCTSTR pstrDirName);
```

### <a name="parameters"></a>Parametreler

*pstrDirName*<br/>
Kaldırılacak dizini içeren bir dize işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0. Çağrı başarısız olursa, hatanın nedenini öğrenmek için WIN32 [Win32 işlevi çağrılabilir](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) .

### <a name="remarks"></a>Açıklamalar

Sunucunun geçerli çalışma dizinini öğrenmek için [GetCurrentDirectory](#getcurrentdirectory) kullanın. Uzak sistemin sizi kök dizine bağladığını varsayın.

*PstrDirName* parametresi, geçerli dizine göre kısmen veya tam nitelenmiş bir dosya adı olabilir. Bir ters eğik çizgi (\\) veya eğik çizgi (/), her iki ad için de dizin ayırıcı olarak kullanılabilir. `RemoveDirectory`, dizin adı ayırıcıları kullanılmadan önce uygun karakterlere çevirir.

##  <a name="rename"></a>CFtpConnection:: Rename

Bağlı sunucuda belirtilen dosyayı yeniden adlandırmak için bu üye işlevi çağırın.

```
BOOL Rename(
    LPCTSTR pstrExisting,
    LPCTSTR pstrNew);
```

### <a name="parameters"></a>Parametreler

*pstrExisting*<br/>
Yeniden adlandırılacak dosyanın geçerli adını içeren bir dize işaretçisi.

*pstrNew*<br/>
Dosyanın yeni adını içeren bir dize işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0. Çağrı başarısız olursa, hatanın nedenini öğrenmek için WIN32 [Win32 işlevi çağrılabilir](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) .

### <a name="remarks"></a>Açıklamalar

*PstrExisting* ve *pstrNew* parametreleri, geçerli dizine göre kısmen nitelenmiş bir dosya adı ya da tam nitelikli bir dosya adı olabilir. Bir ters eğik çizgi (\\) veya eğik çizgi (/), her iki ad için de dizin ayırıcı olarak kullanılabilir. `Rename`, dizin adı ayırıcıları kullanılmadan önce uygun karakterlere çevirir.

##  <a name="setcurrentdirectory"></a>CFtpConnection:: SetCurrentDirectory

FTP sunucusundaki farklı bir dizine geçmek için bu üye işlevi çağırın.

```
BOOL SetCurrentDirectory(LPCTSTR pstrDirName);
```

### <a name="parameters"></a>Parametreler

*pstrDirName*<br/>
Dizinin adını içeren bir dize işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0. Çağrı başarısız olursa, hatanın nedenini öğrenmek için WIN32 [Win32 işlevi çağrılabilir](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) .

### <a name="remarks"></a>Açıklamalar

*PstrDirName* parametresi, geçerli dizine göre kısmen veya tam nitelenmiş bir dosya adı olabilir. Bir ters eğik çizgi (\\) veya eğik çizgi (/), her iki ad için de dizin ayırıcı olarak kullanılabilir. `SetCurrentDirectory`, dizin adı ayırıcıları kullanılmadan önce uygun karakterlere çevirir.

FTP sunucusunun geçerli çalışma dizinini öğrenmek için [GetCurrentDirectory](#getcurrentdirectory) kullanın. Uzak sistemin sizi kök dizine bağladığını varsayın.

## <a name="see-also"></a>Ayrıca bkz.

[CInternetConnection Sınıfı](../../mfc/reference/cinternetconnection-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CInternetConnection Sınıfı](../../mfc/reference/cinternetconnection-class.md)<br/>
[CInternetSession Sınıfı](../../mfc/reference/cinternetsession-class.md)
