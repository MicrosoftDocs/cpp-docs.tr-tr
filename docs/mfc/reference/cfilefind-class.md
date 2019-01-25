---
title: CFileFind sınıfı
ms.date: 11/04/2016
f1_keywords:
- CFileFind
- AFX/CFileFind
- AFX/CFileFind::CFileFind
- AFX/CFileFind::Close
- AFX/CFileFind::FindFile
- AFX/CFileFind::FindNextFile
- AFX/CFileFind::GetCreationTime
- AFX/CFileFind::GetFileName
- AFX/CFileFind::GetFilePath
- AFX/CFileFind::GetFileTitle
- AFX/CFileFind::GetFileURL
- AFX/CFileFind::GetLastAccessTime
- AFX/CFileFind::GetLastWriteTime
- AFX/CFileFind::GetLength
- AFX/CFileFind::GetRoot
- AFX/CFileFind::IsArchived
- AFX/CFileFind::IsCompressed
- AFX/CFileFind::IsDirectory
- AFX/CFileFind::IsDots
- AFX/CFileFind::IsHidden
- AFX/CFileFind::IsNormal
- AFX/CFileFind::IsReadOnly
- AFX/CFileFind::IsSystem
- AFX/CFileFind::IsTemporary
- AFX/CFileFind::MatchesMask
- AFX/CFileFind::CloseContext
- AFX/CFileFind::m_pTM
helpviewer_keywords:
- CFileFind [MFC], CFileFind
- CFileFind [MFC], Close
- CFileFind [MFC], FindFile
- CFileFind [MFC], FindNextFile
- CFileFind [MFC], GetCreationTime
- CFileFind [MFC], GetFileName
- CFileFind [MFC], GetFilePath
- CFileFind [MFC], GetFileTitle
- CFileFind [MFC], GetFileURL
- CFileFind [MFC], GetLastAccessTime
- CFileFind [MFC], GetLastWriteTime
- CFileFind [MFC], GetLength
- CFileFind [MFC], GetRoot
- CFileFind [MFC], IsArchived
- CFileFind [MFC], IsCompressed
- CFileFind [MFC], IsDirectory
- CFileFind [MFC], IsDots
- CFileFind [MFC], IsHidden
- CFileFind [MFC], IsNormal
- CFileFind [MFC], IsReadOnly
- CFileFind [MFC], IsSystem
- CFileFind [MFC], IsTemporary
- CFileFind [MFC], MatchesMask
- CFileFind [MFC], CloseContext
- CFileFind [MFC], m_pTM
ms.assetid: 9990068c-b023-4114-9580-a50182d15240
ms.openlocfilehash: 9eb192e546bcfbba385beea4f1716ce03bbc8ade
ms.sourcegitcommit: c85c8a1226d8fbbaa29f4691ed719f8e6cc6575c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/24/2019
ms.locfileid: "54894061"
---
# <a name="cfilefind-class"></a>CFileFind sınıfı

Yerel dosya aramaları gerçekleştirir ve temel sınıfı olan [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) ve [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md), Internet dosyalarında gerçekleştirin.

## <a name="syntax"></a>Sözdizimi

```
class CFileFind : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CFileFind::CFileFind](#cfilefind)|Oluşturur bir `CFileFind` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CFileFind::Close](#close)|Arama isteği kapatılır.|
|[CFileFind::FindFile](#findfile)|Belirtilen dosya adı için bir dizini arar.|
|[CFileFind::FindNextFile](#findnextfile)|Bir önceki çağrıya bir dosya aramaya devam [FindFile](#findfile).|
|[CFileFind::GetCreationTime](#getcreationtime)|Dosyanın oluşturulduğu saati alır.|
|[CFileFind::GetFileName](#getfilename)|Bulunan dosyanın uzantısı dahil adını alır|
|[CFileFind::GetFilePath](#getfilepath)|Bulunan dosyasının tam yolunu alır.|
|[CFileFind::GetFileTitle](#getfiletitle)|Bulunan dosyayı başlığını alır. Başlık uzantısı içermez.|
|[CFileFind::GetFileURL](#getfileurl)|Dosya yolu, bulunan dosyanın dahil olmak üzere URL'yi alır.|
|[CFileFind::GetLastAccessTime](#getlastaccesstime)|Dosyanın son erişilme zamanı alır.|
|[CFileFind::GetLastWriteTime](#getlastwritetime)|Dosyanın en son değiştirildi ve kaydedilen zaman alır.|
|[CFileFind::GetLength](#getlength)|Bulunan dosyasının bayt cinsinden uzunluğunu alır.|
|[CFileFind::GetRoot](#getroot)|Kök dizininde bulunan dosyayı alır.|
|[CFileFind::IsArchived](#isarchived)|Bulunan dosyayı arşivlenir belirler.|
|[CFileFind::IsCompressed](#iscompressed)|Bulunan dosyayı sıkıştırılmış olup olmadığını belirler.|
|[CFileFind::IsDirectory](#isdirectory)|Dosyayı bir dizin olup olmadığını belirler.|
|[CFileFind::IsDots](#isdots)|Bulunan dosya adını adına sahip olup olmadığını belirler "."veya"...", aslında bir dizin olduğunu gösteren.|
|[CFileFind::IsHidden](#ishidden)|Bulunan dosyayı gizli olduğunu belirler.|
|[CFileFind::IsNormal](#isnormal)|Bulunan dosyayı normal olup olmadığını belirler (diğer bir deyişle, diğer özniteliklere sahip değildir).|
|[CFileFind::IsReadOnly](#isreadonly)|Bulunan dosya salt okunur olup olmadığını belirler.|
|[CFileFind::IsSystem](#issystem)|Dosyayı bir sistem dosyası olup olmadığını belirler.|
|[CFileFind::IsTemporary](#istemporary)|Bulunan dosyayı geçici olup olmadığını belirler.|
|[CFileFind::MatchesMask](#matchesmask)|Dosyanın bulunması istenen dosya özniteliklerini gösterir.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CFileFind::CloseContext](#closecontext)|Geçerli arama tanıtıcı tarafından belirtilen dosyayı kapatır.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CFileFind::m_pTM](#m_ptm)|İşaretçi bir `CAtlTransactionManager` nesne.|

## <a name="remarks"></a>Açıklamalar

`CFileFind` bir arama başlatır, bir dosyayı bulun ve başlık, ad veya dosyanın yolunu döndürür üye işlevleri içerir. Internet aramalar, üye işlevi için [GetFileURL](#getfileurl) dosyanın URL'sini döndürür.

`CFileFind` diğer iki MFC sınıfları için temel sınıfı, belirli sunucu türleri aramak için tasarlanmıştır: `CGopherFileFind` özellikle gopher sunucularıyla çalışır ve `CFtpFileFind` özellikle FTP sunucuları ile çalışır. Birlikte, bu üç sınıflar istemcinin dosyaları, sunucu protokolü, dosya türü veya konum bağımsız olarak yerel makine veya uzak bir sunucuya bulmak sorunsuz bir mekanizma sağlar.

Aşağıdaki kod her dosyanın adı yazdırma geçerli dizindeki tüm dosyaları numaralandırır:

[!code-cpp[NVC_MFCFiles#31](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_1.cpp)]

Bu kod örneği basit tutmak için C++ Standart Kitaplığı kullanan `cout` sınıfı. `cout` Satır yerine bir çağrı `CListBox::AddString`, örneğin, bir grafik kullanıcı arabirimi ile bir programda.

Nasıl kullanılacağı hakkında daha fazla bilgi için `CFileFind` ve diğer WinINet sınıfları başlıklı makaleye bakın [Winınet'in Internet programlama](../../mfc/win32-internet-extensions-wininet.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CFileFind`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

##  <a name="cfilefind"></a>  CFileFind::CFileFind

Bu üye işlevi aldığında çağrılan bir `CFileFind` nesnesi oluşturulur.

```
CFileFind();
CFileFind(CAtlTransactionManager* pTM);
```

### <a name="parameters"></a>Parametreler

*pTM*<br/>
CAtlTransactionManager nesne işaretçisi

### <a name="example"></a>Örnek

  Örneğin bakın [CFileFind::GetFileName](#getfilename).

##  <a name="close"></a>  CFileFind::Close

Aramayı sonlandırmak, bağlam Sıfırla ve tüm kaynakları serbest bırakmak için bu üye işlevini çağırın.

```
void Close();
```

### <a name="remarks"></a>Açıklamalar

Arama sonra `Close`, yeni bir oluşturmak zorunda değilsiniz `CFileFind` örneği çağırmadan önce [FindFile](#findfile) yeni aramaya başlamak için.

### <a name="example"></a>Örnek

  Örneğin bakın [CFileFind::GetFileName](#getfilename).

##  <a name="closecontext"></a>  CFileFind::CloseContext

Geçerli arama tanıtıcı tarafından belirtilen dosyayı kapatır.

```
virtual void CloseContext();
```

### <a name="remarks"></a>Açıklamalar

Arama tanıtıcısı geçerli değeri tarafından belirtilen dosyayı kapatır. Bu işlev varsayılan davranışı değiştirmek için geçersiz kılın.

Çağırmalısınız [FindFile](#findfile) veya ['larını](#findnextfile) geçerli arama tanıtıcısını almak için en az bir kez işlevleri. `FindFile` Ve `FindNextFile` işlevleri belirtilen adla eşleşen adlara sahip dosyaları bulmak için arama tanıtıcı kullanın.

##  <a name="findfile"></a>  CFileFind::FindFile

Dosya arama açmak için bu üye işlevini çağırın.

```
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,
    DWORD dwUnused = 0);
```

### <a name="parameters"></a>Parametreler

*pstrName*<br/>
Bulmak için dosya adını içeren bir dize işaretçisi. NULL geçirirseniz verilen *pstrName*, `FindFile` mu bir joker karakter (*.\*) arama.

*dwUnused*<br/>
Yapmak için ayrılmış `FindFile` türetilen sınıflarla polimorfik. 0 olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0. Genişletilmiş hata bilgilerini almak için Win32 işlevini çağırmak [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360).

### <a name="remarks"></a>Açıklamalar

Arama sonra `FindFile` dosya aramaya başlamak için çağrı ['larını](#findnextfile) sonraki dosyaları almak için. Çağırmalısınız `FindNextFile` üye işlevleri aşağıdaki öznitelik birini çağırmadan önce en az bir kez:

- [GetCreationTime](#getcreationtime)

- [GetFileName](#getfilename)

- [GetFileTitle](#getfiletitle)

- [GetFilePath](#getfilepath)

- [GetFileURL](#getfileurl)

- [GetLastAccessTime](#getlastaccesstime)

- [GetLastWriteTime](#getlastwritetime)

- [GetLength](#getlength)

- [GetRoot](#getroot)

- [IsArchived](#isarchived)

- [IsCompressed](#iscompressed)

- [IsDirectory](#isdirectory)

- [IsDots](#isdots)

- [IsHidden](#ishidden)

- [IsNormal](#isnormal)

- [IsReadOnly](#isreadonly)

- [IsSystem](#issystem)

- [IsTemporary](#istemporary)

- [MatchesMask](#matchesmask)

### <a name="example"></a>Örnek

  Örneğin bakın [CFileFind::IsDirectory](#isdirectory).

##  <a name="findnextfile"></a>  CFileFind::FindNextFile

Bir önceki çağrıya bir dosya aramaya devam etmek için bu üye işlevi çağrısı [FindFile](#findfile).

```
virtual BOOL FindNextFile();
```

### <a name="return-value"></a>Dönüş Değeri

Daha fazla dosya yoksa sıfır; sıfır. dosya bulundu sonuncu dizininde olması veya bir hata oluştu. Genişletilmiş hata bilgilerini almak için Win32 işlevini çağırmak [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360). Son dosya dizininde dosyası bulunamadı veya hiçbir eşleşen dosyaları bulunabilir, `GetLastError` ERROR_NO_MORE_FILES işlevi döndürür.

### <a name="remarks"></a>Açıklamalar

Çağırmalısınız `FindNextFile` üye işlevleri aşağıdaki öznitelik birini çağırmadan önce en az bir kez:

- [GetCreationTime](#getcreationtime)

- [GetFileName](#getfilename)

- [GetFileTitle](#getfiletitle)

- [GetFilePath](#getfilepath)

- [GetFileURL](#getfileurl)

- [GetLastAccessTime](#getlastaccesstime)

- [GetLastWriteTime](#getlastwritetime)

- [GetLength](#getlength)

- [GetRoot](#getroot)

- [IsArchived](#isarchived)

- [IsCompressed](#iscompressed)

- [IsDirectory](#isdirectory)

- [IsDots](#isdots)

- [IsHidden](#ishidden)

- [IsNormal](#isnormal)

- [IsReadOnly](#isreadonly)

- [IsSystem](#issystem)

- [IsTemporary](#istemporary)

- [MatchesMask](#matchesmask)

`FindNextFile` Win32 işlevini sarmalayan ['larını](/windows/desktop/api/fileapi/nf-fileapi-findnextfilea).

### <a name="example"></a>Örnek

  Örneğin bakın [CFileFind::IsDirectory](#isdirectory).

##  <a name="getcreationtime"></a>  CFileFind::GetCreationTime

Belirtilen dosyanın oluşturulduğu zaman almak için bu üye işlevini çağırın.

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

Başarılı olursa sıfır dışı; işlem başarısız olursa 0. `GetCreationTime` yalnızca 0 döndürür ['larını](#findnextfile) hiçbir zaman bu çağrıldıktan `CFileFind` nesne.

### <a name="remarks"></a>Açıklamalar

Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `GetCreationTime`.

> [!NOTE]
>  Tüm dosya sistemleri, bu işlev tarafından döndürülen zaman damgası uygulamak için aynı semantiğe kullanın. Bu işlev, temel alınan dosya sistemi veya sunucu zaman öznitelik tutma desteklemiyorsa, diğer zaman damgası işlevleri tarafından döndürülen aynı değer döndürebilir. Bkz: [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) yapısı saat biçimleri hakkında bilgi için. Bazı işletim Sistemleri'nde döndürülen saat dilimi yerel makineye olan dosyasının bulunduğu saat şöyledir. Win32 bkz [FileTimeToLocalFileTime](/windows/desktop/api/fileapi/nf-fileapi-filetimetolocalfiletime) API daha fazla bilgi için.

### <a name="example"></a>Örnek

  Örneğin bakın [CFileFind::GetLength](#getlength).

##  <a name="getfilename"></a>  CFileFind::GetFileName

Bulunan dosya adını almak için bu üye işlevini çağırın.

```
virtual CString GetFileName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kısa bir süre önce bulunan dosya adı.

### <a name="remarks"></a>Açıklamalar

Çağırmalısınız ['larını](#findnextfile) GetFileName çağırmadan önce en az bir kez.

`GetFileName` üç biri `CFileFind` üye işlevleri, dosya adının biçimi döndürür. Aşağıdaki liste, üç ve nasıl farklılık açıklanmaktadır:

- `GetFileName` Dosya adı uzantısı dahil olmak üzere, döndürür. Örneğin, çağırma `GetFileName` dosyası hakkında bir kullanıcı iletisini oluşturmak için *c:\myhtml\myfile.txt* dosya adını döndürür *myfile.txt*.

- [GetFilePath](#getfilepath) tüm dosya yolunu döndürür. Örneğin, çağırma `GetFilePath` dosyası hakkında bir kullanıcı iletisini oluşturmak için *c:\myhtml\myfile.txt* dosya yolunu döndürür *c:\myhtml\myfile.txt*.

- [GetFileTitle](#getfiletitle) dosya uzantısı hariç dosya adını döndürür. Örneğin, çağırma `GetFileTitle` dosyası hakkında bir kullanıcı iletisini oluşturmak için *c:\myhtml\myfile.txt* dosyanın başlığı döndürür *myfile*.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#32](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_2.cpp)]

##  <a name="getfilepath"></a>  CFileFind::GetFilePath

Belirtilen dosyanın tam yolunu almak için bu üye işlevini çağırın.

```
virtual CString GetFilePath() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belirtilen dosya yolu.

### <a name="remarks"></a>Açıklamalar

Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `GetFilePath`.

`GetFilePath` üç biri `CFileFind` üye işlevleri, dosya adının biçimi döndürür. Aşağıdaki liste, üç ve nasıl farklılık açıklanmaktadır:

- [GetFileName](#getfilename) uzantısı dahil olmak üzere dosya adını döndürür. Örneğin, çağırma `GetFileName` dosyası hakkında bir kullanıcı iletisini oluşturmak için *c:\myhtml\myfile.txt* dosya adını döndürür *myfile.txt*.

- `GetFilePath` Tüm dosya yolunu döndürür. Örneğin, çağırma `GetFilePath` dosyası hakkında bir kullanıcı iletisini oluşturmak için `c:\myhtml\myfile.txt` dosya yolunu döndürür `c:\myhtml\myfile.txt`.

- [GetFileTitle](#getfiletitle) dosya uzantısı hariç dosya adını döndürür. Örneğin, çağırma `GetFileTitle` dosyası hakkında bir kullanıcı iletisini oluşturmak için *c:\myhtml\myfile.txt* dosyanın başlığı döndürür *myfile*.

### <a name="example"></a>Örnek

  Örneğin bakın [CFileFind::GetFileName](#getfilename).

##  <a name="getfiletitle"></a>  CFileFind::GetFileTitle

Bulunan dosyayı başlığını almak için bu üye işlevini çağırın.

```
virtual CString GetFileTitle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dosyanın başlığı.

### <a name="remarks"></a>Açıklamalar

Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `GetFileTitle`.

`GetFileTitle` üç biri `CFileFind` üye işlevleri, dosya adının biçimi döndürür. Aşağıdaki liste, üç ve nasıl farklılık açıklanmaktadır:

- [GetFileName](#getfilename) uzantısı dahil olmak üzere dosya adını döndürür. Örneğin, çağırma `GetFileName` dosyası hakkında bir kullanıcı iletisini oluşturmak için *c:\myhtml\myfile.txt* dosya adını döndürür *myfile.txt*.

- [GetFilePath](#getfilepath) tüm dosya yolunu döndürür. Örneğin, çağırma `GetFilePath` dosyası hakkında bir kullanıcı iletisini oluşturmak için *c:\myhtml\myfile.txt* dosya yolunu döndürür *c:\myhtml\myfile.txt*.

- `GetFileTitle` Dosya uzantısı hariç dosya adını döndürür. Örneğin, çağırma `GetFileTitle` dosyası hakkında bir kullanıcı iletisini oluşturmak için *c:\myhtml\myfile.txt* dosyanın başlığı döndürür *myfile*.

### <a name="example"></a>Örnek

  Örneğin bakın [CFileFind::GetFileName](#getfilename).

##  <a name="getfileurl"></a>  CFileFind::GetFileURL

Belirtilen URL almak için bu üye işlevini çağırın.

```
virtual CString GetFileURL() const;
```

### <a name="return-value"></a>Dönüş Değeri

Tam URL.

### <a name="remarks"></a>Açıklamalar

Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `GetFileURL`.

`GetFileURL` üye işlevine benzer [GetFilePath](#getfilepath)formda URL'yi döndürür, dışında `file://path`. Örneğin, çağırma `GetFileURL` tam URL'sini almak için *myfile.txt* URL'yi döndürür `file://c:\myhtml\myfile.txt`.

### <a name="example"></a>Örnek

  Örneğin bakın [CFileFind::GetFileName](#getfilename).

##  <a name="getlastaccesstime"></a>  CFileFind::GetLastAccessTime

Belirtilen dosya son erişilme zamanı almak için bu üye işlevini çağırın.

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

Başarılı olursa sıfır dışı; işlem başarısız olursa 0. `GetLastAccessTime` yalnızca 0 döndürür ['larını](#findnextfile) hiçbir zaman bu çağrıldıktan `CFileFind` nesne.

### <a name="remarks"></a>Açıklamalar

Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `GetLastAccessTime`.

> [!NOTE]
>  Tüm dosya sistemleri, bu işlev tarafından döndürülen zaman damgası uygulamak için aynı semantiğe kullanın. Bu işlev, temel alınan dosya sistemi veya sunucu zaman öznitelik tutma desteklemiyorsa, diğer zaman damgası işlevleri tarafından döndürülen aynı değer döndürebilir. Bkz: [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) yapısı saat biçimleri hakkında bilgi için. Bazı işletim Sistemleri'nde döndürülen saat dilimi yerel makineye olan dosyasının bulunduğu saat şöyledir. Win32 bkz [FileTimeToLocalFileTime](/windows/desktop/api/fileapi/nf-fileapi-filetimetolocalfiletime) API daha fazla bilgi için.

### <a name="example"></a>Örnek

  Örneğin bakın [CFileFind::GetLength](#getlength).

##  <a name="getlastwritetime"></a>  CFileFind::GetLastWriteTime

Dosya değiştirildi son zamanı almak için bu üye işlevini çağırın.

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

Başarılı olursa sıfır dışı; işlem başarısız olursa 0. `GetLastWriteTime` yalnızca 0 döndürür ['larını](#findnextfile) hiçbir zaman bu çağrıldıktan `CFileFind` nesne.

### <a name="remarks"></a>Açıklamalar

Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `GetLastWriteTime`.

> [!NOTE]
>  Tüm dosya sistemleri, bu işlev tarafından döndürülen zaman damgası uygulamak için aynı semantiğe kullanın. Bu işlev, temel alınan dosya sistemi veya sunucu zaman öznitelik tutma desteklemiyorsa, diğer zaman damgası işlevleri tarafından döndürülen aynı değer döndürebilir. Bkz: [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) yapısı saat biçimleri hakkında bilgi için. Bazı işletim Sistemleri'nde döndürülen saat dilimi yerel makineye olan dosyasının bulunduğu saat şöyledir. Win32 bkz [FileTimeToLocalFileTime](/windows/desktop/api/fileapi/nf-fileapi-filetimetolocalfiletime) API daha fazla bilgi için.

### <a name="example"></a>Örnek

  Örneğin bakın [CFileFind::GetLength](#getlength).

##  <a name="getlength"></a>  CFileFind::GetLength

Bulunan dosyasının bayt cinsinden uzunluğunu almak için bu üye işlevini çağırın.

```
ULONGLONG GetLength() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bulunan dosyasının bayt cinsinden uzunluğu.

### <a name="remarks"></a>Açıklamalar

Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `GetLength`.

`GetLength` Win32 yapısını kullanır [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) alın ve bayt cinsinden boyutunu değerini döndürür.

> [!NOTE]
>  MFC 7.0 itibarıyla `GetLength` 64-bit tamsayı türlerini destekler. Daha önce bu kitaplığı daha yeni sürümü ile oluşturulmuş var olan kod kesme uyarıların sonuçlanabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#33](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_3.cpp)]

##  <a name="getroot"></a>  CFileFind::GetRoot

Bulunan dosyasının kök almak için bu üye işlevini çağırın.

```
virtual CString GetRoot() const;
```

### <a name="return-value"></a>Dönüş Değeri

Etkin arama kökü.

### <a name="remarks"></a>Açıklamalar

Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `GetRoot`.

Bu üye işlevi, bir aramayı başlatmak için kullanılan yol adı ve sürücü tanımlayıcısı döndürür. Örneğin, çağırma [FindFile](#findfile) ile `*.dat` sonuçlanır `GetRoot` boş bir dizeyi döndürür. Bir yol gibi geçirme `c:\windows\system\*.dll`, `FindFile` sonuçları `GetRoot` döndüren `c:\windows\system\`.

### <a name="example"></a>Örnek

  Örneğin bakın [CFileFind::GetFileName](#getfilename).

##  <a name="isarchived"></a>  CFileFind::IsArchived

Bulunan dosyayı arşivlenir belirlemek için bu üye işlevini çağırın.

```
BOOL IsArchived() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Uygulamaların yedeklenmesini ya da FILE_ATTRIBUTE_ARCHIVE, tanımlanan dosya özniteliği kaldırılmış olan bir arşiv dosyasını işaretlemek [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) yapısı.

Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `IsArchived`.

Üye işlevi görmek [MatchesMask](#matchesmask) dosya öznitelikleri tam listesi için.

### <a name="example"></a>Örnek

  Örneğin bakın [CFileFind::GetLength](#getlength).

##  <a name="iscompressed"></a>  CFileFind::IsCompressed

Bulunan dosyayı sıkıştırılmış olup olmadığını belirlemek için bu üye işlevini çağırın.

```
BOOL IsCompressed() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Sıkıştırılmış bir dosya FILE_ATTRIBUTE_COMPRESSED ile işaretlenmiş, tanımlanan dosya özniteliği [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) yapısı. Bir dosya için bu öznitelik, sıkıştırılmış dosyasındaki verilerin tümünü gösterir. Bir dizin için bu öznitelik, sıkıştırma yeni oluşturulan dosyalar ve alt dizinler için varsayılan olduğunu gösterir.

Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `IsCompressed`.

Üye işlevi görmek [MatchesMask](#matchesmask) dosya öznitelikleri tam listesi için.

### <a name="example"></a>Örnek

  Örneğin bakın [CFileFind::GetLength](#getlength).

##  <a name="isdirectory"></a>  CFileFind::IsDirectory

Dosyayı bir dizin olup olmadığını belirlemek için bu üye işlevini çağırın.

```
BOOL IsDirectory() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bir dizine bir dosya FILE_ATTRIBUTE_DIRECTORY tanımlanan dosya özniteliği olarak ile işaretlenen [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) yapısı.

Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `IsDirectory`.

Üye işlevi görmek [MatchesMask](#matchesmask) dosya öznitelikleri tam listesi için.

### <a name="example"></a>Örnek

Bu küçük bir program recurses C:\ sürücüsüne her dizin ve dizin adı yazdırır.

[!code-cpp[NVC_MFCFiles#34](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_4.cpp)]

##  <a name="isdots"></a>  CFileFind::IsDots

Geçerli dizin ve üst dizini işaretçileri için dosyaları aracılığıyla yineleme sırasında test etmek için bu üye işlevini çağırın.

```
virtual BOOL IsDots() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sıfır dışında bulunan dosya adı varsa "."veya"...", bulunan dosyanın aslında bir dizin olduğunu gösterir. Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `IsDots`.

### <a name="example"></a>Örnek

  Örneğin bakın [CFileFind::IsDirectory](#isdirectory).

##  <a name="ishidden"></a>  CFileFind::IsHidden

Bulunan dosyayı gizli olduğunu belirlemek için bu üye işlevini çağırın.

```
BOOL IsHidden() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Dosya özniteliği FILE_ATTRIBUTE_HIDDEN ile işaretlenmiş olduğundan, gizli dosyaları tanımlanan içinde [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) yapısı. Gizli bir dosya bir sıradan dizin listesinde bulunmaz.

Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `IsHidden`.

Üye işlevi görmek [MatchesMask](#matchesmask) dosya öznitelikleri tam listesi için.

### <a name="example"></a>Örnek

  Örneğin bakın [CFileFind::GetLength](#getlength).

##  <a name="isnormal"></a>  CFileFind::IsNormal

Bulunan dosyayı normal bir dosya olup olmadığını belirlemek için bu üye işlevini çağırın.

```
BOOL IsNormal() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

FILE_ATTRIBUTE_NORMAL ile işaretlenmiş dosyaları, dosya özniteliği içinde tanımlanan [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) yapısı. Normal bir dosya kümesi özniteliklere sahip değildir. Diğer tüm dosya öznitelikleri, bu özniteliği geçersiz kılar.

Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `IsNormal`.

Üye işlevi görmek [MatchesMask](#matchesmask) dosya öznitelikleri tam listesi için.

### <a name="example"></a>Örnek

  Örneğin bakın [CFileFind::GetLength](#getlength).

##  <a name="isreadonly"></a>  CFileFind::IsReadOnly

Bulunan dosya salt okunur olup olmadığını belirlemek için bu üye işlevini çağırın.

```
BOOL IsReadOnly() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Salt okunur bir dosya FILE_ATTRIBUTE_READONLY ile işaretlenmiş, tanımlanan dosya özniteliği [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) yapısı. Uygulama böyle bir dosya okuyabilir, ancak yazma veya silin.

Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `IsReadOnly`.

Üye işlevi görmek [MatchesMask](#matchesmask) dosya öznitelikleri tam listesi için.

### <a name="example"></a>Örnek

  Örneğin bakın [CFileFind::GetLength](#getlength).

##  <a name="issystem"></a>  CFileFind::IsSystem

Dosyayı bir sistem dosyası olup olmadığını belirlemek için bu üye işlevini çağırın.

```
BOOL IsSystem() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bir sistem dosyası FILE_ATTRIBUTE_SYSTEM ile işaretlenmiş, tanımlanan dosya özniteliği [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) yapısı. Bir sistem dosyası parçası olan veya yalnızca işletim sistemi tarafından kullanılır.

Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `IsSystem`.

Üye işlevi görmek [MatchesMask](#matchesmask) dosya öznitelikleri tam listesi için.

### <a name="example"></a>Örnek

  Örneğin bakın [CFileFind::GetLength](#getlength).

##  <a name="istemporary"></a>  CFileFind::IsTemporary

Bulunan dosyayı geçici bir dosya olup olmadığını belirlemek için bu üye işlevini çağırın.

```
BOOL IsTemporary() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Geçici bir dosya FILE_ATTRIBUTE_TEMPORARY ile işaretlenmiş, tanımlanan dosya özniteliği [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) yapısı. Geçici bir dosya geçici depolaması için kullanılır. Uygulamalar, yalnızca kesinlikle gerekli olduğunda dosyaya yazmanız gerekir. Dosyanın verilerden en iyi şekilde dosyayı yakında silinecek ortam temizlendi nedeni olmadan bellekte kalır.

Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `IsTemporary`.

Üye işlevi görmek [MatchesMask](#matchesmask) dosya öznitelikleri tam listesi için.

### <a name="example"></a>Örnek

  Örneğin bakın [CFileFind::GetLength](#getlength).

##  <a name="m_ptm"></a>  CFileFind::m_pTM

İşaretçi bir `CAtlTransactionManager` nesne.

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>Açıklamalar

##  <a name="matchesmask"></a>  CFileFind::MatchesMask

Dosya öznitelikleri bulunan dosya çubuğunda test etmek için bu üye işlevini çağırın.

```
virtual BOOL MatchesMask(DWORD dwMask) const;
```

### <a name="parameters"></a>Parametreler

*dwMask*<br/>
Tanımlanan bir veya daha fazla dosya özniteliklerini belirtir [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) yapısı, bulunan dosyanın. Birden çok özniteliklerini aramak için bit düzeyinde OR kullanın (&#124;) işleci. Aşağıdaki özniteliklerden herhangi bir birleşimini kabul edilebilir:

- FILE_ATTRIBUTE_ARCHIVE dosyanın bir arşiv dosyasıdır. Uygulama, yedekleme veya kaldırma için dosyaları işaretlemek için bu öznitelik kullanın.

- Dosya veya dizin FILE_ATTRIBUTE_COMPRESSED sıkıştırılır. Bir dosya için bu sıkıştırılmış dosyasındaki verilerin tümünü anlamına gelir. Bir dizin için bu sıkıştırma yeni oluşturulan dosyalar ve alt dizinler için varsayılan anlamına gelir.

- FILE_ATTRIBUTE_DIRECTORY dosyanın bir dizindir.

- FILE_ATTRIBUTE_NORMAL dosya kümesi özniteliklere sahip değildir. Bu öznitelik, yalnızca tek başına kullanıldığında geçerlidir. Diğer tüm dosya öznitelikleri, bu özniteliği geçersiz kılar.

- Soubor je skrytý FILE_ATTRIBUTE_HIDDEN. Bir sıradan bir dizin listesindeki dahil edilmemesi aittir.

- FILE_ATTRIBUTE_READONLY dosyanın salt okunur. Uygulamaların dosya okuyabilen ancak olamaz yazma veya silin.

- FILE_ATTRIBUTE_SYSTEM dosya parçası veya özel olarak işletim sistemi tarafından kullanılır.

- FILE_ATTRIBUTE_TEMPORARY dosyayı geçici depolama için kullanılır. Uygulamalar, yalnızca kesinlikle gerekli olduğunda dosyaya yazmanız gerekir. Dosyanın verilerden en iyi şekilde dosyayı yakında silinecek ortam temizlendi nedeni olmadan bellekte kalır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0. Genişletilmiş hata bilgilerini almak için Win32 işlevini çağırmak [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360).

### <a name="remarks"></a>Açıklamalar

Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `MatchesMask`.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#35](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_5.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CFtpFileFind Sınıfı](../../mfc/reference/cftpfilefind-class.md)<br/>
[CGopherFileFind Sınıfı](../../mfc/reference/cgopherfilefind-class.md)<br/>
[CInternetFile Sınıfı](../../mfc/reference/cinternetfile-class.md)<br/>
[CGopherFile Sınıfı](../../mfc/reference/cgopherfile-class.md)<br/>
[CHttpFile Sınıfı](../../mfc/reference/chttpfile-class.md)
