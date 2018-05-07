---
title: CGopherFileFind sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CGopherFileFind
- AFXINET/CGopherFileFind
- AFXINET/CGopherFileFind::CGopherFileFind
- AFXINET/CGopherFileFind::FindFile
- AFXINET/CGopherFileFind::FindNextFile
- AFXINET/CGopherFileFind::GetCreationTime
- AFXINET/CGopherFileFind::GetLastAccessTime
- AFXINET/CGopherFileFind::GetLastWriteTime
- AFXINET/CGopherFileFind::GetLength
- AFXINET/CGopherFileFind::GetLocator
- AFXINET/CGopherFileFind::GetScreenName
- AFXINET/CGopherFileFind::IsDots
dev_langs:
- C++
helpviewer_keywords:
- CGopherFileFind [MFC], CGopherFileFind
- CGopherFileFind [MFC], FindFile
- CGopherFileFind [MFC], FindNextFile
- CGopherFileFind [MFC], GetCreationTime
- CGopherFileFind [MFC], GetLastAccessTime
- CGopherFileFind [MFC], GetLastWriteTime
- CGopherFileFind [MFC], GetLength
- CGopherFileFind [MFC], GetLocator
- CGopherFileFind [MFC], GetScreenName
- CGopherFileFind [MFC], IsDots
ms.assetid: 8465a979-6323-496d-ab4b-e81383fb999d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 584644963a647c5b458407b2d777f91014b40fad
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cgopherfilefind-class"></a>CGopherFileFind sınıfı
Internet dosya aramaları gopher sunucularının yardımcı olur.  
  
> [!NOTE]
>  Sınıfları `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` ve üyeleri Windows XP platformunda çalışmaz, ancak daha önceki platformlar üzerinde çalışmaya devam edecek kullanım dışı bırakıldı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CGopherFileFind : public CFileFind  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CGopherFileFind::CGopherFileFind](#cgopherfilefind)|Oluşturan bir `CGopherFileFind` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CGopherFileFind::FindFile](#findfile)|Bir dosyayı bir gopher sunucuda bulur.|  
|[CGopherFileFind::FindNextFile](#findnextfile)|Dosya arama önceki çağrısından devam [FindFile](#findfile).|  
|[CGopherFileFind::GetCreationTime](#getcreationtime)|Belirtilen dosyanın oluşturulduğu saati alır.|  
|[CGopherFileFind::GetLastAccessTime](#getlastaccesstime)|Belirtilen dosya son erişilen zaman alır.|  
|[CGopherFileFind::GetLastWriteTime](#getlastwritetime)|Belirtilen dosya için son yazıldığı zaman alır.|  
|[CGopherFileFind::GetLength](#getlength)|Bulunan dosyanın bayt cinsinden uzunluğunu alır.|  
|[CGopherFileFind::GetLocator](#getlocator)|Alma bir `CGopherLocator` nesnesi.|  
|[CGopherFileFind::GetScreenName](#getscreenname)|Gopher ekran adını alır.|  
|[CGopherFileFind::IsDots](#isdots)|Testleri dosyalar ile yineleme sırasında geçerli dizin ve üst dizini işaretlerin.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CGopherFileFind` bir arama başlatır, bir dosyayı bulmak ve bir dosyanın URL'sini dönüş üye işlevlerini içerir.  
  
 Internet ve arama yerel dosya eklemek için tasarlanmış diğer MFC sınıfları [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) ve [CFileFind](../../mfc/reference/cfilefind-class.md). İle birlikte `CGopherFileFind`, bu sınıfları kullanıcının sunucu protokolü, dosya türü veya konumu (yerel makine ya da uzak bir sunucuya.) bağımsız olarak belirli dosyaları bulmak sorunsuz bir mekanizma sağlar HTTP aramaları tarafından gerekli doğrudan dosya işleme desteklemediğinden HTTP sunucularında aramak için MFC sınıfı yok olduğuna dikkat edin.  
  
> [!NOTE]
> `CGopherFileFind` Aşağıdaki kendi temel sınıfının üye fonksiyonları desteklemiyor [CFileFind](../../mfc/reference/cfilefind-class.md):  
  
- [GetRoot](../../mfc/reference/cfilefind-class.md#getroot)  
  
- [GetFileName](../../mfc/reference/cfilefind-class.md#getfilename)  
  
- [GetFilePath](../../mfc/reference/cfilefind-class.md#getfilepath)  
  
- [GetFileTitle](../../mfc/reference/cfilefind-class.md#getfiletitle)  
  
- [GetFileURL](../../mfc/reference/cfilefind-class.md#getfileurl)  
  
 Ayrıca, birlikte kullanıldığında `CGopherFileFind`, `CFileFind` üye işlevi [IsDots](../../mfc/reference/cfilefind-class.md#isdots) her zaman **FALSE**.  
  
 Nasıl kullanılacağı hakkında daha fazla bilgi için `CGopherFileFind` ve diğer WinINet sınıfları başlıklı makaleye bakın [Internet programlama WinINet ile](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFileFind](../../mfc/reference/cfilefind-class.md)  
  
 `CGopherFileFind`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxinet.h  
  
##  <a name="cgopherfilefind"></a>  CGopherFileFind::CGopherFileFind  
 Bu üye işlevi oluşturmak için çağrılan bir `CGopherFileFind` nesnesi.  
  
```  
explicit CGopherFileFind(
    CGopherConnection* pConnection,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Parametreler  
 `pConnection`  
 Bir işaretçi bir [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) nesnesi.  
  
 `dwContext`  
 İşlem bağlamı tanımlayıcısı. Bkz: **açıklamalar** hakkında daha fazla bilgi için `dwContext`.  
  
### <a name="remarks"></a>Açıklamalar  
 İçin varsayılan değer `dwContext` MFC'ye tarafından gönderilen `CGopherFileFind` nesnesinin [CInternetSession](../../mfc/reference/cinternetsession-class.md) oluşturulan nesne `CGopherFileFind` nesne. Oluşturduğunuzda bir `CGopherFileFind` nesne bağlamı tanımlayıcı bir değerine ayarlamak için varsayılan geçersiz kılabilirsiniz. Bağlam tanıtıcısı döndürülen [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) sahip belirtilen bir nesne üzerinde durumu sağlamak için. Makalesine bakın [Internet ilk adımlar: WinINet](../../mfc/wininet-basics.md) bağlamı tanımlayıcısı hakkında daha fazla bilgi.  
  
##  <a name="findfile"></a>  CGopherFileFind::FindFile  
 Gopher dosyayı bulmak için bu üye işlevini çağırın.  
  
```  
virtual BOOL FindFile(
    CGopherLocator& refLocator,  
    LPCTSTR pstrString,  
    DWORD dwFlags = INTERNET_FLAG_RELOAD);

 
virtual BOOL FindFile(
    LPCTSTR pstrString,  
    DWORD dwFlags = INTERNET_FLAG_RELOAD);
```  
  
### <a name="parameters"></a>Parametreler  
 `refLocator`  
 Bir başvuru bir [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) nesnesi.  
  
 *pstrString*  
 Dosya adı içeren bir dize için bir işaretçi.  
  
 `dwFlags`  
 Bu oturumda ne yapılacağını açıklayan bayrakları. Geçerli bayraklar şunlardır:  
  
-   INTERNET_FLAG_RELOAD veri alma Uzak sunucudan bile yerel olarak önbelleğe alınır.  
  
-   INTERNET_FLAG_DONT_CACHE önbelleğe verileri yerel olarak veya herhangi bir ağ geçidi.  
  
-   Güvenli Yuva Katmanı veya yüzdesi hattaki güvenli işlemler INTERNET_FLAG_SECURE isteği Bu bayrak, yalnızca HTTP istekleri için geçerlidir.  
  
-   INTERNET_FLAG_USE_EXISTING varsa olası, tekrar sunucusuna varolan bağlantılar için yeni **FindFile** her istek için yeni bir oturumu oluşturmak yerine istekleri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0. Genişletilmiş hata bilgilerini için Win32 işlevini çağırın [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırdıktan sonra **FindFile** ilk gopher nesnesini almak için çağırabilirsiniz ['larını](#findnextfile) sonraki gopher dosyaları almak için.  
  
##  <a name="findnextfile"></a>  CGopherFileFind::FindNextFile  
 Bir çağrı ile başlamış bir dosya aramaya devam etmek için bu üye işlevini çağırın [CGopherFileFind::FindFile](#findfile).  
  
```  
virtual BOOL FindNextFile();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Daha fazla dosya varsa sıfır olmayan; sıfır bulunan dosya sonuncu dizininde olması veya bir hata oluştu. Genişletilmiş hata bilgilerini için Win32 işlevini çağırın [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360). Son dosya dizininde bulunan dosya ise veya eşleşme varsa dosyaları bulunabilir, `GetLastError` işlevi ERROR_NO_MORE_FILES döndürür.  
  
##  <a name="getcreationtime"></a>  CGopherFileFind::GetCreationTime  
 Geçerli dosya oluşturulma zamanı alır.  
  
```  
virtual BOOL GetCreationTime(FILETIME* pTimeStamp) const;  
virtual BOOL GetCreationTime(CTime& refTime) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `pTimeStamp`  
 Bir işaretçi bir [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) dosyanın oluşturulduğu zaman içeren yapısı.  
  
 `refTime`  
 Bir başvuru bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; işlem başarısız olursa 0. `GetCreationTime` yalnızca 0 döndürür ['larını](#findnextfile) bu bilgisayarda hiç çağrıldı `CGopherFileFind` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `GetCreationTime`.  
  
> [!NOTE]
>  Tüm dosya sistemleri, bu işlev tarafından döndürülen zaman damgası uygulamak için aynı semantiğini kullanır. Bu işlev temel alınan dosya sistemi veya sunucunun saat özniteliği tutma desteklemiyorsa, diğer zaman damgası işlevleri tarafından döndürülen aynı değeri döndürebilir. Bkz: [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) yapısı saat biçimleri hakkında bilgi için. Bazı işletim sistemlerinde döndürülen bölge yerel makineye olan dosyasının bulunduğu süresi içinde'dır. Win32 bkz [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) daha fazla bilgi için API.  
  
##  <a name="getlastaccesstime"></a>  CGopherFileFind::GetLastAccessTime  
 Belirtilen dosya son erişilen zaman alır.  
  
```  
virtual BOOL GetLastAccessTime(CTime& refTime) const;  
virtual BOOL GetLastAccessTime(FILETIME* pTimeStamp) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `refTime`  
 Bir başvuru bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesi.  
  
 `pTimeStamp`  
 Bir işaretçi bir [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) dosyaya son erişim saati içeren yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; işlem başarısız olursa 0. `GetLastAccessTime` yalnızca 0 döndürür ['larını](#findnextfile) bu bilgisayarda hiç çağrıldı `CGopherFileFind` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `GetLastAccessTime`.  
  
> [!NOTE]
>  Tüm dosya sistemleri, bu işlev tarafından döndürülen zaman damgası uygulamak için aynı semantiğini kullanır. Bu işlev temel alınan dosya sistemi veya sunucunun saat özniteliği tutma desteklemiyorsa, diğer zaman damgası işlevleri tarafından döndürülen aynı değeri döndürebilir. Bkz: [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) yapısı saat biçimleri hakkında bilgi için. Bazı işletim sistemlerinde döndürülen bölge yerel makineye olan dosyasının bulunduğu süresi içinde'dır. Win32 bkz [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) daha fazla bilgi için API.  
  
##  <a name="getlastwritetime"></a>  CGopherFileFind::GetLastWriteTime  
 Dosya değiştirildi en son ne zaman alır.  
  
```  
virtual BOOL GetLastWriteTime(FILETIME* pTimeStamp) const;  
virtual BOOL GetLastWriteTime(CTime& refTime) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `pTimeStamp`  
 Bir işaretçi bir [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) dosya için en son yazıldı saati içeren yapısı.  
  
 `refTime`  
 Bir başvuru bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; işlem başarısız olursa 0. `GetLastWriteTime` yalnızca 0 döndürür ['larını](#findnextfile) bu bilgisayarda hiç çağrıldı `CGopherFileFind` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `GetLastWriteTime`.  
  
> [!NOTE]
>  Tüm dosya sistemleri, bu işlev tarafından döndürülen zaman damgası uygulamak için aynı semantiğini kullanır. Bu işlev temel alınan dosya sistemi veya sunucunun saat özniteliği tutma desteklemiyorsa, diğer zaman damgası işlevleri tarafından döndürülen aynı değeri döndürebilir. Bkz: [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) yapısı saat biçimleri hakkında bilgi için. Bazı işletim sistemlerinde döndürülen bölge yerel makineye olan dosyasının bulunduğu süresi içinde'dır. Win32 bkz [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) daha fazla bilgi için API.  
  
##  <a name="getlength"></a>  CGopherFileFind::GetLength  
 Bulunan dosyanın bayt cinsinden uzunluğu almak için bu üye işlevini çağırın.  
  
```  
virtual ULONGLONG GetLength() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bayt cinsinden uzunluğu bulunan dosya.  
  
### <a name="remarks"></a>Açıklamalar  
 `GetLength` Win32 yapısı kullanır [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) bayt olarak dosya boyutu değeri alınamıyor.  
  
> [!NOTE]
>  MFC 7.0 itibariyle `GetLength` 64-bit tamsayı türlerini destekler. Bu kitaplığı daha yeni sürümü ile oluşturulmuş önceden varolan kod kesilmesi uyarılarla neden olabilir.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CFile::GetLength](../../mfc/reference/cfile-class.md#getlength) (temel sınıf uygulamasını).  
  
##  <a name="getlocator"></a>  CGopherFileFind::GetLocator  
 Almak için bu üye işlevini çağırın [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) nesnesinin [FindFile](#findfile) gopher dosyayı bulmak için kullanır.  
  
```  
CGopherLocator GetLocator() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CGopherLocator` nesnesi.  
  
##  <a name="getscreenname"></a>  CGopherFileFind::GetScreenName  
 Gopher ekran adını almak için bu üye işlevini çağırın.  
  
```  
CString GetScreenName() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Gopher ekran adı.  
  
##  <a name="isdots"></a>  CGopherFileFind::IsDots  
 Testleri dosyalar ile yineleme sırasında geçerli dizin ve üst dizini işaretlerin.  
  
```  
virtual BOOL IsDots() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bulunan dosyanın adı varsa, sıfır olmayan "."veya"..", bulunan dosyanın gerçekten bir dizin olduğunu gösterir. Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `IsDots`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CFileFind sınıfı](../../mfc/reference/cfilefind-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CFtpFileFind sınıfı](../../mfc/reference/cftpfilefind-class.md)   
 [CFileFind sınıfı](../../mfc/reference/cfilefind-class.md)   
 [CInternetFile sınıfı](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile sınıfı](../../mfc/reference/cgopherfile-class.md)   
 [CHttpFile Sınıfı](../../mfc/reference/chttpfile-class.md)
