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
ms.openlocfilehash: 4ad2262b17208dd634b59f5df4d6e60c300bb3c1
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832743"
---
# <a name="cftpconnection-class"></a>CFtpConnection sınıfı

Bir Internet sunucusuyla FTP bağlantınızı yönetir ve bu sunucudaki dizinlerin ve dosyaların doğrudan işlemesini sağlar.

## <a name="syntax"></a>Syntax

```
class CFtpConnection : public CInternetConnection
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CFtpConnection:: CFtpConnection](#cftpconnection)|Bir `CFtpConnection` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
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

Bir FTP Internet sunucusuyla iletişim kurmak için, önce bir [CInternetSession](../../mfc/reference/cinternetsession-class.md)örneği oluşturmanız ve ardından bir nesnesi oluşturmanız gerekir `CFtpConnection` . Doğrudan bir nesne oluşturmadıysanız `CFtpConnection` ; bunun yerine, nesneyi oluşturan ve kendisine bir işaretçi döndüren [CInternetSession:: GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)öğesini çağırın `CFtpConnection` .

Diğer MFC Internet sınıflarıyla nasıl çalıştığı hakkında daha fazla bilgi edinmek için `CFtpConnection` bkz. [Winınet Ile Internet programlama](../../mfc/win32-internet-extensions-wininet.md)makalesi. Desteklenen diğer iki hizmet, HTTP ve gopher ile iletişim kurma hakkında daha fazla bilgi için [CHttpConnection](../../mfc/reference/chttpconnection-class.md) ve [CGopherConnection](../../mfc/reference/cgopherconnection-class.md)sınıflarını inceleyin.

## <a name="example"></a>Örnek

  [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) sınıfına genel bakış bölümündeki örneğe bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CInternetConnection](../../mfc/reference/cinternetconnection-class.md)

`CFtpConnection`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFXINET. h

## <a name="cftpconnectioncftpconnection"></a><a name="cftpconnection"></a> CFtpConnection:: CFtpConnection

Bu üye işlevi bir nesne oluşturmak için çağırılır `CFtpConnection` .

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

Hiçbir şekilde doğrudan bir nesne oluşturmamanız gerekir `CFtpConnection` . Bunun yerine, nesnesini oluşturan [CInternetSession:: GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)öğesini çağırın `CFptConnection` .

## <a name="cftpconnectioncommand"></a><a name="command"></a> CFtpConnection:: komutu

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

- `CmdRespNone` Yanıt beklenmez.
- `CmdRespRead` Yanıt bekleniyor.
- `CmdRespWrite` Kullanılmıyor.

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

## <a name="cftpconnectioncreatedirectory"></a><a name="createdirectory"></a> CFtpConnection:: CreateDirectory

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

`GetCurrentDirectory`Sunucu bağlantısı için geçerli çalışma dizinini öğrenmek üzere kullanın. Uzak sistemin sizi kök dizine bağladığını varsayın.

`pstrDirName`Parametresi, geçerli dizine göre kısmen veya tam nitelenmiş bir dosya adı olabilir. Bir ters eğik çizgi ( \\ ) veya eğik çizgi (/), her iki ad için de dizin ayırıcı olarak kullanılabilir. `CreateDirectory` Dizin adı ayırıcıları kullanılmadan önce uygun karakterlere çevirir.

## <a name="cftpconnectiongetcurrentdirectory"></a><a name="getcurrentdirectory"></a> CFtpConnection:: GetCurrentDirectory

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

Girişte: *pstrDirName*tarafından başvurulan arabelleğin boyutu.

Dönüş sırasında: *pstrDirName*olarak depolanan karakterlerin sayısı. Üye işlevi başarısız olursa ve ERROR_INSUFFICIENT_BUFFER döndürülürse, *lpdwLen* , uygulamanın dizeyi almak için ayırabilmesi gereken bayt sayısını içerir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0. Çağrı başarısız olursa, hatanın nedenini öğrenmek için WIN32 [Win32 işlevi çağrılabilir](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) .

### <a name="remarks"></a>Açıklamalar

Bunun yerine dizin adını bir URL olarak almak için, [GetCurrentDirectoryAsURL](#getcurrentdirectoryasurl)çağırın.

*PstrDirName* veya *strDirName* parametreleri, geçerli dizine göre kısmen nitelenmiş dosya adları veya tam nitelikli olabilir. Bir ters eğik çizgi ( \\ ) veya eğik çizgi (/), her iki ad için de dizin ayırıcı olarak kullanılabilir. `GetCurrentDirectory` Dizin adı ayırıcıları kullanılmadan önce uygun karakterlere çevirir.

## <a name="cftpconnectiongetcurrentdirectoryasurl"></a><a name="getcurrentdirectoryasurl"></a> CFtpConnection:: GetCurrentDirectoryAsURL

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

Girişte: *pstrDirName*tarafından başvurulan arabelleğin boyutu.

Dönüş sırasında: *pstrDirName*olarak depolanan karakterlerin sayısı. Üye işlevi başarısız olursa ve ERROR_INSUFFICIENT_BUFFER döndürülürse, *lpdwLen* , uygulamanın dizeyi almak için ayırabilmesi gereken bayt sayısını içerir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0. Çağrı başarısız olursa, hatanın nedenini öğrenmek için WIN32 [Win32 işlevi çağrılabilir](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) .

### <a name="remarks"></a>Açıklamalar

`GetCurrentDirectoryAsURL`[GetCurrentDirectory](#getcurrentdirectory) ile aynı şekilde davranır

*StrDirName* parametresi, geçerli dizine göre kısmen nitelenmiş dosya adları veya tam nitelikli olabilir. Bir ters eğik çizgi ( \\ ) veya eğik çizgi (/), her iki ad için de dizin ayırıcı olarak kullanılabilir. `GetCurrentDirectoryAsURL` Dizin adı ayırıcıları kullanılmadan önce uygun karakterlere çevirir.

## <a name="cftpconnectiongetfile"></a><a name="getfile"></a> CFtpConnection:: GetFile

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
Dosya adının zaten var olan bir dosya tarafından kullanılıp kullanılamayacağını gösterir. Yerel dosya adı zaten varsa ve bu parametre TRUE ise, `GetFile` başarısız olur. Aksi takdirde, `GetFile` dosyanın varolan kopyasını silecektir.

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

`GetFile` , bir FTP sunucusundan dosya okuma ve yerel olarak depolama ile ilişkili tüm ek yükü işleyen üst düzey bir yordamdır. Yalnızca dosya verilerini alan veya dosya aktarımı üzerinde yakın denetim gerektiren uygulamalar, `OpenFile` bunun yerine [CInternetFile:: Read](../../mfc/reference/cinternetfile-class.md#read) kullanmalıdır.

*DwFlags* FILE_TRANSFER_TYPE_ASCII, dosya verisi çevirisi de denetim ve biçimlendirme karakterlerini Windows eşdeğerlerine dönüştürür. Varsayılan aktarım, dosyanın sunucuda depolandıkları biçimde indirileceği ikili moddur.

Hem *Pstryereldosya* hem de *pstryereldosya* , geçerli dizine göre kısmen nitelenmiş dosya adları veya tam nitelikli olabilir. Bir ters eğik çizgi ( \\ ) veya eğik çizgi (/), her iki ad için de dizin ayırıcı olarak kullanılabilir. `GetFile` Dizin adı ayırıcıları kullanılmadan önce uygun karakterlere çevirir.

Bağlam tanımlayıcısını seçtiğiniz bir değere ayarlamak için *dwContext* varsayılanını geçersiz kılın. Bağlam tanımlayıcısı, `CFtpConnection` [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesi tarafından oluşturulan nesnenin bu özel işlemiyle ilişkilidir. Değer, tanımlandıkları işlemde durum sağlamak için [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) değerine döndürülür. Bağlam tanımlayıcısı hakkında daha fazla bilgi için [Internet Ilk adımlar: WinINet](../../mfc/wininet-basics.md) makalesine bakın.

## <a name="cftpconnectionopenfile"></a><a name="openfile"></a> CFtpConnection:: OpenFile

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

`OpenFile` Aşağıdaki durumlarda kullanılmalıdır:

- Bir uygulamanın, gönderilmesi ve FTP sunucusunda bir dosya olarak oluşturulması gereken verileri vardır, ancak bu veriler yerel bir dosyada yer alır. `OpenFile`Bir dosya açıldığında, uygulama, FTP dosya verilerini sunucuya göndermek Için [CInternetFile:: Write](../../mfc/reference/cinternetfile-class.md#write) ' u kullanır.

- Bir uygulamanın sunucudan bir dosya alması ve uygulamayı diske yazmak yerine uygulama denetimli belleğe yerleştirmeli. Uygulama, dosyayı açmak için kullandıktan sonra [CInternetFile:: Read](../../mfc/reference/cinternetfile-class.md#read) öğesini kullanır `OpenFile` .

- Bir uygulama, bir dosya aktarımı üzerinde ince denetim düzeyine ihtiyaç duyuyor. Örneğin, uygulama bir işlem denetimini bir dosya indirilirken dosya aktarım durumunun ilerlemesini göstermek isteyebilir.

Çağırarak `OpenFile` ve çağrıldıktan sonra `CInternetConnection::Close` , uygulama yalnızca [CInternetFile:: Read](../../mfc/reference/cinternetfile-class.md#read), [CInternetFile:: Write](../../mfc/reference/cinternetfile-class.md#write), `CInternetConnection::Close` veya [CFtpFileFind:: FindFile](../../mfc/reference/cftpfilefind-class.md#findfile)çağırabilir. Aynı FTP oturumu için diğer FTP işlevlerine yapılan çağrılar başarısız olur ve hata kodunu FTP_ETRANSFER_IN_PROGRESS olarak ayarlar.

*PstrFileName* parametresi, geçerli dizine göre kısmen nitelenmiş bir dosya adı veya tam nitelikli bir dosya adı olabilir. Bir ters eğik çizgi ( \\ ) veya eğik çizgi (/), her iki ad için de dizin ayırıcı olarak kullanılabilir. `OpenFile` Dizin adı ayırıcıları kullanmadan önce uygun karakterlere çevirir.

Bağlam tanımlayıcısını seçtiğiniz bir değere ayarlamak için *dwContext* varsayılanını geçersiz kılın. Bağlam tanımlayıcısı, `CFtpConnection` [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesi tarafından oluşturulan nesnenin bu özel işlemiyle ilişkilidir. Değer, tanımlandıkları işlemde durum sağlamak için [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) değerine döndürülür. Bağlam tanımlayıcısı hakkında daha fazla bilgi için [Internet Ilk adımlar: WinINet](../../mfc/wininet-basics.md) makalesine bakın.

## <a name="cftpconnectionputfile"></a><a name="putfile"></a> CFtpConnection::P utFile

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

`PutFile` , bir FTP sunucusunda bir dosya depolanarak ilişkili tüm işlemleri işleyen yüksek düzey bir yordamdır. Yalnızca veri gönderen veya dosya aktarımı üzerinde daha yakından denetim gerektiren uygulamalar [OpenFile](#openfile) ve [CInternetFile:: Write](../../mfc/reference/cinternetfile-class.md#write)kullanmalıdır.

`dwContext`Bağlam tanımlayıcısını seçtiğiniz bir değere ayarlamak için varsayılanı geçersiz kılın. Bağlam tanımlayıcısı, `CFtpConnection` [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesi tarafından oluşturulan nesnenin bu özel işlemiyle ilişkilidir. Değer, tanımlandıkları işlemde durum sağlamak için [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) değerine döndürülür. Bağlam tanımlayıcısı hakkında daha fazla bilgi için [Internet Ilk adımlar: WinINet](../../mfc/wininet-basics.md) makalesine bakın.

## <a name="cftpconnectionremove"></a><a name="remove"></a> CFtpConnection:: Remove

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

*PstrFileName* parametresi, geçerli dizine göre kısmen nitelenmiş bir dosya adı veya tam nitelikli bir dosya adı olabilir. Bir ters eğik çizgi ( \\ ) veya eğik çizgi (/), her iki ad için de dizin ayırıcı olarak kullanılabilir. `Remove`İşlevi, kullanılmadan önce dizin adı ayırıcıları uygun karakterlere dönüştürür.

## <a name="cftpconnectionremovedirectory"></a><a name="removedirectory"></a> CFtpConnection:: RemoveDirectory

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

*PstrDirName* parametresi, geçerli dizine göre kısmen veya tam nitelenmiş bir dosya adı olabilir. Bir ters eğik çizgi ( \\ ) veya eğik çizgi (/), her iki ad için de dizin ayırıcı olarak kullanılabilir. `RemoveDirectory` Dizin adı ayırıcıları kullanılmadan önce uygun karakterlere çevirir.

## <a name="cftpconnectionrename"></a><a name="rename"></a> CFtpConnection:: Rename

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

*PstrExisting* ve *pstrNew* parametreleri, geçerli dizine göre kısmen nitelenmiş bir dosya adı ya da tam nitelikli bir dosya adı olabilir. Bir ters eğik çizgi ( \\ ) veya eğik çizgi (/), her iki ad için de dizin ayırıcı olarak kullanılabilir. `Rename` Dizin adı ayırıcıları kullanılmadan önce uygun karakterlere çevirir.

## <a name="cftpconnectionsetcurrentdirectory"></a><a name="setcurrentdirectory"></a> CFtpConnection:: SetCurrentDirectory

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

*PstrDirName* parametresi, geçerli dizine göre kısmen veya tam nitelenmiş bir dosya adı olabilir. Bir ters eğik çizgi ( \\ ) veya eğik çizgi (/), her iki ad için de dizin ayırıcı olarak kullanılabilir. `SetCurrentDirectory` Dizin adı ayırıcıları kullanılmadan önce uygun karakterlere çevirir.

FTP sunucusunun geçerli çalışma dizinini öğrenmek için [GetCurrentDirectory](#getcurrentdirectory) kullanın. Uzak sistemin sizi kök dizine bağladığını varsayın.

## <a name="see-also"></a>Ayrıca bkz.

[CInternetConnection sınıfı](../../mfc/reference/cinternetconnection-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CInternetConnection sınıfı](../../mfc/reference/cinternetconnection-class.md)<br/>
[CInternetSession sınıfı](../../mfc/reference/cinternetsession-class.md)
