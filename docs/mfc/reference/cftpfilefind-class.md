---
title: "CFtpFileFind sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFtpFileFind
- AFXINET/CFtpFileFind
- AFXINET/CFtpFileFind::CFtpFileFind
- AFXINET/CFtpFileFind::FindFile
- AFXINET/CFtpFileFind::FindNextFile
- AFXINET/CFtpFileFind::GetFileURL
dev_langs: C++
helpviewer_keywords:
- CFtpFileFind [MFC], CFtpFileFind
- CFtpFileFind [MFC], FindFile
- CFtpFileFind [MFC], FindNextFile
- CFtpFileFind [MFC], GetFileURL
ms.assetid: 9667cf01-657f-4b11-b9db-f11e5a7b4e4c
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ff064892172a4d1ab9d31c67be031935650c6c16
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cftpfilefind-class"></a>CFtpFileFind sınıfı
Internet dosya aramaları FTP sunucularının yardımcı olur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CFtpFileFind : public CFileFind  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFtpFileFind::CFtpFileFind](#cftpfilefind)|Oluşturan bir `CFtpFileFind` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFtpFileFind::FindFile](#findfile)|FTP sunucusundaki bir dosyayı bulur.|  
|[CFtpFileFind::FindNextFile](#findnextfile)|Dosya arama önceki çağrısından devam [FindFile](#findfile).|  
|[CFtpFileFind::GetFileURL](#getfileurl)|Bulunan dosyasının yolu da dahil olmak üzere URL'yi alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CFtpFileFind`bir arama başlatır, bir dosyayı bulmak ve URL veya dosya ile ilgili diğer açıklayıcı bilgiler döndürmek üye işlevlerini içerir.  
  
 Internet ve arama yerel dosya eklemek için tasarlanmış diğer MFC sınıfları [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) ve [CFileFind](../../mfc/reference/cfilefind-class.md). İle birlikte `CFtpFileFind`, bu sınıfları istemcinin protokolü veya dosya türü (yerel makine veya uzak bir sunucuya) sunucu bakılmaksızın belirli dosyaları bulmak sorunsuz bir mekanizma sağlar. HTTP arar gerekli doğrudan dosya işleme desteklemediğinden HTTP sunucularında aramak için MFC sınıfı yok olduğuna dikkat edin.  
  
 Nasıl kullanılacağı hakkında daha fazla bilgi için `CFtpFileFind` ve diğer WinINet sınıfları başlıklı makaleye bakın [Internet programlama WinINet ile](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod, FTP sunucusunun geçerli dizindeki tüm dosyaları numaralandırma gösterilmiştir.  
  
 [!code-cpp[NVC_MFCWinInet#8](../../mfc/codesnippet/cpp/cftpfilefind-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFileFind](../../mfc/reference/cfilefind-class.md)  
  
 `CFtpFileFind`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxinet.h  
  
##  <a name="cftpfilefind"></a>CFtpFileFind::CFtpFileFind  
 Bu üye işlevi oluşturmak için çağrılan bir `CFtpFileFind` nesnesi.  
  
```  
explicit CFtpFileFind(
    CFtpConnection* pConnection,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Parametreler  
 `pConnection`  
 Bir işaretçi bir `CFtpConnection` nesnesi. Bir FTP bağlantısı çağırarak elde edebileceğiniz [CInternetSession::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection).  
  
 `dwContext`  
 İçerik tanımlayıcısını `CFtpFileFind` nesnesi. Bkz: **açıklamalar** Bu parametre hakkında daha fazla bilgi.  
  
### <a name="remarks"></a>Açıklamalar  
 İçin varsayılan değer `dwContext` MFC'ye tarafından gönderilen `CFtpFileFind` nesnesinin [CInternetSession](../../mfc/reference/cinternetsession-class.md) oluşturulan nesne `CFtpFileFind` nesne. Bağlam tanımlayıcı bir değerine ayarlamak için varsayılan ayarlarını geçersiz kılabilir. Bağlam tanıtıcısı döndürülen [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) sahip belirtilen bir nesne üzerinde durumu sağlamak için. Makalesine bakın [Internet ilk adımlar: WinINet](../../mfc/wininet-basics.md) bağlamı tanımlayıcısı hakkında daha fazla bilgi.  
  
### <a name="example"></a>Örnek  
  Bu konunun önceki kısımlarında sınıfına genel bakış örneğe bakın.  
  
##  <a name="findfile"></a>CFtpFileFind::FindFile  
 Bir FTP dosyayı bulmak için bu üye işlevini çağırın.  
  
```  
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,  
    DWORD dwFlags = INTERNET_FLAG_RELOAD);
```  
  
### <a name="parameters"></a>Parametreler  
 `pstrName`  
 Bulunacak dosyasının adı içeren bir dize için bir işaretçi. Varsa **NULL**, çağrı (*) joker arama gerçekleştirilir.  
  
 `dwFlags`  
 Bu oturumda ne yapılacağını açıklayan bayrakları. Bu bayrakların bit düzeyinde OR işleci (&#124;) ile birlikte kullanılabilir ve aşağıdaki gibidir:  
  
-   INTERNET_FLAG_RELOAD veri alma hattan bile yerel olarak önbelleğe alınır. Varsayılan bayrağı budur.  
  
-   INTERNET_FLAG_DONT_CACHE önbelleğe verileri yerel olarak veya herhangi bir ağ geçidi.  
  
-   INTERNET_FLAG_RAW_DATA ham verileri döndürmek için varsayılan geçersiz kılma ( [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) FTP yapıları).  
  
-   Güvenli Yuva Katmanı veya yüzdesi hattaki işlemleri INTERNET_FLAG_SECURE güvenliğini sağlar Bu bayrak, yalnızca HTTP istekleri için geçerlidir.  
  
-   INTERNET_FLAG_EXISTING_CONNECT varsa olası, tekrar sunucusuna varolan bağlantılar için yeni **FindFile** her istek için yeni bir oturumu oluşturmak yerine istekleri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0. Genişletilmiş hata bilgilerini için Win32 işlevini çağırın [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırdıktan sonra **FindFile** ilk FTP dosyasını almak için çağırabilirsiniz ['larını](#findnextfile) sonraki FTP dosyaları alınamadı.  
  
### <a name="example"></a>Örnek  
  Bu konuda önceki örneğe bakın.  
  
##  <a name="findnextfile"></a>CFtpFileFind::FindNextFile  
 Bir çağrı ile başlamış bir dosya aramaya devam etmek için bu üye işlevini çağırın [FindFile](#findfile) üye işlevi.  
  
```  
virtual BOOL FindNextFile();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Daha fazla dosya varsa sıfır olmayan; sıfır bulunan dosya sonuncu dizininde olması veya bir hata oluştu. Genişletilmiş hata bilgilerini için Win32 işlevini çağırın [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360). Son dosya dizininde bulunan dosya ise veya eşleşme varsa dosyaları bulunabilir, `GetLastError` işlevi ERROR_NO_MORE_FILES döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 En az bir kez herhangi bir öznitelik işlevini çağırmadan önce bu işlevini çağırmanız gerekir (bkz [CFileFind::FindNextFile](../../mfc/reference/cfilefind-class.md#findnextfile)).  
  
 `FindNextFile`Win32 işlevi sarmalar ['larını](http://msdn.microsoft.com/library/windows/desktop/aa364428).  
  
### <a name="example"></a>Örnek  
  Bu konunun önceki kısımlarında örneğe bakın.  
  
##  <a name="getfileurl"></a>CFtpFileFind::GetFileURL  
 Belirtilen dosyanın URL'sini almak için bu üye işlevini çağırın.  
  
```  
CString GetFileURL() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dosya ve yol Evrensel Kaynak Konum Belirleyicisi (URL).  
  
### <a name="remarks"></a>Açıklamalar  
 `GetFileURL`üye işlevine benzer [CFileFind::GetFilePath](../../mfc/reference/cfilefind-class.md#getfilepath), URL biçiminde döndürür dışında `ftp://moose/dir/file.txt`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CFileFind sınıfı](../../mfc/reference/cfilefind-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CGopherFileFind sınıfı](../../mfc/reference/cgopherfilefind-class.md)   
 [CInternetFile sınıfı](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile sınıfı](../../mfc/reference/cgopherfile-class.md)   
 [CHttpFile sınıfı](../../mfc/reference/chttpfile-class.md)
