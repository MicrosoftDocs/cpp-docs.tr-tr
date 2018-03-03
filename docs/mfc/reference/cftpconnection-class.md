---
title: "CFtpConnection sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a20ee1e3de4d5c9f61437c79bd2eda4240947947
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cftpconnection-class"></a>CFtpConnection sınıfı
Internet sunucusu FTP bağlantınız yönetir ve dizinleri ve dosyaları bu sunucuda doğrudan işlenmesini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CFtpConnection : public CInternetConnection  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFtpConnection::CFtpConnection](#cftpconnection)|Oluşturan bir `CFtpConnection` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFtpConnection::Command](#command)|Bir komutu doğrudan bir FTP sunucusuna gönderir.|  
|[CFtpConnection::CreateDirectory](#createdirectory)|Bir dizin sunucusu üzerinde oluşturur.|  
|[CFtpConnection::GetCurrentDirectory](#getcurrentdirectory)|Bu bağlantı için geçerli dizin alır.|  
|[CFtpConnection::GetCurrentDirectoryAsURL](#getcurrentdirectoryasurl)|URL olarak bu bağlantı için geçerli dizin alır.|  
|[CFtpConnection::GetFile](#getfile)|Bir dosya bağlı sunucudan alır|  
|[CFtpConnection::OpenFile](#openfile)|Bir bağlı sunucu dosyayı açar.|  
|[CFtpConnection::PutFile](#putfile)|Sunucu bir dosyaya yerleştirir.|  
|[CFtpConnection::Remove](#remove)|Bir dosya sunucusundan kaldırır.|  
|[CFtpConnection::RemoveDirectory](#removedirectory)|Belirtilen dizin sunucusundan kaldırır.|  
|[CFtpConnection::Rename](#rename)|Sunucu üzerindeki bir dosyayı yeniden adlandırır.|  
|[CFtpConnection::SetCurrentDirectory](#setcurrentdirectory)|Geçerli FTP dizini ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 FTP tarafından MFC WinINet sınıfları tanınır üç Internet services biridir.  
  
 Bir FTP Internet sunucusu ile iletişim kurmak için önce bir örneğini oluşturmanız gerekir [CInternetSession](../../mfc/reference/cinternetsession-class.md)ve ardından oluşturun bir `CFtpConnection` nesnesi. Hiçbir zaman oluşturduğunuz bir `CFtpConnection` doğrudan nesne; bunun yerine, çağrı [CInternetSession::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection), oluşturan `CFtpConnection` nesne ve bir işaretçi döndürür.  
  
 Hakkında daha fazla bilgi için `CFtpConnection` diğer MFC Internet sınıfları ile works başlıklı makaleye bakın [Internet programlama WinINet ile](../../mfc/win32-internet-extensions-wininet.md). Hizmetleri, HTTP ve gopher bkz sınıfları desteklenen diğer iki ile iletişim kurma hakkında daha fazla bilgi için [CHttpConnection](../../mfc/reference/chttpconnection-class.md) ve [CGopherConnection](../../mfc/reference/cgopherconnection-class.md).  
  
## <a name="example"></a>Örnek  
  Örnekte bkz [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) sınıfına genel bakış.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)  
  
 `CFtpConnection`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxinet.h  
  
##  <a name="cftpconnection"></a>CFtpConnection::CFtpConnection  
 Bu üye işlevi oluşturmak için çağrılan bir `CFtpConnection` nesnesi.  
  
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
 `pSession`  
 Bir işaretçi ilgili [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesi.  
  
 `hConnected`  
 Windows tanıtıcı geçerli Internet oturumunun.  
  
 `pstrServer`  
 FTP sunucusu adını içeren bir dize için bir işaretçi.  
  
 `dwContext`  
 İşlem bağlamı tanımlayıcısı. `dwContext`işlem durumu bilgileri tarafından döndürülen tanımlayan [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback). Varsayılan değer 1 olarak ayarlanır; Ancak, belirli bir bağlam kimliği işlemi için açıkça atayabilirsiniz. Nesne ve mevcut herhangi bir iş, içerik kimliği ile ilişkilendirilecek  
  
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
  
 `bPassive`  
 Bu FTP oturumu için etkin veya Pasif modu belirtir. Varsa kümesine **TRUE**, Win32 API ayarlar `dwFlag` için **INTERNET_FLAG_PASSIVE**.  
  
### <a name="remarks"></a>Açıklamalar  
 Hiçbir zaman oluşturduğunuz bir `CFtpConnection` doğrudan nesne. Bunun yerine, çağrı [CInternetSession::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection), oluşturan **CFptConnection** nesnesi.  
  
##  <a name="command"></a>CFtpConnection::Command  
 Bir komutu doğrudan bir FTP sunucusuna gönderir.  
  
```  
CInternetFile* Command(
    LPCTSTR pszCommand,  
    CmdResponseType eResponse = CmdRespNone,  
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Parametreler  
 `pszCommand`  
 Gönderilecek komut içeren bir dize için bir işaretçi.  
  
 *eResponse*  
 Bir yanıt FTP sunucusundan beklenen durum olup olmadığını belirler. Aşağıdaki değerlerden biri olabilir:  
  
- **CmdRespNone** yanıt beklenir.  
  
- **CmdRespRead** yanıtı bekleniyor.  
  
 `dwFlags`  
 Bu işlev denetim bayrakları içeren bir değer. Tam bir listesi için bkz: [FTPCommand](http://msdn.microsoft.com/library/windows/desktop/aa384133).  
  
 `dwContext`  
 Geri aramalar uygulama bağlamında tanımlamak için kullanılan bir uygulama tanımlı değeri içeren bir değer için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi işlevselliğini öykünen [FTPCommand](http://msdn.microsoft.com/library/windows/desktop/aa384133) , Windows SDK'ın açıklandığı gibi işlev.  
  
 Bir hata oluşursa, MFC türünde bir özel durum atar [CInternetException](../../mfc/reference/cinternetexception-class.md).  
  
##  <a name="createdirectory"></a>CFtpConnection::CreateDirectory  
 Bağlı sunucuda dizin oluşturmak için bu üye işlevini çağırın.  
  
```  
BOOL CreateDirectory(LPCTSTR pstrDirName);
```  
  
### <a name="parameters"></a>Parametreler  
 `pstrDirName`  
 Oluşturmak için dizin adını içeren bir dize için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0. Çağrı başarısız olursa, Windows işlevini [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) hatanın nedenini belirlemek için çağrılabilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `GetCurrentDirectory` bu sunucuya bağlantı için geçerli çalışma dizini belirlenemedi. Uzak sistem kök dizinine bağlandı varsayalım değil.  
  
 `pstrDirName` Parametresi olabilir ya da bir kısmen veya geçerli dizine göreli bir tam dosya adı. Ters eğik çizgi (\\) veya eğik çizgi (/), ya da adı dizin ayırıcı olarak kullanılabilir. `CreateDirectory`kullanıldıkları önce uygun karakter dizin adı ayırıcılar çevirir.  
  
##  <a name="getcurrentdirectory"></a>CFtpConnection::GetCurrentDirectory  
 Geçerli dizinin adını almak için bu üye işlevini çağırın.  
  
```  
BOOL GetCurrentDirectory(CString& strDirName) const;  
  
BOOL GetCurrentDirectory(
    LPTSTR pstrDirName,  
    LPDWORD lpdwLen) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `strDirName`  
 Dizin adı alacak olan bir dize başvuru.  
  
 `pstrDirName`  
 Bir işaretçi bir dizeye dizinin adını alır.  
  
 `lpdwLen`  
 Aşağıdaki bilgileri içeren bir DWORD gösteren bir işaretçi:  
  
|||  
|-|-|  
|Girişi|Tarafından başvurulan arabellek boyutu `pstrDirName`.|  
|Getirisi|Saklı karakter sayısını `pstrDirName`. Üye işlev başarısız olur ve ERROR_INSUFFICIENT_BUFFER döndürülür, ardından `lpdwLen` dize almak için uygulama ayırmalısınız bayt sayısını içerir.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0. Çağrı başarısız olursa, Win32 işlevi [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) hatanın nedenini belirlemek için çağrılabilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Dizin adı yerine bir URL almak için çağrı [GetCurrentDirectoryAsURL](#getcurrentdirectoryasurl).  
  
 Parametreleri `pstrDirName` veya `strDirName` tam veya geçerli dizine göreli kısmen tam ya da dosya adları olabilir. Ters eğik çizgi (\\) veya eğik çizgi (/), ya da adı dizin ayırıcı olarak kullanılabilir. `GetCurrentDirectory`kullanıldıkları önce uygun karakter dizin adı ayırıcılar çevirir.  
  
##  <a name="getcurrentdirectoryasurl"></a>CFtpConnection::GetCurrentDirectoryAsURL  
 URL olarak geçerli dizinin adını almak için bu üye işlevini çağırın.  
  
```  
BOOL GetCurrentDirectoryAsURL(CString& strDirName) const;  
  
BOOL GetCurrentDirectoryAsURL(
    LPTSTR pstrName,  
    LPDWORD lpdwLen) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `strDirName`  
 Dizin adı alacak olan bir dize başvuru.  
  
 `pstrDirName`  
 Bir işaretçi bir dizeye dizinin adını alır.  
  
 `lpdwLen`  
 Aşağıdaki bilgileri içeren bir DWORD gösteren bir işaretçi:  
  
|||  
|-|-|  
|Girişi|Tarafından başvurulan arabellek boyutu `pstrDirName`.|  
|Getirisi|Saklı karakter sayısını `pstrDirName`. Üye işlev başarısız olur ve ERROR_INSUFFICIENT_BUFFER döndürülür, ardından `lpdwLen` dize almak için uygulama ayırmalısınız bayt sayısını içerir.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0. Çağrı başarısız olursa, Win32 işlevi [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) hatanın nedenini belirlemek için çağrılabilir.  
  
### <a name="remarks"></a>Açıklamalar  
 `GetCurrentDirectoryAsURL`aynı şekilde davranır [GetCurrentDirectory](#getcurrentdirectory)  
  
 Parametre `strDirName` tam veya geçerli dizine göreli kısmen tam ya da dosya adları olabilir. Ters eğik çizgi (\\) veya eğik çizgi (/), ya da adı dizin ayırıcı olarak kullanılabilir. `GetCurrentDirectoryAsURL`kullanıldıkları önce uygun karakter dizin adı ayırıcılar çevirir.  
  
##  <a name="getfile"></a>CFtpConnection::GetFile  
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
 `pstrRemoteFile`  
 FTP sunucusundan almak için bir dosya adını içeren null ile sonlandırılmış bir dize için bir işaretçi.  
  
 `pstrLocalFile`  
 Yerel sistemde oluşturmak için dosya adını içeren null ile sonlandırılmış bir dize için bir işaretçi.  
  
 *bFailIfExists*  
 Dosya adı tarafından var olan bir dosya zaten kullanılabilir olup olmadığını gösterir. Yerel dosya adı zaten var ve bu parametre **TRUE**, `GetFile` başarısız olur. Aksi takdirde, `GetFile` dosya var olan kopyasını silecek.  
  
 `dwAttributes`  
 Dosyanın öznitelikleri gösterir. Bu aşağıdaki FILE_ATTRIBUTE_ * bayrakları herhangi bir bileşimini olabilir.  
  
-   FILE_ATTRIBUTE_ARCHIVE dosyayı bir arşiv dosyasıdır. Uygulamalar bu öznitelik yedekleme veya kaldırma için dosyaları için kullanın.  
  
-   Dosya veya dizin FILE_ATTRIBUTE_COMPRESSED sıkıştırılır. Bir dosya için sıkıştırma sıkıştırılmış dosyasındaki verilerin tümü anlamına gelir. Bir dizin için sıkıştırma yeni oluşturulan dosya ve alt dizinler için varsayılan değer.  
  
-   FILE_ATTRIBUTE_DIRECTORY dosyayı bir dizindir.  
  
-   FILE_ATTRIBUTE_NORMAL dosya Ayarla özniteliğe sahip değildir. Bu öznitelik, yalnızca tek başına kullanıldığında geçerlidir. Diğer tüm dosya öznitelikleri FILE_ATTRIBUTE_NORMAL geçersiz kıl:  
  
-   Dosya gizli FILE_ATTRIBUTE_HIDDEN. Bu bir sıradan dizin listesinde değil eklenir.  
  
-   FILE_ATTRIBUTE_READONLY dosya salt okunur. Uygulamaların dosyayı okuma ancak olamaz yazma veya silin.  
  
-   Dosya parçası olan veya yalnızca işletim sistemi tarafından kullanılan FILE_ATTRIBUTE_SYSTEM.  
  
-   Dosya geçici depolama için kullanılan FILE_ATTRIBUTE_TEMPORARY. Uygulamalar, yalnızca kesinlikle gerekli olduğunda veya dosyaya yazmak. Dosyanın verilerin çoğu dosya hemen silinecek medyaya temizlendi nedeni olmadan bellekte kalır.  
  
 `dwFlags`  
 Aktarım oluştuğu koşulları belirtir. Bu parametre herhangi biri olabilir `dwFlags` değerleri açıklanan [FtpGetFile](http://msdn.microsoft.com/library/windows/desktop/aa384157) Windows SDK'sındaki.  
  
 `dwContext`  
 Dosya alma içerik tanımlayıcısı. Bkz: **açıklamalar** hakkında daha fazla bilgi için `dwContext`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0. Çağrı başarısız olursa, Win32 işlevi [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) hatanın nedenini belirlemek için çağrılabilir.  
  
### <a name="remarks"></a>Açıklamalar  
 `GetFile`bir FTP sunucusundan bir dosya okuma ve yerel olarak depolamak ile ilgili ek yükü tüm işler üst düzey bir yordamdır. Dosya verileri yalnızca almak veya dosya aktarımı Kapat denetime gerektiren uygulamalar kullanması gereken `OpenFile` ve [CInternetFile::Read](../../mfc/reference/cinternetfile-class.md#read) yerine.  
  
 Varsa `dwFlags` FILE_TRANSFER_TYPE_ASCII, dosya verilerini çevrilmesi aynı zamanda dönüştürür denetim ve Windows eşdeğerleri karakterlere biçimlendirme. Varsayılan aktarım ikili, sunucuda depolanan gibi dosya aynı biçimde indirdiğiniz moddur.  
  
 Her ikisi de `pstrRemoteFile` ve `pstrLocalFile` tam veya geçerli dizine göreli kısmen tam ya da dosya adları olabilir. Ters eğik çizgi (\\) veya eğik çizgi (/), ya da adı dizin ayırıcı olarak kullanılabilir. `GetFile`kullanıldıkları önce uygun karakter dizin adı ayırıcılar çevirir.  
  
 Geçersiz kılma `dwContext` varsayılan bağlam tanımlayıcı bir değerine ayarlayın. Bağlam tanıtıcısı belirli bu işlemle ilişkili `CFtpConnection` tarafından oluşturulan nesne kendi [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesi. İçin döndürülen değer [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) sahip belirtilen işlem durumu sağlamak için. Makalesine bakın [Internet ilk adımlar: WinINet](../../mfc/wininet-basics.md) bağlamı tanımlayıcısı hakkında daha fazla bilgi.  
  
##  <a name="openfile"></a>CFtpConnection::OpenFile  
 Okuma veya yazma için bir FTP sunucusunda bulunan bir dosyayı açmak için bu üye işlevini çağırın.  
  
```  
CInternetFile* OpenFile(
    LPCTSTR pstrFileName,  
    DWORD dwAccess = GENERIC_READ,  
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Parametreler  
 `pstrFileName`  
 Açılması için dosyanın adını içeren bir dize için bir işaretçi.  
  
 *dwAccess*  
 Dosyanın nasıl erişileceği belirler. GENERIC_READ veya GENERIC_WRITE ancak ikisini olabilir.  
  
 `dwFlags`  
 Sonraki aktarımları meydana geldiği altında koşulları belirtir. Bu herhangi FTP_TRANSFER_ * sabitlerden biri olabilir:  
  
-   FTP ASCII (tür A) aktarım yöntemini kullanarak FTP_TRANSFER_TYPE_ASCII dosyaya aktarır. Dönüştürür denetim ve yerel eşdeğerlerine biçimlendirme bilgileri.  
  
-   FTP_TRANSFER_TYPE_BINARY dosya FTP's görüntü (tür ı) aktarım yöntemini kullanarak veri aktarır. Dosya aktarımları verileri tam olarak, herhangi bir değişiklik yapmadan bulunmaktadır. Bu varsayılan aktarımı yöntemdir.  
  
 `dwContext`  
 Dosyayı açmak için içerik tanımlayıcısı. Bkz: **açıklamalar** hakkında daha fazla bilgi için `dwContext`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir [CInternetFile](../../mfc/reference/cinternetfile-class.md) nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 `OpenFile`Aşağıdaki durumlarda kullanılmalıdır:  
  
-   Uygulama verileri yerel bir dosyada değil ancak bu, gönderilen ve FTP sunucusundaki bir dosya olarak oluşturulmuş olması gereken verileri içeriyor. Bir kez `OpenFile` uygulamanız tarafından kullanılan bir dosyayı açtığında [CInternetFile::Write](../../mfc/reference/cinternetfile-class.md#write) sunucuya FTP dosya verileri göndermek için.  
  
-   Bir uygulama, bir dosya sunucusundan almak ve diske yazmak yerine uygulama kontrollü bellek içine yerleştirin. Uygulamanın kullandığı [CInternetFile::Read](../../mfc/reference/cinternetfile-class.md#read) kullandıktan sonra `OpenFile` dosyası açılamıyor.  
  
-   Bir uygulama bir dosya aktarımı üzerinde denetim ayrıntılı bir düzeyde gerekir. Örneğin, uygulama bir ilerleme durumunu görüntüleme isteyebilirsiniz denetim dosya indirilirken dosya aktarımı durumunu ilerlemesini gösterir.  
  
 Çağırdıktan sonra `OpenFile` ve arama kadar **CInternetConnection::Close**, uygulamanın yalnızca çağırabilir [CInternetFile::Read](../../mfc/reference/cinternetfile-class.md#read), [CInternetFile::Write](../../mfc/reference/cinternetfile-class.md#write), **CInternetConnection::Close**, veya [CFtpFileFind::FindFile](../../mfc/reference/cftpfilefind-class.md#findfile). Diğer FTP işlevleri aynı FTP oturumu için çağrılar başarısız ve hata kodu için FTP_ETRANSFER_IN_PROGRESS ayarlayın.  
  
 `pstrFileName` Parametresi ya da bir kısmen tam dosya adı geçerli dizine göreli veya tam olabilir. Ters eğik çizgi (\\) veya eğik çizgi (/), ya da adı dizin ayırıcı olarak kullanılabilir. `OpenFile`Dizin adı ayırıcılar uygun karakter kullanmadan önce çevirir.  
  
 Geçersiz kılma `dwContext` varsayılan bağlam tanımlayıcı bir değerine ayarlayın. Bağlam tanıtıcısı belirli bu işlemle ilişkili `CFtpConnection` tarafından oluşturulan nesne kendi [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesi. İçin döndürülen değer [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) sahip belirtilen işlem durumu sağlamak için. Makalesine bakın [Internet ilk adımlar: WinINet](../../mfc/wininet-basics.md) bağlamı tanımlayıcısı hakkında daha fazla bilgi.  
  
##  <a name="putfile"></a>CFtpConnection::PutFile  
 Bir FTP sunucusu üzerindeki bir dosyaya depolamak için bu üye işlevini çağırın.  
  
```  
BOOL PutFile(
    LPCTSTR pstrLocalFile,  
    LPCTSTR pstrRemoteFile,  
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Parametreler  
 `pstrLocalFile`  
 Yerel sistemden gönderilecek dosyanın adını içeren bir dize için bir işaretçi.  
  
 `pstrRemoteFile`  
 FTP sunucusunda oluşturmak için dosya adını içeren bir dize için bir işaretçi.  
  
 `dwFlags`  
 Dosya aktarımını oluştuğu koşulları belirtir. Açıklanan FTP_TRANSFER_ * sabitlerden herhangi birisi olabilir [OpenFile](#openfile).  
  
 `dwContext`  
 Dosyayı yerleştirmek için içerik tanımlayıcısı. Bkz: **açıklamalar** hakkında daha fazla bilgi için `dwContext`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0. Çağrı başarısız olursa, Win32 işlevi [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) hatanın nedenini belirlemek için çağrılabilir.  
  
### <a name="remarks"></a>Açıklamalar  
 `PutFile`tüm FTP sunucusu üzerindeki bir dosyaya saklamanın işlemlerini işleme üst düzey bir yordamdır. Verileri yalnızca göndermek veya dosya aktarımı üzerinde daha yakından denetim gerektiren uygulamalar kullanması gereken [OpenFile](#openfile) ve [CInternetFile::Write](../../mfc/reference/cinternetfile-class.md#write).  
  
 Geçersiz kılma `dwContext` varsayılan bağlam tanımlayıcı bir değerine ayarlayın. Bağlam tanıtıcısı belirli bu işlemle ilişkili `CFtpConnection` tarafından oluşturulan nesne kendi [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesi. İçin döndürülen değer [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) sahip belirtilen işlem durumu sağlamak için. Makalesine bakın [Internet ilk adımlar: WinINet](../../mfc/wininet-basics.md) bağlamı tanımlayıcısı hakkında daha fazla bilgi.  
  
##  <a name="remove"></a>CFtpConnection::Remove  
 Belirtilen dosya bağlı sunucusunu silmek için bu üye işlevini çağırın.  
  
```  
BOOL Remove(LPCTSTR pstrFileName);
```  
  
### <a name="parameters"></a>Parametreler  
 `pstrFileName`  
 Kaldırmak için dosya adını içeren bir dize için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0. Çağrı başarısız olursa, Win32 işlevi [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) hatanın nedenini belirlemek için çağrılabilir.  
  
### <a name="remarks"></a>Açıklamalar  
 `pstrFileName` Parametresi ya da bir kısmen tam dosya adı geçerli dizine göreli veya tam olabilir. Ters eğik çizgi (\\) veya eğik çizgi (/), ya da adı dizin ayırıcı olarak kullanılabilir. **Kaldırmak** işlevi kullanıldıkları önce uygun karakter dizin adı ayırıcılar çevirir.  
  
##  <a name="removedirectory"></a>CFtpConnection::RemoveDirectory  
 Belirtilen dizin bağlı sunucusundan kaldırmak için bu üye işlevini çağırın.  
  
```  
BOOL RemoveDirectory(LPCTSTR pstrDirName);
```  
  
### <a name="parameters"></a>Parametreler  
 `pstrDirName`  
 Kaldırılacak dizini içeren bir dize için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0. Çağrı başarısız olursa, Win32 işlevi [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) hatanın nedenini belirlemek için çağrılabilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım [GetCurrentDirectory](#getcurrentdirectory) sunucunun geçerli çalışma dizini belirlenemedi. Uzak sistem kök dizinine bağlandı varsayalım değil.  
  
 `pstrDirName` Parametresi geçerli dizine göreli kısmen veya tamamen tam filename olabilir. Ters eğik çizgi (\\) veya eğik çizgi (/), ya da adı dizin ayırıcı olarak kullanılabilir. `RemoveDirectory`kullanıldıkları önce uygun karakter dizin adı ayırıcılar çevirir.  
  
##  <a name="rename"></a>CFtpConnection::Rename  
 Belirtilen dosya bağlı sunucu üzerinde yeniden adlandırmak için bu üye işlevini çağırın.  
  
```  
BOOL Rename(
    LPCTSTR pstrExisting,  
    LPCTSTR pstrNew);
```  
  
### <a name="parameters"></a>Parametreler  
 `pstrExisting`  
 Yeniden adlandırılacak dosyanın geçerli adını içeren bir dize için bir işaretçi.  
  
 `pstrNew`  
 Dosyanın yeni adını içeren bir dize için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0. Çağrı başarısız olursa, Win32 işlevi [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) hatanın nedenini belirlemek için çağrılabilir.  
  
### <a name="remarks"></a>Açıklamalar  
 `pstrExisting` Ve `pstrNew` parametreleri ya da bir kısmen tam dosya adı geçerli dizine göreli veya tam olabilir. Ters eğik çizgi (\\) veya eğik çizgi (/), ya da adı dizin ayırıcı olarak kullanılabilir. **Yeniden Adlandır** kullanıldıkları önce uygun karakter dizin adı ayırıcılar çevirir.  
  
##  <a name="setcurrentdirectory"></a>CFtpConnection::SetCurrentDirectory  
 FTP sunucusunda farklı bir dizin değiştirmek için bu üye işlevini çağırın.  
  
```  
BOOL SetCurrentDirectory(LPCTSTR pstrDirName);
```  
  
### <a name="parameters"></a>Parametreler  
 `pstrDirName`  
 Dizinin adını içeren bir dize için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0. Çağrı başarısız olursa, Win32 işlevi [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) hatanın nedenini belirlemek için çağrılabilir.  
  
### <a name="remarks"></a>Açıklamalar  
 `pstrDirName` Parametresi geçerli dizine göreli kısmen veya tamamen tam filename olabilir. Ters eğik çizgi (\\) veya eğik çizgi (/), ya da adı dizin ayırıcı olarak kullanılabilir. `SetCurrentDirectory`kullanıldıkları önce uygun karakter dizin adı ayırıcılar çevirir.  
  
 Kullanım [GetCurrentDirectory](#getcurrentdirectory) bir FTP sunucusu geçerli çalışma dizini belirlenemedi. Uzak sistem kök dizinine bağlandı varsayalım değil.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CInternetConnection sınıfı](../../mfc/reference/cinternetconnection-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CInternetConnection sınıfı](../../mfc/reference/cinternetconnection-class.md)   
 [CInternetSession Sınıfı](../../mfc/reference/cinternetsession-class.md)
