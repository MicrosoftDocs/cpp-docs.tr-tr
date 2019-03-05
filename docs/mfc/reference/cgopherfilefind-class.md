---
title: CGopherFileFind sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: c1157b3583e266a09840f710b46766ffc4f31b5e
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57269701"
---
# <a name="cgopherfilefind-class"></a>CGopherFileFind sınıfı

Gopher sunucularına, Internet dosyası aramalarındaki Yardımcıları.

> [!NOTE]
>  Sınıfları `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` ve üyeleri bırakılmıştır, Windows XP platformu üzerinde çalışmaz, ancak önceki platformları üzerinde çalışmaya devam eder.

## <a name="syntax"></a>Sözdizimi

```
class CGopherFileFind : public CFileFind
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CGopherFileFind::CGopherFileFind](#cgopherfilefind)|Oluşturur bir `CGopherFileFind` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CGopherFileFind::FindFile](#findfile)|Bir gopher sunucusunda bir dosya bulur.|
|[CGopherFileFind::FindNextFile](#findnextfile)|Bir önceki çağrıya bir dosya aramaya devam [FindFile](#findfile).|
|[CGopherFileFind::GetCreationTime](#getcreationtime)|Belirtilen dosyanın oluşturulduğu saati alır.|
|[CGopherFileFind::GetLastAccessTime](#getlastaccesstime)|Belirtilen dosya son erişilme zamanı alır.|
|[CGopherFileFind::GetLastWriteTime](#getlastwritetime)|Belirtilen dosya için son yazıldığı zaman alır.|
|[CGopherFileFind::GetLength](#getlength)|Bulunan dosyasının bayt cinsinden uzunluğunu alır.|
|[CGopherFileFind::GetLocator](#getlocator)|Alma bir `CGopherLocator` nesne.|
|[CGopherFileFind::GetScreenName](#getscreenname)|Bir gopher ekran adını alır.|
|[CGopherFileFind::IsDots](#isdots)|Dosyaları aracılığıyla yineleme sırasında geçerli dizin ve üst dizini işaretlerinin sınar.|

## <a name="remarks"></a>Açıklamalar

`CGopherFileFind` bir arama başlatır, bir dosyayı bulun ve dönüş bir dosyanın URL'si üye işlevleri içerir.

Internet ve Aranan yerel dosya eklemek için tasarlanmış diğer MFC sınıfları [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) ve [CFileFind](../../mfc/reference/cfilefind-class.md). İle birlikte `CGopherFileFind`, bu sınıflar, sunucu protokolü, dosya türü veya konum (yerel makine veya uzak bir sunucuya.) bağımsız olarak, belirli dosyaları bulmak kullanıcı için sorunsuz bir mekanizma sağlar. HTTP aramaları tarafından gerekli doğrudan dosyasının düzenlenmesini desteklemediği için HTTP sunucularına arama için MFC sınıfı yok olduğuna dikkat edin.

> [!NOTE]
> `CGopherFileFind` Aşağıdaki üye işlevleri kendi taban sınıfının desteklemiyor [CFileFind](../../mfc/reference/cfilefind-class.md):

- [GetRoot](../../mfc/reference/cfilefind-class.md#getroot)

- [GetFileName](../../mfc/reference/cfilefind-class.md#getfilename)

- [GetFilePath](../../mfc/reference/cfilefind-class.md#getfilepath)

- [GetFileTitle](../../mfc/reference/cfilefind-class.md#getfiletitle)

- [GetFileURL](../../mfc/reference/cfilefind-class.md#getfileurl)

Ayrıca, ile kullanıldığında `CGopherFileFind`, `CFileFind` üye işlevi [IsDots](../../mfc/reference/cfilefind-class.md#isdots) her zaman false'tur.

Nasıl kullanılacağı hakkında daha fazla bilgi için `CGopherFileFind` ve diğer WinINet sınıfları başlıklı makaleye bakın [Winınet'in Internet programlama](../../mfc/win32-internet-extensions-wininet.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CFileFind](../../mfc/reference/cfilefind-class.md)

`CGopherFileFind`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxinet.h

##  <a name="cgopherfilefind"></a>  CGopherFileFind::CGopherFileFind

Bu üye işlevi oluşturmak için çağrılan bir `CGopherFileFind` nesne.

```
explicit CGopherFileFind(
    CGopherConnection* pConnection,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Parametreler

*pConnection*<br/>
Bir işaretçi bir [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) nesne.

*dwContext*<br/>
İşlem bağlamı tanımlayıcısı. Bkz: **açıklamalar** hakkında daha fazla bilgi için *dwContext*.

### <a name="remarks"></a>Açıklamalar

İçin varsayılan değer *dwContext* MFC'ye tarafından gönderilen `CGopherFileFind` nesnesinden [Cınternetsession](../../mfc/reference/cinternetsession-class.md) oluşturulan nesne `CGopherFileFind` nesne. Oluşturduğunuzda bir `CGopherFileFind` nesne bağlamı tanımlayıcısını bir değere ayarlamak için varsayılan kılabilir. İçerik tanımlayıcısı döndürülür [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) durumu ile belirtilen nesneye sağlamak için. Makaleye göz atın [Internet ilk adımlar: WinINet](../../mfc/wininet-basics.md) bağlam tanımlayıcısı hakkında daha fazla bilgi.

##  <a name="findfile"></a>  CGopherFileFind::FindFile

Bir gopher dosyayı bulmak için bu üye işlevini çağırın.

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

*refLocator*<br/>
Bir başvuru bir [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) nesne.

*pstrString*<br/>
Dosya adını içeren bir dize işaretçisi.

*CertOpenStore*<br/>
Bu oturumda nasıl ele alınacağını açıklayan bayrakları. Geçerli bayraklar:

- INTERNET_FLAG_RELOAD veri alma Uzak sunucudan bile yerel olarak önbelleğe alınır.

- INTERNET_FLAG_DONT_CACHE önbelleğe almaz verileri yerel olarak veya herhangi bir ağ geçidi.

- Güvenli Yuva Katmanı veya yüzdesi Tel üzerinde güvenli işlemler INTERNET_FLAG_SECURE iste Bu bayrağı yalnızca HTTP istekleri için geçerlidir.

- INTERNET_FLAG_USE_EXISTING varsa mümkün tekrar sunucuya varolan bağlantılar yeni `FindFile` her istek için yeni bir oturum oluşturmak yerine istekleri.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0. Genişletilmiş hata bilgilerini almak için Win32 işlevini çağırmak [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360).

### <a name="remarks"></a>Açıklamalar

Arama sonra `FindFile` ilk gopher nesnesini almak için çağırabilirsiniz ['larını](#findnextfile) sonraki gopher dosyaları almak için.

##  <a name="findnextfile"></a>  CGopherFileFind::FindNextFile

Bu üye işlevi çağrısı ile başlamış bir dosya aramaya devam etmek için arama [CGopherFileFind::FindFile](#findfile).

```
virtual BOOL FindNextFile();
```

### <a name="return-value"></a>Dönüş Değeri

Daha fazla dosya yoksa sıfır; sıfır. dosya bulundu sonuncu dizininde olması veya bir hata oluştu. Genişletilmiş hata bilgilerini almak için Win32 işlevini çağırmak [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360). Son dosya dizininde dosyası bulunamadı veya hiçbir eşleşen dosyaları bulunabilir, `GetLastError` ERROR_NO_MORE_FILES işlevi döndürür.

##  <a name="getcreationtime"></a>  CGopherFileFind::GetCreationTime

Geçerli dosya için oluşturulma zamanını alır.

```
virtual BOOL GetCreationTime(FILETIME* pTimeStamp) const;
virtual BOOL GetCreationTime(CTime& refTime) const;
```

### <a name="parameters"></a>Parametreler

*pTimeStamp*<br/>
Bir işaretçi bir [FILETIME](/windows/desktop/api/minwinbase/ns-minwinbase-filetime) yapısı içeren dosyanın oluşturulduğu zaman.

*refTime*<br/>
Bir başvuru bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; işlem başarısız olursa 0. `GetCreationTime` yalnızca 0 döndürür ['larını](#findnextfile) hiçbir zaman bu çağrıldıktan `CGopherFileFind` nesne.

### <a name="remarks"></a>Açıklamalar

Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `GetCreationTime`.

> [!NOTE]
>  Tüm dosya sistemleri, bu işlev tarafından döndürülen zaman damgası uygulamak için aynı semantiğe kullanın. Bu işlev, temel alınan dosya sistemi veya sunucu zaman öznitelik tutma desteklemiyorsa, diğer zaman damgası işlevleri tarafından döndürülen aynı değer döndürebilir. Bkz: [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) yapısı saat biçimleri hakkında bilgi için. Bazı işletim sistemlerinde, döndürülen saat dilimi yerel makineye olan dosyasının bulunduğu saat şöyledir. Win32 bkz [FileTimeToLocalFileTime](/windows/desktop/api/fileapi/nf-fileapi-filetimetolocalfiletime) API daha fazla bilgi için.

##  <a name="getlastaccesstime"></a>  CGopherFileFind::GetLastAccessTime

Belirtilen dosya son erişilme zamanı alır.

```
virtual BOOL GetLastAccessTime(CTime& refTime) const;
virtual BOOL GetLastAccessTime(FILETIME* pTimeStamp) const;
```

### <a name="parameters"></a>Parametreler

*refTime*<br/>
Bir başvuru bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesne.

*pTimeStamp*<br/>
Bir işaretçi bir [FILETIME](/windows/desktop/api/minwinbase/ns-minwinbase-filetime) içeren dosyanın son erişildi zaman yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; işlem başarısız olursa 0. `GetLastAccessTime` yalnızca 0 döndürür ['larını](#findnextfile) hiçbir zaman bu çağrıldıktan `CGopherFileFind` nesne.

### <a name="remarks"></a>Açıklamalar

Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `GetLastAccessTime`.

> [!NOTE]
>  Tüm dosya sistemleri, bu işlev tarafından döndürülen zaman damgası uygulamak için aynı semantiğe kullanın. Bu işlev, temel alınan dosya sistemi veya sunucu zaman öznitelik tutma desteklemiyorsa, diğer zaman damgası işlevleri tarafından döndürülen aynı değer döndürebilir. Bkz: [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) yapısı saat biçimleri hakkında bilgi için. Bazı işletim sistemlerinde, döndürülen saat dilimi yerel makineye olan dosyasının bulunduğu saat şöyledir. Win32 bkz [FileTimeToLocalFileTime](/windows/desktop/api/fileapi/nf-fileapi-filetimetolocalfiletime) API daha fazla bilgi için.

##  <a name="getlastwritetime"></a>  CGopherFileFind::GetLastWriteTime

Dosya değiştirildiği son saati alır.

```
virtual BOOL GetLastWriteTime(FILETIME* pTimeStamp) const;
virtual BOOL GetLastWriteTime(CTime& refTime) const;
```

### <a name="parameters"></a>Parametreler

*pTimeStamp*<br/>
Bir işaretçi bir [FILETIME](/windows/desktop/api/minwinbase/ns-minwinbase-filetime) içeren dosyanın son kaydedilmişti zaman yapısı.

*refTime*<br/>
Bir başvuru bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; işlem başarısız olursa 0. `GetLastWriteTime` yalnızca 0 döndürür ['larını](#findnextfile) hiçbir zaman bu çağrıldıktan `CGopherFileFind` nesne.

### <a name="remarks"></a>Açıklamalar

Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `GetLastWriteTime`.

> [!NOTE]
>  Tüm dosya sistemleri, bu işlev tarafından döndürülen zaman damgası uygulamak için aynı semantiğe kullanın. Bu işlev, temel alınan dosya sistemi veya sunucu zaman öznitelik tutma desteklemiyorsa, diğer zaman damgası işlevleri tarafından döndürülen aynı değer döndürebilir. Bkz: [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) yapısı saat biçimleri hakkında bilgi için. Bazı işletim sistemlerinde, döndürülen saat dilimi yerel makineye olan dosyasının bulunduğu saat şöyledir. Win32 bkz [FileTimeToLocalFileTime](/windows/desktop/api/fileapi/nf-fileapi-filetimetolocalfiletime) API daha fazla bilgi için.

##  <a name="getlength"></a>  CGopherFileFind::GetLength

Bulunan dosyayı bayt cinsinden uzunluğunu almak için bu üye işlevini çağırın.

```
virtual ULONGLONG GetLength() const;
```

### <a name="return-value"></a>Dönüş Değeri

Uzunluğu, bayt cinsinden bulunan dosya.

### <a name="remarks"></a>Açıklamalar

`GetLength` Win32 yapısını kullanır [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) bayt cinsinden boyutu değerini almak için.

> [!NOTE]
>  MFC 7.0 itibarıyla `GetLength` 64-bit tamsayı türlerini destekler. Bu kitaplığı daha yeni sürümü ile oluşturulan önceden varolan kod kesme uyarıların sonuçlanabilir.

### <a name="example"></a>Örnek

  Örneğin bakın [CFile::GetLength](../../mfc/reference/cfile-class.md#getlength) (temel sınıf uygulamasına).

##  <a name="getlocator"></a>  CGopherFileFind::GetLocator

Almak için bu üye işlevi çağrısı [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) nesnesinin [FindFile](#findfile) gopher dosyayı bulmak için kullanır.

```
CGopherLocator GetLocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

A `CGopherLocator` nesne.

##  <a name="getscreenname"></a>  CGopherFileFind::GetScreenName

Gopher ekranın adını almak için bu üye işlevini çağırın.

```
CString GetScreenName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Gopher ekranın adı.

##  <a name="isdots"></a>  CGopherFileFind::IsDots

Dosyaları aracılığıyla yineleme sırasında geçerli dizin ve üst dizini işaretlerinin sınar.

```
virtual BOOL IsDots() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sıfır dışında bulunan dosya adı varsa "."veya"...", bulunan dosyanın aslında bir dizin olduğunu gösterir. Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `IsDots`.

## <a name="see-also"></a>Ayrıca bkz.

[CFileFind Sınıfı](../../mfc/reference/cfilefind-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CFtpFileFind Sınıfı](../../mfc/reference/cftpfilefind-class.md)<br/>
[CFileFind Sınıfı](../../mfc/reference/cfilefind-class.md)<br/>
[CInternetFile Sınıfı](../../mfc/reference/cinternetfile-class.md)<br/>
[CGopherFile Sınıfı](../../mfc/reference/cgopherfile-class.md)<br/>
[CHttpFile Sınıfı](../../mfc/reference/chttpfile-class.md)
