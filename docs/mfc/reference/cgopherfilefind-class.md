---
title: CGopherFileFind Sınıf
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
ms.openlocfilehash: 7a42b99c919abd9098bff1897c4c5febf443314d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373687"
---
# <a name="cgopherfilefind-class"></a>CGopherFileFind Sınıf

Gopher sunucularının Internet dosya aramalarında yardımlar.

> [!NOTE]
> Sınıflar `CGopherConnection`, `CGopherFile` `CGopherFileFind`, `CGopherLocator` , , windows xp platformunda çalışmıyor çünkü onların üyeleri küçümsenmiş, ancak önceki platformlarda çalışmaya devam edecektir.

## <a name="syntax"></a>Sözdizimi

```
class CGopherFileFind : public CFileFind
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CGopherFileFind::CGopherFileFind](#cgopherfilefind)|Bir `CGopherFileFind` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CGopherFileFind::FindFile](#findfile)|Bir gopher sunucusunda bir dosya bulur.|
|[CGopherFileFind::FindNextFile](#findnextfile)|[FindFile](#findfile)için önceki bir aramadan bir dosya aramasına devam ediyor.|
|[CGopherFileFind::GetCreationTime](#getcreationtime)|Belirtilen dosyanın oluşturulduğu zamanı alır.|
|[CGopherFileFind::GetLastAccessTime](#getlastaccesstime)|Belirtilen dosyaya en son erişilen saati alır.|
|[CGopherFileFind::GetLastWriteTime](#getlastwritetime)|Belirtilen dosyanın en son yazıldığı zamanı alır.|
|[CGopherFileFind::GetLength](#getlength)|Bulunan dosyanın uzunluğunu baytlarla alır.|
|[CGopherFileFind::GetLocator](#getlocator)|Bir `CGopherLocator` nesne al.|
|[CGopherFileFind::GetScreenName](#getscreenname)|Bir gopher ekran adını alır.|
|[CGopherFileFind::IsDots](#isdots)|Dosyalar arasında yinelerken geçerli dizin ve üst dizin işaretçileri için testler.|

## <a name="remarks"></a>Açıklamalar

`CGopherFileFind`aramayı başlatan, dosyayı bulup dosyanın URL'sini döndüren üye işlevleri içerir.

Internet ve yerel dosya aranan için tasarlanmış diğer MFC sınıfları [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) ve [CFileFind](../../mfc/reference/cfilefind-class.md)içerir. Bu `CGopherFileFind`sınıflar, sunucu protokolü, dosya türü veya konumdan (yerel bir makine veya uzak bir sunucu) bağımsız olarak, kullanıcının belirli dosyaları bulması için sorunsuz bir mekanizma sağlar. HTTP aramaların gerektirdiği doğrudan dosya işlemeyi desteklemediği için HTTP sunucularında arama yapmak için MFC sınıfı olmadığını unutmayın.

> [!NOTE]
> `CGopherFileFind`taban sınıfı [CFileFind](../../mfc/reference/cfilefind-class.md)aşağıdaki üye işlevleri desteklemez:

- [GetRoot](../../mfc/reference/cfilefind-class.md#getroot)

- [GetFileName](../../mfc/reference/cfilefind-class.md#getfilename)

- [Getfilepath](../../mfc/reference/cfilefind-class.md#getfilepath)

- [GetFileTitle](../../mfc/reference/cfilefind-class.md#getfiletitle)

- [GetFileURL](../../mfc/reference/cfilefind-class.md#getfileurl)

Buna ek olarak, `CGopherFileFind`üye `CFileFind` işlevi [IsDots](../../mfc/reference/cfilefind-class.md#isdots) ile kullanıldığında her zaman FALSE.

Nasıl kullanılacağı `CGopherFileFind` ve diğer WinInet sınıfları hakkında daha fazla bilgi için, [WinInet ile](../../mfc/win32-internet-extensions-wininet.md)makale Internet Programlama bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Cfilefind](../../mfc/reference/cfilefind-class.md)

`CGopherFileFind`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxinet.h

## <a name="cgopherfilefindcgopherfilefind"></a><a name="cgopherfilefind"></a>CGopherFileFind::CGopherFileFind

Bu üye işlev bir `CGopherFileFind` nesne oluşturmak için çağrılır.

```
explicit CGopherFileFind(
    CGopherConnection* pConnection,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Parametreler

*pBağlantı*<br/>
[CGopherConnection](../../mfc/reference/cgopherconnection-class.md) nesnesine işaretçi.

*dwBağlam*<br/>
İşlem için bağlam tanımlayıcısı. *dwContext*hakkında daha fazla bilgi için **Açıklamalar'a** bakın.

### <a name="remarks"></a>Açıklamalar

*dwContext* için varsayılan değer, MFC `CGopherFileFind` tarafından `CGopherFileFind` nesneyi oluşturan [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesinden nesneye gönderilir. Bir `CGopherFileFind` nesne oluştursanız, bağlam tanımlayıcısını seçtiğiniz bir değere ayarlamak için varsayılanı geçersiz kılabilirsiniz. Bağlam tanımlayıcısı [CInternetSession döndürülür::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) ile tanımlanan nesne üzerinde durum sağlamak için. Makaleye bakın [Internet İlk Adımlar: WinInet](../../mfc/wininet-basics.md) bağlam tanımlayıcısı hakkında daha fazla bilgi için.

## <a name="cgopherfilefindfindfile"></a><a name="findfile"></a>CGopherFileFind::FindFile

Bir gopher dosyası bulmak için bu üye işlevini arayın.

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
[CGopherLocator](../../mfc/reference/cgopherlocator-class.md) nesnesine bir gönderme.

*pstrString*<br/>
Dosya adını içeren bir dize için işaretçi.

*Dwflags*<br/>
Bu oturumun nasıl işleyeceğini açıklayan bayraklar. Geçerli bayraklar şunlardır:

- INTERNET_FLAG_RELOAD Yerel olarak önbelleğe alınmış olsa bile verileri uzak sunucudan alın.

- INTERNET_FLAG_DONT_CACHE Verileri yerel olarak veya herhangi bir ağ geçidinde önbelleğe alma.

- INTERNET_FLAG_SECURE Güvenli Soketkatmanı veya PCT ile tel üzerinde güvenli işlemler isteyin. Bu bayrak yalnızca HTTP istekleri için geçerlidir.

- INTERNET_FLAG_USE_EXISTING Mümkünse, her istek için yeni `FindFile` bir oturum oluşturmak yerine sunucuya varolan bağlantıları yeni istekler için yeniden kullanın.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0. Genişletilmiş hata bilgilerini almak için Win32 işlevini [getLastError'ı](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)arayın.

### <a name="remarks"></a>Açıklamalar

İlk `FindFile` gopher nesnesini almak için aradıktan sonra, sonraki gopher dosyalarını almak için [FindNextFile'ı](#findnextfile) arayabilirsiniz.

## <a name="cgopherfilefindfindnextfile"></a><a name="findnextfile"></a>CGopherFileFind::FindNextFile

CGopherFileFind bir çağrı ile başlayan bir dosya arama devam etmek için bu üye işlevi [arayın::FindFile](#findfile).

```
virtual BOOL FindNextFile();
```

### <a name="return-value"></a>Dönüş Değeri

Daha fazla dosya varsa sıfır olmayan; bulunan dosya dizindeki son dosyaysa veya bir hata oluştuysa sıfır. Genişletilmiş hata bilgilerini almak için Win32 işlevini [getLastError'ı](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)arayın. Bulunan dosya dizindeki son dosyaysa veya eşleşen dosya bulunamazsa, `GetLastError` işlev ERROR_NO_MORE_FILES döndürür.

## <a name="cgopherfilefindgetcreationtime"></a><a name="getcreationtime"></a>CGopherFileFind::GetCreationTime

Geçerli dosyaiçin oluşturma süresini alır.

```
virtual BOOL GetCreationTime(FILETIME* pTimeStamp) const;
virtual BOOL GetCreationTime(CTime& refTime) const;
```

### <a name="parameters"></a>Parametreler

*pTimeStamp*<br/>
Dosyanın oluşturulduğu zamanı içeren bir [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) yapısına işaretçi.

*refTime*<br/>
[CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesine başvuru.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; Başarısız olursa 0. `GetCreationTime`yalnızca [FindNextFile](#findnextfile) bu `CGopherFileFind` nesneüzerinde hiç çağrılmadıysa 0 döndürür.

### <a name="remarks"></a>Açıklamalar

Aramadan önce [FindNextFile'ı](#findnextfile) `GetCreationTime`en az bir kez aramalısınız.

> [!NOTE]
> Tüm dosya sistemleri, bu işlev tarafından döndürülen zaman damgasını uygulamak için aynı semantikleri kullanmaz. Bu işlev, temel dosya sistemi veya sunucu zaman özniteliğini tutmayı desteklemiyorsa, diğer zaman damgası işlevleri tarafından döndürülen aynı değeri döndürebilir. Zaman biçimleri hakkında bilgi için [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) yapıya bakın. Bazı işletim sistemlerinde, döndürülen saat dilimi içinde olan dosyanın bulunduğu makineye yereldir. Daha fazla bilgi için Win32 [FileTimeToLocalFileTime](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime) API'sine bakın.

## <a name="cgopherfilefindgetlastaccesstime"></a><a name="getlastaccesstime"></a>CGopherFileFind::GetLastAccessTime

Belirtilen dosyaya en son erişilen saati alır.

```
virtual BOOL GetLastAccessTime(CTime& refTime) const;
virtual BOOL GetLastAccessTime(FILETIME* pTimeStamp) const;
```

### <a name="parameters"></a>Parametreler

*refTime*<br/>
[CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesine başvuru.

*pTimeStamp*<br/>
Dosyaya en son erişilen saati içeren bir [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) yapısına işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; Başarısız olursa 0. `GetLastAccessTime`yalnızca [FindNextFile](#findnextfile) bu `CGopherFileFind` nesneüzerinde hiç çağrılmadıysa 0 döndürür.

### <a name="remarks"></a>Açıklamalar

Aramadan önce [FindNextFile'ı](#findnextfile) `GetLastAccessTime`en az bir kez aramalısınız.

> [!NOTE]
> Tüm dosya sistemleri, bu işlev tarafından döndürülen zaman damgasını uygulamak için aynı semantikleri kullanmaz. Bu işlev, temel dosya sistemi veya sunucu zaman özniteliğini tutmayı desteklemiyorsa, diğer zaman damgası işlevleri tarafından döndürülen aynı değeri döndürebilir. Zaman biçimleri hakkında bilgi için [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) yapıya bakın. Bazı işletim sistemlerinde, döndürülen saat dilimi içinde olan dosyanın bulunduğu makineye yereldir. Daha fazla bilgi için Win32 [FileTimeToLocalFileTime](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime) API'sine bakın.

## <a name="cgopherfilefindgetlastwritetime"></a><a name="getlastwritetime"></a>CGopherFileFind::GetLastWriteTime

Dosya son kez değiştirilsin.

```
virtual BOOL GetLastWriteTime(FILETIME* pTimeStamp) const;
virtual BOOL GetLastWriteTime(CTime& refTime) const;
```

### <a name="parameters"></a>Parametreler

*pTimeStamp*<br/>
Dosyanın en son yazıldığı zamanı içeren bir [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) yapısına işaretçi.

*refTime*<br/>
[CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesine başvuru.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; Başarısız olursa 0. `GetLastWriteTime`yalnızca [FindNextFile](#findnextfile) bu `CGopherFileFind` nesneüzerinde hiç çağrılmadıysa 0 döndürür.

### <a name="remarks"></a>Açıklamalar

Aramadan önce [FindNextFile'ı](#findnextfile) `GetLastWriteTime`en az bir kez aramalısınız.

> [!NOTE]
> Tüm dosya sistemleri, bu işlev tarafından döndürülen zaman damgasını uygulamak için aynı semantikleri kullanmaz. Bu işlev, temel dosya sistemi veya sunucu zaman özniteliğini tutmayı desteklemiyorsa, diğer zaman damgası işlevleri tarafından döndürülen aynı değeri döndürebilir. Zaman biçimleri hakkında bilgi için [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) yapıya bakın. Bazı işletim sistemlerinde, döndürülen saat dilimi içinde olan dosyanın bulunduğu makineye yereldir. Daha fazla bilgi için Win32 [FileTimeToLocalFileTime](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime) API'sine bakın.

## <a name="cgopherfilefindgetlength"></a><a name="getlength"></a>CGopherFileFind::GetLength

Bulunan dosyanın uzunluğunu, baytlarını almak için bu üye işlevini arayın.

```
virtual ULONGLONG GetLength() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bulunan dosyanın baytlarındaki uzunluğu.

### <a name="remarks"></a>Açıklamalar

`GetLength`baytlarda dosya boyutunun değerini almak için [Win32](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) yapısını WIN32_FIND_DATA kullanır.

> [!NOTE]
> MFC 7.0 itibariyle, `GetLength` 64 bit tümseci türlerini destekler. Kitaplığın bu yeni sürümüyle oluşturulmuş daha önce varolan kod, kesilme uyarılarına neden olabilir.

### <a name="example"></a>Örnek

  [CFile::GetLength](../../mfc/reference/cfile-class.md#getlength) (taban sınıf uygulaması) örneğine bakın.

## <a name="cgopherfilefindgetlocator"></a><a name="getlocator"></a>CGopherFileFind::GetLocator

[FindFile](#findfile) gopher dosyasını bulmak için kullandığı [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) nesnealmak için bu üye işlevi arayın.

```
CGopherLocator GetLocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir `CGopherLocator` nesnesi.

## <a name="cgopherfilefindgetscreenname"></a><a name="getscreenname"></a>CGopherFileFind::GetScreenName

Gopher ekranının adını almak için bu üye işlevini arayın.

```
CString GetScreenName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Gopher ekranının adı.

## <a name="cgopherfilefindisdots"></a><a name="isdots"></a>CGopherFileFind::IsDots

Dosyalar arasında yinelerken geçerli dizin ve üst dizin işaretçileri için testler.

```
virtual BOOL IsDots() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bulunan dosyada "." veya ".."adı varsa, bulunan dosyanın aslında bir dizin olduğunu gösterir. Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Aramadan önce [FindNextFile'ı](#findnextfile) `IsDots`en az bir kez aramalısınız.

## <a name="see-also"></a>Ayrıca bkz.

[CFileFind Sınıfı](../../mfc/reference/cfilefind-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CFtpFileFind Sınıf](../../mfc/reference/cftpfilefind-class.md)<br/>
[CFileFind Sınıfı](../../mfc/reference/cfilefind-class.md)<br/>
[CInternetFile Sınıfı](../../mfc/reference/cinternetfile-class.md)<br/>
[CGopherFile Sınıfı](../../mfc/reference/cgopherfile-class.md)<br/>
[Chttpfile Sınıfı](../../mfc/reference/chttpfile-class.md)
