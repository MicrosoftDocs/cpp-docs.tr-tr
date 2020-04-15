---
title: CFtpConnection Sınıfı
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
ms.openlocfilehash: a1fe516869aa98cc291597211eee175ef591e45d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373771"
---
# <a name="cftpconnection-class"></a>CFtpConnection Sınıfı

FTP bağlantınızı bir Internet sunucusuna yönetir ve bu sunucudaki dizinlerin ve dosyaların doğrudan manipülasyonuna izin verir.

## <a name="syntax"></a>Sözdizimi

```
class CFtpConnection : public CInternetConnection
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CFtpConnection::CFtpBağlantı](#cftpconnection)|Bir `CFtpConnection` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CFtpConnection::Komut](#command)|Bir komutu doğrudan FTP sunucusuna gönderir.|
|[CFtpConnection::CreateDirectory](#createdirectory)|Sunucuda bir dizin oluşturur.|
|[CFtpConnection::GetCurrentDirectory](#getcurrentdirectory)|Bu bağlantı için geçerli dizini alır.|
|[CFtpConnection::GetCurrentDirectoryAsURL](#getcurrentdirectoryasurl)|Bu bağlantının geçerli dizinini URL olarak alır.|
|[CFtpConnection::GetFile](#getfile)|Bağlı sunucudan dosya alır|
|[CFtpConnection::OpenFile](#openfile)|Bağlı sunucuda bir dosya açar.|
|[CFtpConnection::PutFile](#putfile)|Sunucuya bir dosya yerleştirir.|
|[CFtpConnection::Kaldır](#remove)|Bir dosyayı sunucudan kaldırır.|
|[CFtpConnection::RemoveDirectory](#removedirectory)|Belirtilen dizini sunucudan kaldırır.|
|[CFtpConnection::Yeniden adlandır](#rename)|Sunucudaki bir dosyayı yeniden adlandırır.|
|[CFtpConnection::SetCurrentDirectory](#setcurrentdirectory)|Geçerli FTP dizinini ayarlar.|

## <a name="remarks"></a>Açıklamalar

FTP, MFC WinInet sınıfları tarafından tanınan üç Internet hizmetinden biridir.

FTP Internet sunucusuyla iletişim kurmak için önce [CInternetSession'ın](../../mfc/reference/cinternetsession-class.md)bir `CFtpConnection` örneğini oluşturmanız ve ardından bir nesne oluşturmanız gerekir. Hiçbir `CFtpConnection` nesneyi doğrudan oluşturmazsınız; bunun yerine, [CInternetSession'ı arayın::Nesneyi](../../mfc/reference/cinternetsession-class.md#getftpconnection) `CFtpConnection` oluşturan ve işaretçisini döndüren GetFtpConnection' ı arayın.

Diğer MFC `CFtpConnection` Internet sınıfları ile nasıl çalıştığı hakkında daha fazla bilgi edinmek için [WinInet ile internet programlama](../../mfc/win32-internet-extensions-wininet.md)makalesine bakın. Desteklenen diğer iki hizmet olan HTTP ve gopher ile iletişim kurma hakkında daha fazla bilgi için [CHttpConnection](../../mfc/reference/chttpconnection-class.md) ve [CGopherConnection](../../mfc/reference/cgopherconnection-class.md)sınıflarını görün.

## <a name="example"></a>Örnek

  [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) sınıfına genel bakış örneği görün.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Cınternetconnection](../../mfc/reference/cinternetconnection-class.md)

`CFtpConnection`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxinet.h

## <a name="cftpconnectioncftpconnection"></a><a name="cftpconnection"></a>CFtpConnection::CFtpBağlantı

Bu üye işlev bir `CFtpConnection` nesne oluşturmak için çağrılır.

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

*pOturum*<br/>
İlgili [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesinin işaretçisi.

*hBağlı*<br/>
Geçerli Internet oturumunun Windows tutamacı.

*pstrServer*<br/>
FTP sunucu adını içeren bir dize için bir işaretçi.

*dwBağlam*<br/>
İşlem için bağlam tanımlayıcısı. *dwContext,* CInternetSession tarafından döndürülen operasyonun durum bilgilerini [tanımlar::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback). Varsayılan değer 1 olarak ayarlanır; ancak, işlem için açıkça belirli bir bağlam kimliği atayabilirsiniz. Nesne ve yaptığı herhangi bir çalışma bu bağlam kimliği ile ilişkilendirilecektir.

*pstrUserName*<br/>
Oturum açmak için kullanıcının adını belirten null-sonlandırılan dize işaretçi. NULL ise, varsayılan adsızdır.

*pstrPassword*<br/>
Oturum açmak için kullanılacak parolayı belirten, geçersiz sonlandırılmış bir dize için işaretçi. Hem *pstrPassword* hem de *pstrUserName* NULL ise, varsayılan anonim parola kullanıcının e-posta adıdır. *pstrPassword* NULL (veya boş bir dize) ancak *pstrUserName* NULL değilse, boş bir parola kullanılır. Aşağıdaki *tabloda pstrUserName* ve *pstrPassword*dört olası ayarları için davranış açıklanır:

|*pstrUserName*|*pstrPassword*|FTP sunucusuna gönderilen kullanıcı adı|FTP sunucusuna gönderilen parola|
|--------------------|--------------------|---------------------------------|---------------------------------|
|NULL veya " "|NULL veya " "|"anonim"|Kullanıcının e-posta adı|
|Null Olmayan Dize|NULL veya " "|*pstrUserName*|" "|
|NULL Non-NULL Dize|HATA|HATA||
|Null Olmayan Dize|Null Olmayan Dize|*pstrUserName*|*pstrPassword*|

*nPort*<br/>
Sunucuda kullanılacak TCP/IP bağlantı noktasını tanımlayan bir sayı.

*bPasif*<br/>
Bu FTP oturumu için pasif veya etkin modu belirtir. TRUE olarak ayarlanırsa, Win32 API *dwFlag'ı* INTERNET_FLAG_PASSIVE ayarlar.

### <a name="remarks"></a>Açıklamalar

Hiçbir `CFtpConnection` nesneyi doğrudan oluşturmazsınız. Bunun yerine, [CInternetSession'ı arayın::Nesneyi oluşturan GetFtpConnection'](../../mfc/reference/cinternetsession-class.md#getftpconnection)ı `CFptConnection` arayın.

## <a name="cftpconnectioncommand"></a><a name="command"></a>CFtpConnection::Komut

Bir komutu doğrudan FTP sunucusuna gönderir.

```
CInternetFile* Command(
    LPCTSTR pszCommand,
    CmdResponseType eResponse = CmdRespNone,
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Parametreler

*pszCommand*<br/>
Gönderilecek komutu içeren bir dize için bir işaretçi.

*eResponse*<br/>
FTP sunucusundan yanıt beklenip beklenmediğini belirtir. Aşağıdaki değerlerden biri olabilir:

- `CmdRespNone`Yanıt beklenmiyor.
- `CmdRespRead`Bir yanıt bekleniyor.
- `CmdRespWrite`Kullanılmaz.

CmdResponseType, *afxinet.h'de*tanımlanan CFtpConnection'ın bir üyesidir.

*Dwflags*<br/>
Bu işlevi denetleyen bayrakları içeren bir değer. Tam liste için [FTPCommand'a](/windows/win32/api/wininet/nf-wininet-ftpcommandw)bakın.

*dwBağlam*<br/>
Geri aramalarda uygulama bağlamını tanımlamak için kullanılan uygulama tanımlı bir değer içeren bir değer için işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, Windows SDK'da açıklandığı gibi [FTPCommand](/windows/win32/api/wininet/nf-wininet-ftpcommandw) işlevinitaklit eder.

Bir hata oluşursa, MFC [CInternetException](../../mfc/reference/cinternetexception-class.md)türünden bir özel durum oluşturur.

## <a name="cftpconnectioncreatedirectory"></a><a name="createdirectory"></a>CFtpConnection::CreateDirectory

Bağlı sunucuda bir dizin oluşturmak için bu üye işlevi arayın.

```
BOOL CreateDirectory(LPCTSTR pstrDirName);
```

### <a name="parameters"></a>Parametreler

*pstrDirName*<br/>
Oluşturulacak dizinin adını içeren bir dize işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0. Arama başarısız olursa, hatanın nedenini belirlemek için Windows işlevi [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) çağrılabilir.

### <a name="remarks"></a>Açıklamalar

Sunucuya bu bağlantı için geçerli çalışma dizini belirlemek için kullanın. `GetCurrentDirectory` Uzak sistemin sizi kök dizine bağladığını düşünmeyin.

Parametre, `pstrDirName` geçerli dizine göre kısmen veya tam nitelikli bir dosya adı olabilir. Bir ters\\çizgi ( ) veya ileri eğik çizgi (/) her iki ad için dizin ayırıcı olarak kullanılabilir. `CreateDirectory`dizin adı ayırıcılarını kullanılmadan önce uygun karakterlere çevirir.

## <a name="cftpconnectiongetcurrentdirectory"></a><a name="getcurrentdirectory"></a>CFtpConnection::GetCurrentDirectory

Geçerli dizinin adını almak için bu üye işlevi arayın.

```
BOOL GetCurrentDirectory(CString& strDirName) const;

BOOL GetCurrentDirectory(
    LPTSTR pstrDirName,
    LPDWORD lpdwLen) const;
```

### <a name="parameters"></a>Parametreler

*strDirName*<br/>
Dizinin adını alacak bir dize için bir başvuru.

*pstrDirName*<br/>
Dizinin adını alacak bir dize için bir işaretçi.

*lpdwLen*<br/>
Aşağıdaki bilgileri içeren bir DWORD işaretçisi:

|||
|-|-|
|Girişte|*pstrDirName*tarafından başvurulan arabelleğin boyutu.|
|Dönüşte|*pstrDirName*için depolanan karakter sayısı. Üye işlev başarısız olursa ve ERROR_INSUFFICIENT_BUFFER döndürülürse, *lpdwLen,* dizeyi almak için uygulamanın ayırması gereken bayt sayısını içerir.|

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0. Arama başarısız olursa, hatanın nedenini belirlemek için Win32 işlevi [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) çağrılabilir.

### <a name="remarks"></a>Açıklamalar

Bunun yerine dizin adını URL olarak almak için [GetCurrentDirectoryAsURL'yi](#getcurrentdirectoryasurl)arayın.

*PstrDirName* veya *strDirName* parametreleri, geçerli dizine göre kısmen nitelikli dosya adları veya tam nitelikli olabilir. Bir ters\\çizgi ( ) veya ileri eğik çizgi (/) her iki ad için dizin ayırıcı olarak kullanılabilir. `GetCurrentDirectory`dizin adı ayırıcılarını kullanılmadan önce uygun karakterlere çevirir.

## <a name="cftpconnectiongetcurrentdirectoryasurl"></a><a name="getcurrentdirectoryasurl"></a>CFtpConnection::GetCurrentDirectoryAsURL

Geçerli dizinin adını URL olarak almak için bu üye işlevini arayın.

```
BOOL GetCurrentDirectoryAsURL(CString& strDirName) const;

BOOL GetCurrentDirectoryAsURL(
    LPTSTR pstrName,
    LPDWORD lpdwLen) const;
```

### <a name="parameters"></a>Parametreler

*strDirName*<br/>
Dizinin adını alacak bir dize için bir başvuru.

*pstrDirName*<br/>
Dizinin adını alacak bir dize için bir işaretçi.

*lpdwLen*<br/>
Aşağıdaki bilgileri içeren bir DWORD işaretçisi:

|||
|-|-|
|Girişte|*pstrDirName*tarafından başvurulan arabelleğin boyutu.|
|Dönüşte|*pstrDirName*için depolanan karakter sayısı. Üye işlev başarısız olursa ve ERROR_INSUFFICIENT_BUFFER döndürülürse, *lpdwLen,* dizeyi almak için uygulamanın ayırması gereken bayt sayısını içerir.|

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0. Arama başarısız olursa, hatanın nedenini belirlemek için Win32 işlevi [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) çağrılabilir.

### <a name="remarks"></a>Açıklamalar

`GetCurrentDirectoryAsURL`[GetCurrentDirectory](#getcurrentdirectory) ile aynı şekilde

Parametre *strDirName,* geçerli dizine göre kısmen nitelikli dosya adları veya tam nitelikli olabilir. Bir ters\\çizgi ( ) veya ileri eğik çizgi (/) her iki ad için dizin ayırıcı olarak kullanılabilir. `GetCurrentDirectoryAsURL`dizin adı ayırıcılarını kullanılmadan önce uygun karakterlere çevirir.

## <a name="cftpconnectiongetfile"></a><a name="getfile"></a>CFtpConnection::GetFile

Bir FTP sunucusundan bir dosya almak ve yerel makinede depolamak için bu üye işlevi arayın.

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

*pstrRemoteFile*<br/>
FTP sunucusundan alınacak bir dosyanın adını içeren geçersiz sonlandırılmış dize için bir işaretçi.

*pstrLocalFile*<br/>
Yerel sistemde oluşturulacak dosyanın adını içeren null-sonlandırılan dize için bir işaretçi.

*bFailIfExists*<br/>
Dosya adının varolan bir dosya tarafından zaten kullanılıp kullanılmadığını gösterir. Yerel dosya adı zaten varsa ve bu parametre TRUE ise, `GetFile` başarısız olur. Aksi `GetFile` takdirde, dosyanın varolan kopyasını siler.

*dwÖzler*<br/>
Dosyanın özniteliklerini gösterir. Bu, aşağıdaki FILE_ATTRIBUTE_* bayrakların herhangi bir kombinasyonu olabilir.

- FILE_ATTRIBUTE_ARCHIVE Dosya bir arşiv dosyasıdır. Uygulamalar yedekleme veya kaldırma için dosyaları işaretlemek için bu özniteliği kullanır.

- FILE_ATTRIBUTE_COMPRESSED Dosya veya dizin sıkıştırılır. Bir dosya için sıkıştırma, dosyadaki tüm verilerin sıkıştırılmış olduğu anlamına gelir. Bir dizin için sıkıştırma, yeni oluşturulan dosyalar ve alt dizinler için varsayılan dır.

- FILE_ATTRIBUTE_DIRECTORY Dosya bir dizin.

- FILE_ATTRIBUTE_NORMAL Dosyanın başka öznitelikleri kümesi yoktur. Bu öznitelik yalnızca tek başına kullanıldığında geçerlidir. Diğer tüm dosya öznitelikleri FILE_ATTRIBUTE_NORMAL geçersiz kılar:

- FILE_ATTRIBUTE_HIDDEN Dosya gizlidir. Sıradan bir dizin listesine dahil edilmeyin.

- FILE_ATTRIBUTE_READONLY Dosya yalnızca okunur. Uygulamalar dosyayı okuyabilir, ancak dosyaya yazamaz veya silemez.

- FILE_ATTRIBUTE_SYSTEM Dosya yalnızca işletim sisteminin bir parçasıdır veya yalnızca bu sistem tarafından kullanılır.

- FILE_ATTRIBUTE_TEMPORARY Dosya geçici depolama için kullanılıyor. Başvurular sadece kesinlikle gerekli yse dosyaya yazılmalıdır. Dosya yakında silineceği için dosyanın verilerinin çoğu ortama atılmadan bellekte kalır.

*Dwflags*<br/>
Aktarımın hangi koşullar altında oluştuğunu belirtir. Bu parametre, Windows SDK'da [FtpGetFile'da](/windows/win32/api/wininet/nf-wininet-ftpgetfilew) açıklanan *dwFlags* değerlerinden herhangi biri olabilir.

*dwBağlam*<br/>
Dosya alma için bağlam tanımlayıcısı. *dwContext*hakkında daha fazla bilgi için **Açıklamalar'a** bakın.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0. Arama başarısız olursa, hatanın nedenini belirlemek için Win32 işlevi [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) çağrılabilir.

### <a name="remarks"></a>Açıklamalar

`GetFile`ftp sunucusundan bir dosyayı okuma ve yerel olarak depolama ile ilişkili tüm ek yükü işleyen üst düzey bir yordamdır. Yalnızca dosya verilerini alan veya dosya aktarımı üzerinde yakın denetim `OpenFile` gerektiren uygulamalar kullanmalıdır ve [CInternetFile::Bunun](../../mfc/reference/cinternetfile-class.md#read) yerine okuyun.

*dwFlags* FILE_TRANSFER_TYPE_ASCII ise, dosya verilerinin çevirisi de denetimi ve karakterleri Windows eşdeğerlerine biçimlendirebilir. Varsayılan aktarım, dosyanın sunucuda depolandığı aynı biçimde indirildiği ikili moddur.

Hem *pstrRemoteFile* hem de *pstrLocalFile,* geçerli dizine göre kısmen nitelikli dosya adları veya tam nitelikli olabilir. Bir ters\\çizgi ( ) veya ileri eğik çizgi (/) her iki ad için dizin ayırıcı olarak kullanılabilir. `GetFile`dizin adı ayırıcılarını kullanılmadan önce uygun karakterlere çevirir.

Bağlam tanımlayıcısını seçtiğiniz bir değere ayarlamak için *dwContext* varsayılanını geçersiz kılın. Bağlam tanımlayıcısı, [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesi tarafından `CFtpConnection` oluşturulan nesnenin bu özel çalışmasıyla ilişkilidir. Değer [CInternetSession döndürülür::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) ile tanımlanan işlem durumu sağlamak için. Makaleye bakın [Internet İlk Adımlar: WinInet](../../mfc/wininet-basics.md) bağlam tanımlayıcısı hakkında daha fazla bilgi için.

## <a name="cftpconnectionopenfile"></a><a name="openfile"></a>CFtpConnection::OpenFile

FtP sunucusunda bulunan bir dosyayı okumak veya yazmak için açmak için bu üye işlevini arayın.

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
Dosyaya nasıl erişileceğini belirler. ya GENERIC_READ ya da GENERIC_WRITE olabilir, ama her ikisi de değil.

*Dwflags*<br/>
Sonraki aktarımların hangi koşullar altında oluştuğunu belirtir. Bu, aşağıdaki FTP_TRANSFER_* sabitlerinden biri olabilir:

- FTP_TRANSFER_TYPE_ASCII FTP ASCII (Tip A) aktarım yöntemini kullanarak dosya aktarımları. Denetim ve biçimlendirme bilgilerini yerel eşdeğerlere dönüştürür.

- FTP_TRANSFER_TYPE_BINARY Dosya FTP'nin Resim (Tip I) aktarım yöntemini kullanarak veri aktarımı. Dosya, hiçbir değişiklik olmadan verileri tam olarak var olduğu gibi aktarMaktadır. Bu varsayılan aktarım yöntemidir.

*dwBağlam*<br/>
Dosyayı açmak için bağlam tanımlayıcısı. *dwContext*hakkında daha fazla bilgi için **Açıklamalar'a** bakın.

### <a name="return-value"></a>Dönüş Değeri

[CInternetFile](../../mfc/reference/cinternetfile-class.md) nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

`OpenFile`aşağıdaki durumlarda kullanılmalıdır:

- Bir uygulama, FTP sunucusunda dosya olarak gönderilmesi ve oluşturulması gereken verilere sahiptir, ancak bu veriler yerel bir dosyada değildir. Bir `OpenFile` dosyayı açtıktan sonra, uygulama [CInternetFile kullanır::FTP](../../mfc/reference/cinternetfile-class.md#write) dosya verilerini sunucuya göndermek için yazın.

- Bir uygulama, bir dosyayı diske yazmak yerine sunucudan alıp uygulama denetimli belleğe yerleştirmelidir. Uygulama [CInternetFile kullanır::Dosyayı](../../mfc/reference/cinternetfile-class.md#read) açmak için kullandıktan `OpenFile` sonra okuyun.

- Bir uygulamanın dosya aktarımı üzerinde ince bir denetim düzeyine ihtiyacı vardır. Örneğin, uygulama bir dosya indirirken dosya aktarım durumunun ilerlemesini gösteren bir ilerleme denetimi görüntülemek isteyebilirsiniz.

Aradıktan `OpenFile` sonra `CInternetConnection::Close`ve aradıktan sonra, uygulama sadece [CInternetFile arayabilirsiniz::Oku](../../mfc/reference/cinternetfile-class.md#read), [CInternetFile::Yaz](../../mfc/reference/cinternetfile-class.md#write), `CInternetConnection::Close`veya [CFtpFileFind::FindFile](../../mfc/reference/cftpfilefind-class.md#findfile). Aynı FTP oturumu için diğer FTP işlevlerine yapılan aramalar başarısız olur ve hata kodunu FTP_ETRANSFER_IN_PROGRESS olarak ayarlar.

*pstrFileName* parametresi, geçerli dizine göre kısmen nitelikli bir dosya adı veya tam nitelikli olabilir. Bir ters\\çizgi ( ) veya ileri eğik çizgi (/) her iki ad için dizin ayırıcı olarak kullanılabilir. `OpenFile`kullanmadan önce dizin adı ayırıcılarını uygun karakterlere çevirir.

Bağlam tanımlayıcısını seçtiğiniz bir değere ayarlamak için *dwContext* varsayılanını geçersiz kılın. Bağlam tanımlayıcısı, [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesi tarafından `CFtpConnection` oluşturulan nesnenin bu özel çalışmasıyla ilişkilidir. Değer [CInternetSession döndürülür::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) ile tanımlanan işlem durumu sağlamak için. Makaleye bakın [Internet İlk Adımlar: WinInet](../../mfc/wininet-basics.md) bağlam tanımlayıcısı hakkında daha fazla bilgi için.

## <a name="cftpconnectionputfile"></a><a name="putfile"></a>CFtpConnection::PutFile

Bir FTP sunucusunda bir dosya depolamak için bu üye işlevini arayın.

```
BOOL PutFile(
    LPCTSTR pstrLocalFile,
    LPCTSTR pstrRemoteFile,
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Parametreler

*pstrLocalFile*<br/>
Yerel sistemden gönderilecek dosyanın adını içeren bir dize işaretçisi.

*pstrRemoteFile*<br/>
FTP sunucusunda oluşturulacak dosyanın adını içeren bir dize işaretçisi.

*Dwflags*<br/>
Dosyanın aktarımının hangi koşullar altında oluştuğunu belirtir. [OpenFile'da](#openfile)açıklanan FTP_TRANSFER_* sabitlerden herhangi biri olabilir.

*dwBağlam*<br/>
Dosyayı yerleştirmek için bağlam tanımlayıcısı. *dwContext*hakkında daha fazla bilgi için **Açıklamalar'a** bakın.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0. Arama başarısız olursa, hatanın nedenini belirlemek için Win32 işlevi [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) çağrılabilir.

### <a name="remarks"></a>Açıklamalar

`PutFile`bir FTP sunucusunda bir dosyadepolama ile ilişkili tüm işlemleri işleyen üst düzey bir yordamdır. Yalnızca veri gönderen veya dosya aktarımı üzerinde daha yakından kontrol gerektiren uygulamalar [OpenFile](#openfile) ve [CInternetFile kullanmalıdır::Yaz.](../../mfc/reference/cinternetfile-class.md#write)

Bağlam tanımlayıcısını `dwContext` seçtiğiniz bir değere ayarlamak için varsayılanı geçersiz kılın. Bağlam tanımlayıcısı, [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesi tarafından `CFtpConnection` oluşturulan nesnenin bu özel çalışmasıyla ilişkilidir. Değer [CInternetSession döndürülür::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) ile tanımlanan işlem durumu sağlamak için. Makaleye bakın [Internet İlk Adımlar: WinInet](../../mfc/wininet-basics.md) bağlam tanımlayıcısı hakkında daha fazla bilgi için.

## <a name="cftpconnectionremove"></a><a name="remove"></a>CFtpConnection::Kaldır

Belirtilen dosyayı bağlı sunucudan silmek için bu üye işlevini arayın.

```
BOOL Remove(LPCTSTR pstrFileName);
```

### <a name="parameters"></a>Parametreler

*pstrFileName*<br/>
Kaldırılacak dosya adını içeren bir dize işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0. Arama başarısız olursa, hatanın nedenini belirlemek için Win32 işlevi [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) çağrılabilir.

### <a name="remarks"></a>Açıklamalar

*pstrFileName* parametresi, geçerli dizine göre kısmen nitelikli bir dosya adı veya tam nitelikli olabilir. Bir ters\\çizgi ( ) veya ileri eğik çizgi (/) her iki ad için dizin ayırıcı olarak kullanılabilir. İşlev, `Remove` dizin adı ayırıcılarını kullanılmadan önce uygun karakterlere çevirir.

## <a name="cftpconnectionremovedirectory"></a><a name="removedirectory"></a>CFtpConnection::RemoveDirectory

Belirtilen dizini bağlı sunucudan kaldırmak için bu üye işlevi arayın.

```
BOOL RemoveDirectory(LPCTSTR pstrDirName);
```

### <a name="parameters"></a>Parametreler

*pstrDirName*<br/>
Kaldırılacak dizin içeren bir dize için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0. Arama başarısız olursa, hatanın nedenini belirlemek için Win32 işlevi [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) çağrılabilir.

### <a name="remarks"></a>Açıklamalar

Sunucunun geçerli çalışma dizinini belirlemek için [GetCurrentDirectory'yi](#getcurrentdirectory) kullanın. Uzak sistemin sizi kök dizine bağladığını düşünmeyin.

*pstrDirName* parametresi, geçerli dizine göre kısmen veya tamamen nitelikli bir dosya adı olabilir. Bir ters\\çizgi ( ) veya ileri eğik çizgi (/) her iki ad için dizin ayırıcı olarak kullanılabilir. `RemoveDirectory`dizin adı ayırıcılarını kullanılmadan önce uygun karakterlere çevirir.

## <a name="cftpconnectionrename"></a><a name="rename"></a>CFtpConnection::Yeniden adlandır

Bağlı sunucuda belirtilen dosyayı yeniden adlandırmak için bu üye işlevini arayın.

```
BOOL Rename(
    LPCTSTR pstrExisting,
    LPCTSTR pstrNew);
```

### <a name="parameters"></a>Parametreler

*pstrMevcut*<br/>
Yeniden adlandırılacak dosyanın geçerli adını içeren bir dize işaretçisi.

*pstrYeni*<br/>
Dosyanın yeni adını içeren bir dize için işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0. Arama başarısız olursa, hatanın nedenini belirlemek için Win32 işlevi [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) çağrılabilir.

### <a name="remarks"></a>Açıklamalar

*PstrExisting* ve *pstrNew parametreleri,* geçerli dizine göre kısmen nitelikli veya tam nitelikli bir dosya adı olabilir. Bir ters\\çizgi ( ) veya ileri eğik çizgi (/) her iki ad için dizin ayırıcı olarak kullanılabilir. `Rename`dizin adı ayırıcılarını kullanılmadan önce uygun karakterlere çevirir.

## <a name="cftpconnectionsetcurrentdirectory"></a><a name="setcurrentdirectory"></a>CFtpConnection::SetCurrentDirectory

FTP sunucusunda farklı bir dizine değiştirmek için bu üye işlevini arayın.

```
BOOL SetCurrentDirectory(LPCTSTR pstrDirName);
```

### <a name="parameters"></a>Parametreler

*pstrDirName*<br/>
Dizinin adını içeren bir dize için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0. Arama başarısız olursa, hatanın nedenini belirlemek için Win32 işlevi [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) çağrılabilir.

### <a name="remarks"></a>Açıklamalar

*pstrDirName* parametresi, geçerli dizine göre kısmen veya tamamen nitelikli bir dosya adı olabilir. Bir ters\\çizgi ( ) veya ileri eğik çizgi (/) her iki ad için dizin ayırıcı olarak kullanılabilir. `SetCurrentDirectory`dizin adı ayırıcılarını kullanılmadan önce uygun karakterlere çevirir.

FtP sunucusunun geçerli çalışma dizinini belirlemek için [GetCurrentDirectory'yi](#getcurrentdirectory) kullanın. Uzak sistemin sizi kök dizine bağladığını düşünmeyin.

## <a name="see-also"></a>Ayrıca bkz.

[CInternetConnection Sınıfı](../../mfc/reference/cinternetconnection-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CInternetConnection Sınıfı](../../mfc/reference/cinternetconnection-class.md)<br/>
[CInternetSession Sınıfı](../../mfc/reference/cinternetsession-class.md)
