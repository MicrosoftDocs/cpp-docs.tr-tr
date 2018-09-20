---
title: CFtpConnection sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f3dce0efa8ced6e51557e4efc64b8c5f7441d662
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46422382"
---
# <a name="cftpconnection-class"></a>CFtpConnection sınıfı

Internet sunucusuyla olan FTP bağlantınızı yönetir ve dizinleri ve dosyaları bu sunucuda doğrudan işlenmesini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CFtpConnection : public CInternetConnection
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CFtpConnection::CFtpConnection](#cftpconnection)|Oluşturur bir `CFtpConnection` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CFtpConnection::Command](#command)|Bir komut doğrudan bir FTP sunucusuna gönderir.|
|[CFtpConnection::CreateDirectory](#createdirectory)|Sunucu üzerinde bir dizin oluşturur.|
|[CFtpConnection::GetCurrentDirectory](#getcurrentdirectory)|Bu bağlantı için geçerli dizini alır.|
|[CFtpConnection::GetCurrentDirectoryAsURL](#getcurrentdirectoryasurl)|URL olarak bu bağlantı için geçerli dizini alır.|
|[CFtpConnection::GetFile](#getfile)|Bağlı sunucudan bir dosya alır|
|[CFtpConnection::OpenFile](#openfile)|Bağlı sunucuda bir dosya açar.|
|[CFtpConnection::PutFile](#putfile)|Sunucu bir dosyaya yerleştirir.|
|[CFtpConnection::Remove](#remove)|Bir dosya sunucusundan kaldırır.|
|[CFtpConnection::RemoveDirectory](#removedirectory)|Belirtilen dizin sunucuda kaldırır.|
|[CFtpConnection::Rename](#rename)|Sunucudaki bir dosyayı yeniden adlandırır.|
|[CFtpConnection::SetCurrentDirectory](#setcurrentdirectory)|Geçerli FTP dizininin ayarlar.|

## <a name="remarks"></a>Açıklamalar

FTP MFC WinINet sınıfları tarafından tanınan üç Internet Hizmetleri biridir.

Bir FTP Internet sunucusuyla iletişim kurmak için öncelikle bir örneğini oluşturmanız gerekir [Cınternetsession](../../mfc/reference/cinternetsession-class.md)ve ardından bir `CFtpConnection` nesne. Asla oluşturma bir `CFtpConnection` doğrudan nesne; bunun yerine, çağırarak [CInternetSession::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection), oluşturan `CFtpConnection` nesnesi ve bir işaretçi döndürür.

Hakkında daha fazla bilgi edinmek için `CFtpConnection` diğer Internet MFC sınıfları ile çalışır, başlıklı makaleye bakın [Winınet'in Internet programlama](../../mfc/win32-internet-extensions-wininet.md). Desteklenen diğer iki ile Hizmetleri, HTTP ve gopher bkz sınıflar iletişim hakkında daha fazla bilgi için [CHttpConnection](../../mfc/reference/chttpconnection-class.md) ve [CGopherConnection](../../mfc/reference/cgopherconnection-class.md).

## <a name="example"></a>Örnek

  Örnekte bakın [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) sınıfına genel bakış.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CInternetConnection](../../mfc/reference/cinternetconnection-class.md)

`CFtpConnection`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxinet.h

##  <a name="cftpconnection"></a>  CFtpConnection::CFtpConnection

Bu üye işlevi oluşturmak için çağrılan bir `CFtpConnection` nesne.

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
İlgili bir işaretçiye [Cınternetsession](../../mfc/reference/cinternetsession-class.md) nesne.

*hConnected*<br/>
Geçerli Internet oturumu Windows tanıtıcısı.

*pstrServer*<br/>
FTP sunucusu adını içeren bir dize işaretçisi.

*dwContext*<br/>
İşlem bağlamı tanımlayıcısı. *dwContext* tarafından döndürülen işlem durumu bilgilerini tanımlayan [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback). Varsayılan değer 1 olarak ayarlanır; Ancak, belirli bir bağlam kimliği işlemi için açıkça atayabilirsiniz. Nesne ve mevcut herhangi bir iş, bir bağlam kimliği ile ilişkilendirilecek

*pstrUserName*<br/>
Oturum açmak için kullanıcı adını belirten bir null ile sonlandırılmış dize işaretçisi. NULL ise, anonim bir varsayılandır.

*pstrPassword*<br/>
Oturum açmak için kullanılacak parolayı belirten bir boş sonlandırılmış dizeye bir işaretçi. Her iki *pstrPassword* ve *pstrUserName* NULL, varsayılan anonim kullanıcı e-posta adını paroladır. Varsa *pstrPassword* boş (veya boş bir dize) ancak *pstrUserName* NULL değil boş bir parola kullanılır. Aşağıdaki tabloda dört olası ayarlarını davranışını açıklar *pstrUserName* ve *pstrPassword*:

|*pstrUserName*|*pstrPassword*|FTP sunucusuna gönderilen kullanıcı adı|FTP sunucusuna gönderilen parola|
|--------------------|--------------------|---------------------------------|---------------------------------|
|NULL veya ""|NULL veya ""|"anonim"|Kullanıcının e-posta adı|
|BOŞ olmayan bir dize|NULL veya ""|*pstrUserName*|" "|
|BOŞ bir NULL olmayan dize|HATA|HATA||
|BOŞ olmayan bir dize|BOŞ olmayan bir dize|*pstrUserName*|*pstrPassword*|

*nbağlantı noktası*<br/>
Sunucu üzerinde kullanılacak TCP/IP bağlantı noktasını tanımlayan bir sayı.

*bPassive*<br/>
Bu FTP oturumu için pasif veya etkin modunu belirtir. TRUE olarak ayarlanırsa, Win32 API kümelerini *dwFlag* INTERNET_FLAG_PASSIVE için.

### <a name="remarks"></a>Açıklamalar

Asla oluşturma bir `CFtpConnection` doğrudan nesne. Bunun yerine çağrı [CInternetSession::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection), oluşturan `CFptConnection` nesne.

##  <a name="command"></a>  CFtpConnection::Command

Bir komut doğrudan bir FTP sunucusuna gönderir.

```
CInternetFile* Command(
    LPCTSTR pszCommand,
    CmdResponseType eResponse = CmdRespNone,
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Parametreler

*pszCommand*<br/>
Gönderilecek komut içeren bir dize işaretçisi.

*eResponse*<br/>
FTP sunucusundan bir yanıt beklenen durum olup olmadığını belirler. Aşağıdaki değerlerden biri olabilir:

- `CmdRespNone` Yanıt bekleniyor.

- `CmdRespRead` Yanıt bekleniyor.

*CertOpenStore*<br/>
Bu işlev denetim bayrakları içeren bir değer. Tam bir listesi için bkz. [FTPCommand](/windows/desktop/api/wininet/nf-wininet-ftpcommanda).

*dwContext*<br/>
Geri çağırmaları uygulama bağlamında tanımlamak için kullanılan bir uygulama tanımlı değerini içeren bir değere bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi işlevselliğine öykünür [FTPCommand](/windows/desktop/api/wininet/nf-wininet-ftpcommanda) Windows SDK içinde anlatıldığı gibi işlev.

Bir hata oluşursa, MFC türünde bir özel durum oluşturur. [Cınternetexception](../../mfc/reference/cinternetexception-class.md).

##  <a name="createdirectory"></a>  CFtpConnection::CreateDirectory

Bağlı sunucuda bir dizin oluşturmak için bu üye işlevini çağırın.

```
BOOL CreateDirectory(LPCTSTR pstrDirName);
```

### <a name="parameters"></a>Parametreler

*pstrDirName*<br/>
Oluşturulacak dizinin adını içeren bir dize işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0. Windows işlev çağrı başarısız olursa [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) hatanın nedenini belirlemek için çağrılabilir.

### <a name="remarks"></a>Açıklamalar

Kullanım `GetCurrentDirectory` sunucusuyla Bu bağlantı için geçerli çalışma dizini belirlemek için. Uzak sistem kök dizine bağlandı varsaymayın.

`pstrDirName` Parametresi ya da olabilir bir kısmen ya da geçerli dizine göreli tam bir dosya adı. Ters eğik çizgi (\\) veya her iki adı dizin ayırıcı olarak eğik çizgi (/) kullanılabilir. `CreateDirectory` Bunlar kullanılmadan önce dizin adı ayırıcılar uygun karakterlere çevirir.

##  <a name="getcurrentdirectory"></a>  CFtpConnection::GetCurrentDirectory

Geçerli dizin adını almak için bu üye işlevini çağırın.

```
BOOL GetCurrentDirectory(CString& strDirName) const;

BOOL GetCurrentDirectory(
    LPTSTR pstrDirName,
    LPDWORD lpdwLen) const;
```

### <a name="parameters"></a>Parametreler

*strDirName*<br/>
Dizin adı alacak bir dize için bir başvuru.

*pstrDirName*<br/>
Dizin adı alacak bir dizeye bir işaretçi.

*lpdwLen*<br/>
Aşağıdaki bilgileri içeren bir DWORD işaretçi:

|||
|-|-|
|Girişi|Tarafından başvurulan arabellek boyutu *pstrDirName*.|
|Geri dönüş|Saklı karakter sayısını *pstrDirName*. Üye işlev başarısız olur ve ERROR_INSUFFICIENT_BUFFER döndürülür, ardından *lpdwLen* dizeyi almak için uygulama ayırmalısınız bayt sayısını içerir.|

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0. Çağrı başarısız olursa, Win32 işlevini [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) hatanın nedenini belirlemek için çağrılabilir.

### <a name="remarks"></a>Açıklamalar

Dizin adı yerine bir URL olarak almak için arama [GetCurrentDirectoryAsURL](#getcurrentdirectoryasurl).

Parametreleri *pstrDirName* veya *strDirName* tam olarak veya kısmen nitelenmiş ya da dosya adları geçerli dizine göreli olabilir. Ters eğik çizgi (\\) veya her iki adı dizin ayırıcı olarak eğik çizgi (/) kullanılabilir. `GetCurrentDirectory` Bunlar kullanılmadan önce dizin adı ayırıcılar uygun karakterlere çevirir.

##  <a name="getcurrentdirectoryasurl"></a>  CFtpConnection::GetCurrentDirectoryAsURL

URL olarak geçerli dizinin adını almak için bu üye işlevini çağırın.

```
BOOL GetCurrentDirectoryAsURL(CString& strDirName) const;

BOOL GetCurrentDirectoryAsURL(
    LPTSTR pstrName,
    LPDWORD lpdwLen) const;
```

### <a name="parameters"></a>Parametreler

*strDirName*<br/>
Dizin adı alacak bir dize için bir başvuru.

*pstrDirName*<br/>
Dizin adı alacak bir dizeye bir işaretçi.

*lpdwLen*<br/>
Aşağıdaki bilgileri içeren bir DWORD işaretçi:

|||
|-|-|
|Girişi|Tarafından başvurulan arabellek boyutu *pstrDirName*.|
|Geri dönüş|Saklı karakter sayısını *pstrDirName*. Üye işlev başarısız olur ve ERROR_INSUFFICIENT_BUFFER döndürülür, ardından *lpdwLen* dizeyi almak için uygulama ayırmalısınız bayt sayısını içerir.|

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0. Çağrı başarısız olursa, Win32 işlevini [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) hatanın nedenini belirlemek için çağrılabilir.

### <a name="remarks"></a>Açıklamalar

`GetCurrentDirectoryAsURL` gibi davranır [GetCurrentDirectory](#getcurrentdirectory)

Parametre *strDirName* tam olarak veya kısmen nitelenmiş ya da dosya adları geçerli dizine göreli olabilir. Ters eğik çizgi (\\) veya her iki adı dizin ayırıcı olarak eğik çizgi (/) kullanılabilir. `GetCurrentDirectoryAsURL` Bunlar kullanılmadan önce dizin adı ayırıcılar uygun karakterlere çevirir.

##  <a name="getfile"></a>  CFtpConnection::GetFile

Dosya bir FTP sunucusundan almak ve yerel makinede depolamak için bu üye işlevini çağırın.

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
FTP sunucusundan almak için bir dosya adını içeren bir boş sonlandırılmış dizeye bir işaretçi.

*pstrLocalFile*<br/>
Yerel sistemde oluşturulacak dosyanın adını içeren bir boş sonlandırılmış dizeye bir işaretçi.

*bFailIfExists*<br/>
Dosya adı tarafından mevcut bir dosyayı zaten kullanılabilir olup olmadığını gösterir. Yerel dosya adı zaten var ve bu parametre TRUE ise `GetFile` başarısız olur. Aksi takdirde, `GetFile` dosyanın mevcut kopyalama silecektir.

*dwAttributes*<br/>
Dosyanın özniteliklerini gösterir. Bu, aşağıdaki FILE_ATTRIBUTE_ * bayrakları herhangi bir birleşimi olabilir.

- FILE_ATTRIBUTE_ARCHIVE dosyanın bir arşiv dosyasıdır. Uygulama, yedekleme veya kaldırma için dosyaları işaretlemek için bu öznitelik kullanın.

- Dosya veya dizin FILE_ATTRIBUTE_COMPRESSED sıkıştırılır. Bir dosya için sıkıştırma sıkıştırılmış dosyasındaki verilerin tümünü anlamına gelir. Bir dizin için sıkıştırma yeni oluşturulan dosyaları ve alt dizinleri için varsayılandır.

- FILE_ATTRIBUTE_DIRECTORY dosyanın bir dizindir.

- FILE_ATTRIBUTE_NORMAL dosya kümesi özniteliklere sahip değildir. Bu öznitelik, yalnızca tek başına kullanıldığında geçerlidir. Diğer tüm dosya özniteliklerini FILE_ATTRIBUTE_NORMAL geçersiz kıl:

- Soubor je skrytý FILE_ATTRIBUTE_HIDDEN. Bir sıradan bir dizin listesindeki dahil edilmemesi aittir.

- FILE_ATTRIBUTE_READONLY dosyanın salt okunur. Uygulamaların dosya okuyabilen ancak olamaz yazma veya silin.

- FILE_ATTRIBUTE_SYSTEM dosya parçası veya özel olarak işletim sistemi tarafından kullanılır.

- FILE_ATTRIBUTE_TEMPORARY dosyayı geçici depolama için kullanılır. Uygulamalar, yalnızca kesinlikle gerekli olduğunda dosyaya yazmanız gerekir. Dosyanın verilerden en iyi şekilde dosyayı yakında silinecek ortam temizlendi nedeni olmadan bellekte kalır.

*CertOpenStore*<br/>
Aktarım oluştuğu koşulları belirtir. Bu parametre herhangi biri olabilir *CertOpenStore* değerleri açıklanan [FtpGetFile](/windows/desktop/api/wininet/nf-wininet-ftpgetfilea) Windows SDK.

*dwContext*<br/>
Dosya alma bağlamı tanımlayıcısı. Bkz: **açıklamalar** hakkında daha fazla bilgi için *dwContext*.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0. Çağrı başarısız olursa, Win32 işlevini [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) hatanın nedenini belirlemek için çağrılabilir.

### <a name="remarks"></a>Açıklamalar

`GetFile` bir FTP sunucusundan bir dosyayı okuma ve yerel depolama ile ilgili ek yükü tüm işler üst düzey bir yordamdır. Dosya verileri yalnızca almak veya dosya aktarımı Kapat denetime gerektiren uygulamaların kullanması gereken `OpenFile` ve [CInternetFile::Read](../../mfc/reference/cinternetfile-class.md#read) yerine.

Varsa *CertOpenStore* FILE_TRANSFER_TYPE_ASCII, dosya verilerinin çeviri de dönüştürür denetimi ve Windows eşdeğerleri karakterlere biçimlendirme. Varsayılan aktarım ikili, sunucuda depolanan dosya aynı biçimde indirildiği modudur.

Her ikisi de *pstrRemoteFile* ve *pstrLocalFile* tam olarak veya kısmen nitelenmiş ya da dosya adları geçerli dizine göreli olabilir. Ters eğik çizgi (\\) veya her iki adı dizin ayırıcı olarak eğik çizgi (/) kullanılabilir. `GetFile` Bunlar kullanılmadan önce dizin adı ayırıcılar uygun karakterlere çevirir.

Geçersiz kılma *dwContext* varsayılan bağlamı tanımlayıcısını bir değere ayarlamak için. Bu belirli işlemle ilişkili bağlam tanımlayıcıdır `CFtpConnection` tarafından oluşturulan nesne kendi [Cınternetsession](../../mfc/reference/cinternetsession-class.md) nesne. İçin döndürülen değer [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) ile belirtilen işlem durumu sağlamak için. Makaleye göz atın [Internet ilk adımlar: WinINet](../../mfc/wininet-basics.md) bağlam tanımlayıcısı hakkında daha fazla bilgi.

##  <a name="openfile"></a>  CFtpConnection::OpenFile

Okuma veya yazma için bir FTP sunucusunda bulunan bir dosyayı açmak için bu üye işlevini çağırın.

```
CInternetFile* OpenFile(
    LPCTSTR pstrFileName,
    DWORD dwAccess = GENERIC_READ,
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Parametreler

*pstrFileName*<br/>
Açılması için dosyanın adını içeren bir dize işaretçisi.

*dwAccess*<br/>
Dosyanın nasıl erişileceğini belirler. GENERIC_READ veya GENERIC_WRITE ancak ikisini birden olamaz.

*CertOpenStore*<br/>
Sonraki aktarımları altında oluşabilen koşulları belirtir. Bu aşağıdaki FTP_TRANSFER_ * sabitlerden biri olabilir:

- FTP_TRANSFER_TYPE_ASCII dosyanın, FTP ASCII (tür A) aktarım yöntemi kullanılarak aktarılır. Ve biçimlendirme bilgileri yerel eşdeğerlerine dönüştürür denetimi.

- Dosya FTP_TRANSFER_TYPE_BINARY FTP's görüntü (tür ı) aktarım yöntemi kullanarak verileri aktarır. Tam olarak dosya aktarımları veri değişikliğine gerek yok. Varsayılan aktarım yöntem budur.

*dwContext*<br/>
Dosyayı açmak için bağlam tanımlayıcısı. Bkz: **açıklamalar** hakkında daha fazla bilgi için *dwContext*.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir [Cınternetfile](../../mfc/reference/cinternetfile-class.md) nesne.

### <a name="remarks"></a>Açıklamalar

`OpenFile` Aşağıdaki durumlarda kullanılmalıdır:

- Bir uygulama, verileri bir yerel dosyada değil ancak bu, gönderilen ve FTP sunucusundaki bir dosya olarak oluşturulan gereken veri sahiptir. Bir kez `OpenFile` uygulamanız tarafından kullanılan bir dosya açar [CInternetFile::Write](../../mfc/reference/cinternetfile-class.md#write) FTP dosya verilerini sunucuya gönderilecek.

- Bir uygulama, bir dosya sunucusundan almak ve diske yazmak yerine uygulama tarafından denetlenen bellek yerleştirin. Uygulamanın kullandığı [CInternetFile::Read](../../mfc/reference/cinternetfile-class.md#read) kullandıktan sonra `OpenFile` dosyayı açmak için.

- Bir uygulamanın ince bir dosya aktarımı üzerinden denetim düzeyi gerekir. Örneğin, uygulama bir ilerleme durumunu görüntülemek isteyebilirsiniz denetimi bir dosya indirilirken Dosya Aktarım durumu ilerlemesini gösterir.

Arama sonra `OpenFile` ve arama kadar `CInternetConnection::Close`, uygulamayı yalnızca çağırabilirsiniz [CInternetFile::Read](../../mfc/reference/cinternetfile-class.md#read), [CInternetFile::Write](../../mfc/reference/cinternetfile-class.md#write), `CInternetConnection::Close`, veya [ CFtpFileFind::FindFile](../../mfc/reference/cftpfilefind-class.md#findfile). Diğer aynı FTP oturumu FTP işlevlere yapılan çağrıları başarısız olur ve hata kodu için FTP_ETRANSFER_IN_PROGRESS ayarlayın.

*PstrFileName* parametresi ya da kısmen nitelenmiş dosya adını geçerli dizine göreli veya tam olabilir. Ters eğik çizgi (\\) veya her iki adı dizin ayırıcı olarak eğik çizgi (/) kullanılabilir. `OpenFile` kullanmadan önce dizin adı ayırıcılar uygun karakterlere çevirir.

Geçersiz kılma *dwContext* varsayılan bağlamı tanımlayıcısını bir değere ayarlamak için. Bu belirli işlemle ilişkili bağlam tanımlayıcıdır `CFtpConnection` tarafından oluşturulan nesne kendi [Cınternetsession](../../mfc/reference/cinternetsession-class.md) nesne. İçin döndürülen değer [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) ile belirtilen işlem durumu sağlamak için. Makaleye göz atın [Internet ilk adımlar: WinINet](../../mfc/wininet-basics.md) bağlam tanımlayıcısı hakkında daha fazla bilgi.

##  <a name="putfile"></a>  CFtpConnection::PutFile

Bir FTP sunucusuna dosya depolamak için bu üye işlevini çağırın.

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

*CertOpenStore*<br/>
Dosya aktarımını oluştuğu koşulları belirtir. Açıklanan FTP_TRANSFER_ * sabitlerin olabilir [Openfıle](#openfile).

*dwContext*<br/>
Dosya yerleştirme içerik tanımlayıcısı. Bkz: **açıklamalar** hakkında daha fazla bilgi için *dwContext*.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0. Çağrı başarısız olursa, Win32 işlevini [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) hatanın nedenini belirlemek için çağrılabilir.

### <a name="remarks"></a>Açıklamalar

`PutFile` tüm FTP sunucusunda dosya depolamanın işlemlerini işler üst düzey bir yordamdır. Veri yalnızca gönderme veya üzerinden dosya aktarımı daha yakından denetleyebilme gerektiren uygulamaların kullanması gereken [Openfıle](#openfile) ve [CInternetFile::Write](../../mfc/reference/cinternetfile-class.md#write).

Geçersiz kılma `dwContext` varsayılan bağlamı tanımlayıcısını bir değere ayarlamak için. Bu belirli işlemle ilişkili bağlam tanımlayıcıdır `CFtpConnection` tarafından oluşturulan nesne kendi [Cınternetsession](../../mfc/reference/cinternetsession-class.md) nesne. İçin döndürülen değer [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) ile belirtilen işlem durumu sağlamak için. Makaleye göz atın [Internet ilk adımlar: WinINet](../../mfc/wininet-basics.md) bağlam tanımlayıcısı hakkında daha fazla bilgi.

##  <a name="remove"></a>  CFtpConnection::Remove

Belirtilen dosya bağlı sunucusunu silmek için bu üye işlevini çağırın.

```
BOOL Remove(LPCTSTR pstrFileName);
```

### <a name="parameters"></a>Parametreler

*pstrFileName*<br/>
Kaldırmak için dosya adını içeren bir dize işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0. Çağrı başarısız olursa, Win32 işlevini [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) hatanın nedenini belirlemek için çağrılabilir.

### <a name="remarks"></a>Açıklamalar

*PstrFileName* parametresi ya da kısmen nitelenmiş dosya adını geçerli dizine göreli veya tam olabilir. Ters eğik çizgi (\\) veya her iki adı dizin ayırıcı olarak eğik çizgi (/) kullanılabilir. `Remove` İşlevi kullanmadan önce dizin adı ayırıcılar uygun karakterlere çevirir.

##  <a name="removedirectory"></a>  CFtpConnection::RemoveDirectory

Belirtilen dizin bağlı sunucudan kaldırmak için bu üye işlevini çağırın.

```
BOOL RemoveDirectory(LPCTSTR pstrDirName);
```

### <a name="parameters"></a>Parametreler

*pstrDirName*<br/>
Kaldırılacak dizini içeren bir dize işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0. Çağrı başarısız olursa, Win32 işlevini [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) hatanın nedenini belirlemek için çağrılabilir.

### <a name="remarks"></a>Açıklamalar

Kullanım [GetCurrentDirectory](#getcurrentdirectory) server'ın geçerli çalışma dizini belirlemek için. Uzak sistem kök dizine bağlandı varsaymayın.

*PstrDirName* parametresi, geçerli dizine göreli kısmen veya tamamen nitelikli filename olabilir. Ters eğik çizgi (\\) veya her iki adı dizin ayırıcı olarak eğik çizgi (/) kullanılabilir. `RemoveDirectory` Bunlar kullanılmadan önce dizin adı ayırıcılar uygun karakterlere çevirir.

##  <a name="rename"></a>  CFtpConnection::Rename

Bağlı sunucuda belirtilen dosyayı yeniden adlandırmak için bu üye işlevini çağırın.

```
BOOL Rename(
    LPCTSTR pstrExisting,
    LPCTSTR pstrNew);
```

### <a name="parameters"></a>Parametreler

*pstrExisting*<br/>
Yeniden adlandırılacak dosyasının geçerli adını içeren bir dize işaretçisi.

*pstrNew*<br/>
Yeni dosyanın adını içeren bir dize işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0. Çağrı başarısız olursa, Win32 işlevini [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) hatanın nedenini belirlemek için çağrılabilir.

### <a name="remarks"></a>Açıklamalar

*PstrExisting* ve *pstrNew* parametreleri ya da kısmen nitelenmiş dosya adını geçerli dizine göreli veya tam olabilir. Ters eğik çizgi (\\) veya her iki adı dizin ayırıcı olarak eğik çizgi (/) kullanılabilir. `Rename` Bunlar kullanılmadan önce dizin adı ayırıcılar uygun karakterlere çevirir.

##  <a name="setcurrentdirectory"></a>  CFtpConnection::SetCurrentDirectory

FTP sunucusunda farklı bir dizine değiştirmek için bu üye işlevini çağırın.

```
BOOL SetCurrentDirectory(LPCTSTR pstrDirName);
```

### <a name="parameters"></a>Parametreler

*pstrDirName*<br/>
Dizinin adını içeren bir dize işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0. Çağrı başarısız olursa, Win32 işlevini [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) hatanın nedenini belirlemek için çağrılabilir.

### <a name="remarks"></a>Açıklamalar

*PstrDirName* parametresi, geçerli dizine göreli kısmen veya tamamen nitelikli filename olabilir. Ters eğik çizgi (\\) veya her iki adı dizin ayırıcı olarak eğik çizgi (/) kullanılabilir. `SetCurrentDirectory` Bunlar kullanılmadan önce dizin adı ayırıcılar uygun karakterlere çevirir.

Kullanım [GetCurrentDirectory](#getcurrentdirectory) bir FTP sunucusunun geçerli çalışma dizini belirlemek için. Uzak sistem kök dizine bağlandı varsaymayın.

## <a name="see-also"></a>Ayrıca Bkz.

[CInternetConnection Sınıfı](../../mfc/reference/cinternetconnection-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CInternetConnection Sınıfı](../../mfc/reference/cinternetconnection-class.md)<br/>
[CInternetSession Sınıfı](../../mfc/reference/cinternetsession-class.md)
