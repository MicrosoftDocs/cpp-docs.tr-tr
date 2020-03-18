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
ms.openlocfilehash: 55c40fc04934f00ccb541a01cce611d9532bee1a
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79418582"
---
# <a name="cgopherfilefind-class"></a>CGopherFileFind sınıfı

Gopher sunucularının Internet dosya aramalarında yardımlıklar.

> [!NOTE]
>  `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` ve üyeleri Windows XP platformunda çalışmadıklarından, ancak önceki platformlarda çalışmaya devam edebileceğinden, bu sınıflar kullanım dışı bırakılmıştır.

## <a name="syntax"></a>Sözdizimi

```
class CGopherFileFind : public CFileFind
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Genel Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CGopherFileFind:: CGopherFileFind](#cgopherfilefind)|`CGopherFileFind` nesnesi oluşturur.|

### <a name="public-methods"></a>Genel Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CGopherFileFind:: FindFile](#findfile)|Gopher sunucusunda bir dosya bulur.|
|[CGopherFileFind:: FindNextFile](#findnextfile)|Önceki bir [FindFile](#findfile)çağrısından bir dosya aramaya devam eder.|
|[CGopherFileFind:: GetCreationTime](#getcreationtime)|Belirtilen dosyanın oluşturulduğu saati alır.|
|[CGopherFileFind:: GetLastAccessTime](#getlastaccesstime)|Belirtilen dosyanın son erişildiği saati alır.|
|[CGopherFileFind:: GetLastWriteTime](#getlastwritetime)|Belirtilen dosyanın son yazıldığı saati alır.|
|[CGopherFileFind:: GetLength](#getlength)|Bulunan dosyanın uzunluğunu bayt cinsinden alır.|
|[CGopherFileFind:: GetLocator](#getlocator)|`CGopherLocator` nesnesi alın.|
|[CGopherFileFind:: GetScreenName](#getscreenname)|Bir gopher ekranının adını alır.|
|[CGopherFileFind:: ısnoktalar](#isdots)|Dosyalar arasında yineleme yaparken geçerli dizin ve üst dizin işaretleyicilerini sınar.|

## <a name="remarks"></a>Açıklamalar

`CGopherFileFind`, arama işlemine başlayan, bir dosyayı bulacak ve bir dosyanın URL 'sini döndüren üye işlevleri içerir.

Internet ve yerel dosya için tasarlanan diğer MFC sınıfları, [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) ve [CFileFind](../../mfc/reference/cfilefind-class.md)' i içerir. `CGopherFileFind`ile birlikte, bu sınıflar, kullanıcının sunucu protokolü, dosya türü veya konumdan (yerel makine ya da uzak bir sunucu) bağımsız olarak belirli dosyaları bulması için sorunsuz bir mekanizma sağlar. HTTP sunucularında arama yapmak için MFC sınıfı olmadığını unutmayın çünkü HTTP, aramalar için gereken doğrudan dosya işlemesini desteklemez.

> [!NOTE]
> `CGopherFileFind`, temel sınıfının [CFileFind](../../mfc/reference/cfilefind-class.md)öğesinin aşağıdaki üye işlevlerini desteklemez:

- [GetRoot](../../mfc/reference/cfilefind-class.md#getroot)

- [GetFileName](../../mfc/reference/cfilefind-class.md#getfilename)

- [GetFilePath](../../mfc/reference/cfilefind-class.md#getfilepath)

- [GetFileTitle](../../mfc/reference/cfilefind-class.md#getfiletitle)

- [GetFileURL](../../mfc/reference/cfilefind-class.md#getfileurl)

Ayrıca, `CGopherFileFind`ile kullanıldığında, `CFileFind` üye işlevi [ısnoktalarla](../../mfc/reference/cfilefind-class.md#isdots) her zaman false 'tur.

`CGopherFileFind` ve diğer WinINet sınıflarını kullanma hakkında daha fazla bilgi için bkz. [Wininet Ile Internet programlama](../../mfc/win32-internet-extensions-wininet.md)makalesi.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CFileFind](../../mfc/reference/cfilefind-class.md)

`CGopherFileFind`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFXINET. h

##  <a name="cgopherfilefind"></a>CGopherFileFind:: CGopherFileFind

Bu üye işlevi bir `CGopherFileFind` nesnesi oluşturmak için çağırılır.

```
explicit CGopherFileFind(
    CGopherConnection* pConnection,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Parametreler

*pConnection*<br/>
[CGopherConnection](../../mfc/reference/cgopherconnection-class.md) nesnesine yönelik bir işaretçi.

*dwContext*<br/>
İşlemin bağlam tanımlayıcısı. *DwContext*hakkında daha fazla bilgi için bkz. **açıklamalar** .

### <a name="remarks"></a>Açıklamalar

*DwContext* için varsayılan değer, MFC tarafından `CGopherFileFind` nesnesini oluşturan [cınternetsession](../../mfc/reference/cinternetsession-class.md) nesnesinden `CGopherFileFind` nesnesine gönderilir. Bir `CGopherFileFind` nesnesi oluşturduğunuzda, bağlam tanımlayıcıyı seçtiğiniz bir değere ayarlamak için varsayılanı geçersiz kılabilirsiniz. Bağlam tanımlayıcısı, tanımlanan nesne üzerinde durum sağlamak için [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) öğesine döndürülür. Bağlam tanımlayıcısı hakkında daha fazla bilgi için [Internet Ilk adımlar: WinINet](../../mfc/wininet-basics.md) makalesine bakın.

##  <a name="findfile"></a>CGopherFileFind:: FindFile

Bir gopher dosyası bulmak için bu üye işlevini çağırın.

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
[CGopherLocator](../../mfc/reference/cgopherlocator-class.md) nesnesine bir başvuru.

*pstrString*<br/>
Dosya adını içeren bir dize işaretçisi.

*dwFlags*<br/>
Bu oturumun nasıl işleneceğini açıklayan bayraklar. Geçerli bayraklar şunlardır:

- Yerel olarak önbelleğe alınmış olsa bile, uzak sunucudan verileri al INTERNET_FLAG_RELOAD.

- INTERNET_FLAG_DONT_CACHE, yerel olarak veya herhangi bir ağ geçitlerinde bulunan verileri önbelleğe almaz.

- Güvenli Yuva Katmanı veya PCT ile tel üzerinde güvenli işlemler INTERNET_FLAG_SECURE Isteyin. Bu bayrak yalnızca HTTP istekleri için geçerlidir.

- Mümkünse INTERNET_FLAG_USE_EXISTING, her istek için yeni bir oturum oluşturmak yerine yeni `FindFile` istekleri için sunucuya mevcut bağlantıları yeniden kullanın.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0. Genişletilmiş hata bilgilerini almak için, WIN32 [işlevini çağırın](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror).

### <a name="remarks"></a>Açıklamalar

İlk Gopher nesnesini almak için `FindFile` çağrıldıktan sonra, sonraki Gopher dosyalarını almak için [FindNextFile](#findnextfile) öğesini çağırabilirsiniz.

##  <a name="findnextfile"></a>CGopherFileFind:: FindNextFile

Bir dosya aramasının bir [CGopherFileFind:: FindFile](#findfile)çağrısıyla çalışmaya devam etmesi için bu üye işlevini çağırın.

```
virtual BOOL FindNextFile();
```

### <a name="return-value"></a>Dönüş Değeri

Daha fazla dosya varsa sıfır dışı; Dosya, dizinde sonuncu ise veya bir hata oluştuysa sıfır olur. Genişletilmiş hata bilgilerini almak için, WIN32 [işlevini çağırın](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror). Bulunan dosya dizindeki son dosya ise veya eşleşen dosya bulunamazsa, `GetLastError` işlevi ERROR_NO_MORE_FILES döndürür.

##  <a name="getcreationtime"></a>CGopherFileFind:: GetCreationTime

Geçerli dosyanın oluşturulma saatini alır.

```
virtual BOOL GetCreationTime(FILETIME* pTimeStamp) const;
virtual BOOL GetCreationTime(CTime& refTime) const;
```

### <a name="parameters"></a>Parametreler

*pTimeStamp*<br/>
Dosya oluşturulduğu saati içeren bir [filetime](/windows/win32/api/minwinbase/ns-minwinbase-filetime) yapısına yönelik işaretçi.

*refTime*<br/>
[CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesine bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; başarısız ise 0. `GetCreationTime` yalnızca [FindNextFile](#findnextfile) bu `CGopherFileFind` nesnesinde çağrılmadıysa 0 değerini döndürür.

### <a name="remarks"></a>Açıklamalar

`GetCreationTime`çağrılmadan önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir.

> [!NOTE]
>  Tüm dosya sistemleri bu işlev tarafından döndürülen zaman damgasını uygulamak için aynı semantiğini kullanmaz. Bu işlev, temeldeki dosya sistemi veya sunucusu zaman özniteliğini tutmayı desteklemiyorsa, diğer zaman damgası işlevleri tarafından döndürülen değeri döndürebilir. Zaman biçimleri hakkında bilgi için [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) yapısına bakın. Bazı işletim sistemlerinde döndürülen süre, makinenin yerel olarak bulunduğu saat dilimindedir. Daha fazla bilgi için bkz. Win32 [FileTimeToLocalFileTime](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime) API.

##  <a name="getlastaccesstime"></a>CGopherFileFind:: GetLastAccessTime

Belirtilen dosyanın son erişildiği saati alır.

```
virtual BOOL GetLastAccessTime(CTime& refTime) const;
virtual BOOL GetLastAccessTime(FILETIME* pTimeStamp) const;
```

### <a name="parameters"></a>Parametreler

*refTime*<br/>
[CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesine bir başvuru.

*pTimeStamp*<br/>
Dosyanın son erişildiği saati içeren bir [filetime](/windows/win32/api/minwinbase/ns-minwinbase-filetime) yapısına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; başarısız ise 0. `GetLastAccessTime` yalnızca [FindNextFile](#findnextfile) bu `CGopherFileFind` nesnesinde çağrılmadıysa 0 değerini döndürür.

### <a name="remarks"></a>Açıklamalar

`GetLastAccessTime`çağrılmadan önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir.

> [!NOTE]
>  Tüm dosya sistemleri bu işlev tarafından döndürülen zaman damgasını uygulamak için aynı semantiğini kullanmaz. Bu işlev, temeldeki dosya sistemi veya sunucusu zaman özniteliğini tutmayı desteklemiyorsa, diğer zaman damgası işlevleri tarafından döndürülen değeri döndürebilir. Zaman biçimleri hakkında bilgi için [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) yapısına bakın. Bazı işletim sistemlerinde döndürülen süre, makinenin yerel olarak bulunduğu saat dilimindedir. Daha fazla bilgi için bkz. Win32 [FileTimeToLocalFileTime](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime) API.

##  <a name="getlastwritetime"></a>CGopherFileFind:: GetLastWriteTime

Dosyanın son değiştirildiği zamanı alır.

```
virtual BOOL GetLastWriteTime(FILETIME* pTimeStamp) const;
virtual BOOL GetLastWriteTime(CTime& refTime) const;
```

### <a name="parameters"></a>Parametreler

*pTimeStamp*<br/>
Dosyanın son yazıldığı saati içeren bir [filetime](/windows/win32/api/minwinbase/ns-minwinbase-filetime) yapısına yönelik işaretçi.

*refTime*<br/>
[CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesine bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; başarısız ise 0. `GetLastWriteTime` yalnızca [FindNextFile](#findnextfile) bu `CGopherFileFind` nesnesinde çağrılmadıysa 0 değerini döndürür.

### <a name="remarks"></a>Açıklamalar

`GetLastWriteTime`çağrılmadan önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir.

> [!NOTE]
>  Tüm dosya sistemleri bu işlev tarafından döndürülen zaman damgasını uygulamak için aynı semantiğini kullanmaz. Bu işlev, temeldeki dosya sistemi veya sunucusu zaman özniteliğini tutmayı desteklemiyorsa, diğer zaman damgası işlevleri tarafından döndürülen değeri döndürebilir. Zaman biçimleri hakkında bilgi için [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) yapısına bakın. Bazı işletim sistemlerinde döndürülen süre, makinenin yerel olarak bulunduğu saat dilimindedir. Daha fazla bilgi için bkz. Win32 [FileTimeToLocalFileTime](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime) API.

##  <a name="getlength"></a>CGopherFileFind:: GetLength

Bulunan dosyanın uzunluğunu bayt olarak almak için bu üye işlevini çağırın.

```
virtual ULONGLONG GetLength() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bulunan dosyanın bayt cinsinden uzunluğu.

### <a name="remarks"></a>Açıklamalar

`GetLength`, dosya boyutu değerini bayt olarak almak için [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) Win32 yapısını kullanır.

> [!NOTE]
>  MFC 7,0 itibariyle, `GetLength` 64 bit tamsayı türlerini destekler. Kitaplığın bu yeni sürümüyle oluşturulan önceden varolan kod, kesme uyarılarına neden olabilir.

### <a name="example"></a>Örnek

  [CFile:: GetLength](../../mfc/reference/cfile-class.md#getlength) (temel sınıf uygulama) için örneğe bakın.

##  <a name="getlocator"></a>CGopherFileFind:: GetLocator

[FindFile](#findfile) 'ın Gopher dosyasını bulmak Için kullandığı [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) nesnesini almak için bu üye işlevi çağırın.

```
CGopherLocator GetLocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir `CGopherLocator` nesnesi.

##  <a name="getscreenname"></a>CGopherFileFind:: GetScreenName

Gopher ekranının adını almak için bu üye işlevini çağırın.

```
CString GetScreenName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Gopher ekranının adı.

##  <a name="isdots"></a>CGopherFileFind:: ısnoktalar

Dosyalar arasında yineleme yaparken geçerli dizin ve üst dizin işaretleyicilerini sınar.

```
virtual BOOL IsDots() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bulunan dosyanın adı "." veya ".." ise, bulunan dosyanın gerçekten bir dizin olduğunu gösterir. Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`IsDots`çağrılmadan önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[CFileFind Sınıfı](../../mfc/reference/cfilefind-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CFtpFileFind Sınıfı](../../mfc/reference/cftpfilefind-class.md)<br/>
[CFileFind Sınıfı](../../mfc/reference/cfilefind-class.md)<br/>
[CInternetFile Sınıfı](../../mfc/reference/cinternetfile-class.md)<br/>
[CGopherFile Sınıfı](../../mfc/reference/cgopherfile-class.md)<br/>
[CHttpFile Sınıfı](../../mfc/reference/chttpfile-class.md)
