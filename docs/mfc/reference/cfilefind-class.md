---
title: CFileFind Sınıfı
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
ms.openlocfilehash: 5bb53a6abf7040bd6ee9f5f2cf56b0feb4d62e66
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81755025"
---
# <a name="cfilefind-class"></a>CFileFind Sınıfı

Yerel dosya aramaları gerçekleştirir ve Internet dosya aramaları gerçekleştirmek [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) ve [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md)için taban sınıftır.

## <a name="syntax"></a>Sözdizimi

```
class CFileFind : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CFileFind::CFileFind](#cfilefind)|Bir `CFileFind` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CFileFind::Kapat](#close)|Arama isteğini kapatır.|
|[CFileFind::FindFile](#findfile)|Belirli bir dosya adı için bir dizini arar.|
|[CFileFind::FindNextFile](#findnextfile)|[FindFile](#findfile)için önceki bir aramadan bir dosya aramasına devam ediyor.|
|[CFileFind::GetCreationTime](#getcreationtime)|Dosyanın oluşturulduğu zamanı alır.|
|[CFileFind::GetFileName](#getfilename)|Bulunan dosyanın uzantısı da dahil olmak üzere adını alır|
|[CFileFind::GetFilePath](#getfilepath)|Bulunan dosyanın tüm yolunu alır.|
|[CFileFind::GetFileTitle](#getfiletitle)|Bulunan dosyanın başlığını alır. Başlık uzantısı içermez.|
|[CFileFind::GetFileURL](#getfileurl)|Bulunan dosya yolunu da içeren URL'yi alır.|
|[CFileFind::GetLastAccessTime](#getlastaccesstime)|Dosyaya en son erişilen zamanı alır.|
|[CFileFind::GetLastWriteTime](#getlastwritetime)|Dosyanın en son değiştirilip kaydedildiği zamanı alır.|
|[CFileFind::GetLength](#getlength)|Bulunan dosyanın uzunluğunu baytlarla alır.|
|[CFileFind::GetRoot](#getroot)|Bulunan dosyanın kök dizinini alır.|
|[CFileFind::Arşivlenmiş](#isarchived)|Bulunan dosyanın arşivlendirilip arşivlendirilemeyişilep arşivlendirileni belirler.|
|[CFileFind::Sıkıştırılmış](#iscompressed)|Bulunan dosyanın sıkıştırılmış olup olmadığını belirler.|
|[CFileFind::İşDirectory](#isdirectory)|Bulunan dosyanın bir dizin olup olmadığını belirler.|
|[CFileFind::IsDots](#isdots)|Bulunan dosyanın adının "." veya "..", aslında bir dizin olduğunu belirten adı olup olmadığını belirler.|
|[CFileFind::Gizli](#ishidden)|Bulunan dosyanın gizli olup olmadığını belirler.|
|[CfileFind::Normal](#isnormal)|Bulunan dosyanın normal olup olmadığını belirler (başka bir deyişle, başka bir özniteliği yoktur).|
|[CfileFind::Sadece IsreadOnly](#isreadonly)|Bulunan dosyanın salt okunur olup olmadığını belirler.|
|[CFileFind::IsSystem](#issystem)|Bulunan dosyanın bir sistem dosyası olup olmadığını belirler.|
|[CFileFind::IsTemporary](#istemporary)|Bulunan dosyanın geçici olup olmadığını belirler.|
|[CFileFind::Kibrit Maskesi](#matchesmask)|Bulunacak dosyanın istenen dosya özniteliklerini gösterir.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CFileFind::CloseContext](#closecontext)|Geçerli arama tanıtıcıtarafından belirtilen dosyayı kapatır.|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CFileFind::m_pTM](#m_ptm)|Bir `CAtlTransactionManager` nesneye işaretçi.|

## <a name="remarks"></a>Açıklamalar

`CFileFind`aramayı başlatan, dosyayı bulup dosyanın başlığını, adını veya yolunu döndüren üye işlevleri içerir. Internet aramaları için üye işlevi [GetFileURL](#getfileurl) dosyanın URL'sini döndürür.

`CFileFind`belirli sunucu türlerini aramak için tasarlanmış diğer iki `CGopherFileFind` MFC sınıfının temel `CFtpFileFind` sınıfıdır: özellikle gopher sunucularıyla çalışır ve özellikle FTP sunucularıyla çalışır. Bu üç sınıf birlikte, istemcinin sunucu protokolü, dosya türü veya konumdan bağımsız olarak yerel bir makinede veya uzak bir sunucuda dosyaları bulması için sorunsuz bir mekanizma sağlar.

Aşağıdaki kod, geçerli dizindeki tüm dosyaları, her dosyanın adını yazdırarak, numarası görür:

[!code-cpp[NVC_MFCFiles#31](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_1.cpp)]

Örneği basit tutmak için bu kod C++ `cout` Standart Kitaplığı sınıfını kullanır. Satır, `cout` örneğin grafik kullanıcı arabirimine sahip bir programa yapılan `CListBox::AddString`bir çağrıyla değiştirilebilir.

Nasıl kullanılacağı `CFileFind` ve diğer WinInet sınıfları hakkında daha fazla bilgi için, [WinInet ile](../../mfc/win32-internet-extensions-wininet.md)makale Internet Programlama bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CFileFind`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="cfilefindcfilefind"></a><a name="cfilefind"></a>CFileFind::CFileFind

Bir `CFileFind` nesne oluşturulduğunda bu üye işlev çağrılır.

```
CFileFind();
CFileFind(CAtlTransactionManager* pTM);
```

### <a name="parameters"></a>Parametreler

*pTM*<br/>
CAtlTransactionManager nesnesine işaretçi

### <a name="example"></a>Örnek

  CFileFind örneğine [bakın:GetFileName](#getfilename).

## <a name="cfilefindclose"></a><a name="close"></a>CFileFind::Kapat

Aramayı sona erdirmek, bağlamı sıfırlamak ve tüm kaynakları serbest bırakmak için bu üye işlevini çağırın.

```cpp
void Close();
```

### <a name="remarks"></a>Açıklamalar

Aradıktan `Close`sonra, yeni bir aramaya `CFileFind` başlamak için [FindFile'ı](#findfile) aramadan önce yeni bir örnek oluşturmanız gerekmez.

### <a name="example"></a>Örnek

  CFileFind örneğine [bakın:GetFileName](#getfilename).

## <a name="cfilefindclosecontext"></a><a name="closecontext"></a>CFileFind::CloseContext

Geçerli arama tanıtıcıtarafından belirtilen dosyayı kapatır.

```
virtual void CloseContext();
```

### <a name="remarks"></a>Açıklamalar

Arama tanıtıcısının geçerli değeriyle belirtilen dosyayı kapatır. Varsayılan davranışı değiştirmek için bu işlevi geçersiz kılın.

Geçerli bir arama tanıtıcısını almak için [FindFile](#findfile) veya [FindNextFile](#findnextfile) işlevlerini en az bir kez aramanız gerekir. Ve `FindFile` `FindNextFile` işlevler, belirli bir ada uyan adlara sahip dosyaları bulmak için arama tutamacını kullanır.

## <a name="cfilefindfindfile"></a><a name="findfile"></a>CFileFind::FindFile

Dosya aramasını açmak için bu üye işlevini arayın.

```
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,
    DWORD dwUnused = 0);
```

### <a name="parameters"></a>Parametreler

*pstrName*<br/>
Bulmak için dosyanın adını içeren bir dize için bir işaretçi. *Eğer pstrName*için NULL `FindFile` geçerseniz, bir\*joker (*. ) arama yapar.

*dwKullanılmamış*<br/>
Türemiş `FindFile` sınıflarla polimorfik yapmak için ayrılmıştır. 0 olmalı.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0. Genişletilmiş hata bilgilerini almak için Win32 işlevini [getLastError'ı](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)arayın.

### <a name="remarks"></a>Açıklamalar

Dosya `FindFile` aramaya başlamak için aradıktan sonra, sonraki dosyaları almak için [FindNextFile'ı](#findnextfile) arayın. Aşağıdaki öznitelik üye işlevlerinden herhangi birini aramadan önce en az bir kez aramalısınız: `FindNextFile`

- [GetCreationTime](#getcreationtime)

- [GetFileName](#getfilename)

- [GetFileTitle](#getfiletitle)

- [Getfilepath](#getfilepath)

- [GetFileURL](#getfileurl)

- [Getlastaccesstime](#getlastaccesstime)

- [Getlastwritetime](#getlastwritetime)

- [Getlength](#getlength)

- [GetRoot](#getroot)

- [IsArchived](#isarchived)

- [IsCompressed](#iscompressed)

- [İş Dizini](#isdirectory)

- [IsDots](#isdots)

- [ıshidden](#ishidden)

- [IsNormal](#isnormal)

- [IsReadOnly](#isreadonly)

- [IsSystem](#issystem)

- [Geçici](#istemporary)

- [Kibrit Maskesi](#matchesmask)

### <a name="example"></a>Örnek

  CFileFind örneğine [bakın::IsDirectory](#isdirectory).

## <a name="cfilefindfindnextfile"></a><a name="findnextfile"></a>CFileFind::FindNextFile

Önceki bir aramadan [FindFile'a](#findfile)bir dosya aramasına devam etmek için bu üye işlevini arayın.

```
virtual BOOL FindNextFile();
```

### <a name="return-value"></a>Dönüş Değeri

Daha fazla dosya varsa sıfır olmayan; bulunan dosya dizindeki son dosyaysa veya bir hata oluştuysa sıfır. Genişletilmiş hata bilgilerini almak için Win32 işlevini [getLastError'ı](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)arayın. Bulunan dosya dizindeki son dosyaysa veya eşleşen dosya bulunamazsa, `GetLastError` işlev ERROR_NO_MORE_FILES döndürür.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki öznitelik üye işlevlerinden herhangi birini aramadan önce en az bir kez aramalısınız: `FindNextFile`

- [GetCreationTime](#getcreationtime)

- [GetFileName](#getfilename)

- [GetFileTitle](#getfiletitle)

- [Getfilepath](#getfilepath)

- [GetFileURL](#getfileurl)

- [Getlastaccesstime](#getlastaccesstime)

- [Getlastwritetime](#getlastwritetime)

- [Getlength](#getlength)

- [GetRoot](#getroot)

- [IsArchived](#isarchived)

- [IsCompressed](#iscompressed)

- [İş Dizini](#isdirectory)

- [IsDots](#isdots)

- [ıshidden](#ishidden)

- [IsNormal](#isnormal)

- [IsReadOnly](#isreadonly)

- [IsSystem](#issystem)

- [Geçici](#istemporary)

- [Kibrit Maskesi](#matchesmask)

`FindNextFile`Win32 işlevini [BulurİleriDosya'yu](/windows/win32/api/fileapi/nf-fileapi-findnextfilew)sarar.

### <a name="example"></a>Örnek

  CFileFind örneğine [bakın::IsDirectory](#isdirectory).

## <a name="cfilefindgetcreationtime"></a><a name="getcreationtime"></a>CFileFind::GetCreationTime

Belirtilen dosyanın oluşturulduğu zamanı almak için bu üye işlevini arayın.

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

Sıfırsız eğer başarılı; Başarısız olursa 0. `GetCreationTime`yalnızca [FindNextFile](#findnextfile) bu `CFileFind` nesneüzerinde hiç çağrılmadıysa 0 döndürür.

### <a name="remarks"></a>Açıklamalar

Aramadan önce [FindNextFile'ı](#findnextfile) `GetCreationTime`en az bir kez aramalısınız.

> [!NOTE]
> Tüm dosya sistemleri, bu işlev tarafından döndürülen zaman damgasını uygulamak için aynı semantikleri kullanmaz. Bu işlev, temel dosya sistemi veya sunucu zaman özniteliğini tutmayı desteklemiyorsa, diğer zaman damgası işlevleri tarafından döndürülen aynı değeri döndürebilir. Zaman biçimleri hakkında bilgi için [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) yapıya bakın. Bazı işlem sistemlerinde, döndürülen saat dilimi içinde olan dosyanın bulunduğu makineye yereldir. Daha fazla bilgi için Win32 [FileTimeToLocalFileTime](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime) API'sine bakın.

### <a name="example"></a>Örnek

  CFileFind örneğine [bakın:GetLength](#getlength).

## <a name="cfilefindgetfilename"></a><a name="getfilename"></a>CFileFind::GetFileName

Bulunan dosyanın adını almak için bu üye işlevini arayın.

```
virtual CString GetFileName() const;
```

### <a name="return-value"></a>Dönüş Değeri

En son bulunan dosyanın adı.

### <a name="remarks"></a>Açıklamalar

GetFileName'yi aramadan önce [FindNextFile'ı](#findnextfile) en az bir kez aramalısınız.

`GetFileName`dosya adının `CFileFind` bir biçimini döndüren üç üye işlevden biridir. Aşağıdaki listede üç ve nasıl değişir açıklar:

- `GetFileName`uzantı da dahil olmak üzere dosya adını döndürür. Örneğin, dosya `GetFileName` hakkında kullanıcı iletisi oluşturmak için arama *c:\myhtml\myfile.txt* dosya adı *myfile.txt*döndürür.

- [GetFilePath](#getfilepath) dosya için tüm yolu döndürür. Örneğin, dosya `GetFilePath` hakkında kullanıcı iletisi oluşturmak için arama *c:\myhtml\myfile.txt* dosya yolu *c:\myhtml\myfile.txt*döndürür.

- [GetFileTitle](#getfiletitle) dosya uzantısı hariç dosya adını döndürür. Örneğin, dosya `GetFileTitle` hakkında bir kullanıcı iletisi oluşturmak için arama *c:\myhtml\myfile.txt* dosya başlığı *myfile*döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#32](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_2.cpp)]

## <a name="cfilefindgetfilepath"></a><a name="getfilepath"></a>CFileFind::GetFilePath

Belirtilen dosyanın tam yolunu almak için bu üye işlevi arayın.

```
virtual CString GetFilePath() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belirtilen dosyanın yolu.

### <a name="remarks"></a>Açıklamalar

Aramadan önce [FindNextFile'ı](#findnextfile) `GetFilePath`en az bir kez aramalısınız.

`GetFilePath`dosya adının `CFileFind` bir biçimini döndüren üç üye işlevden biridir. Aşağıdaki listede üç ve nasıl değişir açıklar:

- [GetFileName](#getfilename) uzantı da dahil olmak üzere dosya adını döndürür. Örneğin, dosya `GetFileName` hakkında kullanıcı iletisi oluşturmak için arama *c:\myhtml\myfile.txt* dosya adı *myfile.txt*döndürür.

- `GetFilePath`dosya için tüm yolu döndürür. Örneğin, dosya `GetFilePath` `c:\myhtml\myfile.txt` hakkında bir kullanıcı iletisi oluşturmak `c:\myhtml\myfile.txt`için arama dosya yolunu döndürür.

- [GetFileTitle](#getfiletitle) dosya uzantısı hariç dosya adını döndürür. Örneğin, dosya `GetFileTitle` hakkında bir kullanıcı iletisi oluşturmak için arama *c:\myhtml\myfile.txt* dosya başlığı *myfile*döndürür.

### <a name="example"></a>Örnek

  CFileFind örneğine [bakın:GetFileName](#getfilename).

## <a name="cfilefindgetfiletitle"></a><a name="getfiletitle"></a>CFileFind::GetFileTitle

Bulunan dosyanın başlığını almak için bu üye işlevini arayın.

```
virtual CString GetFileTitle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dosyanın başlığı.

### <a name="remarks"></a>Açıklamalar

Aramadan önce [FindNextFile'ı](#findnextfile) `GetFileTitle`en az bir kez aramalısınız.

`GetFileTitle`dosya adının `CFileFind` bir biçimini döndüren üç üye işlevden biridir. Aşağıdaki listede üç ve nasıl değişir açıklar:

- [GetFileName](#getfilename) uzantı da dahil olmak üzere dosya adını döndürür. Örneğin, dosya `GetFileName` hakkında kullanıcı iletisi oluşturmak için arama *c:\myhtml\myfile.txt* dosya adı *myfile.txt*döndürür.

- [GetFilePath](#getfilepath) dosya için tüm yolu döndürür. Örneğin, dosya `GetFilePath` hakkında kullanıcı iletisi oluşturmak için arama *c:\myhtml\myfile.txt* dosya yolu *c:\myhtml\myfile.txt*döndürür.

- `GetFileTitle`dosya uzantısı hariç dosya adını döndürür. Örneğin, dosya `GetFileTitle` hakkında bir kullanıcı iletisi oluşturmak için arama *c:\myhtml\myfile.txt* dosya başlığı *myfile*döndürür.

### <a name="example"></a>Örnek

  CFileFind örneğine [bakın:GetFileName](#getfilename).

## <a name="cfilefindgetfileurl"></a><a name="getfileurl"></a>CFileFind::GetFileURL

Belirtilen URL'yi almak için bu üye işlevini arayın.

```
virtual CString GetFileURL() const;
```

### <a name="return-value"></a>Dönüş Değeri

Tam URL.

### <a name="remarks"></a>Açıklamalar

Aramadan önce [FindNextFile'ı](#findnextfile) `GetFileURL`en az bir kez aramalısınız.

`GetFileURL`üye işlevi [GetFilePath](#getfilepath)benzer , formda `file://path`URL döndürür dışında . Örneğin, *myfile.txt* için tam URL almak için `file://c:\myhtml\myfile.txt`arama `GetFileURL` URL döndürür.

### <a name="example"></a>Örnek

  CFileFind örneğine [bakın:GetFileName](#getfilename).

## <a name="cfilefindgetlastaccesstime"></a><a name="getlastaccesstime"></a>CFileFind::GetLastAccessTime

Belirtilen dosyaya en son erişilen zamanı almak için bu üye işlevini arayın.

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

Sıfırsız eğer başarılı; Başarısız olursa 0. `GetLastAccessTime`yalnızca [FindNextFile](#findnextfile) bu `CFileFind` nesneüzerinde hiç çağrılmadıysa 0 döndürür.

### <a name="remarks"></a>Açıklamalar

Aramadan önce [FindNextFile'ı](#findnextfile) `GetLastAccessTime`en az bir kez aramalısınız.

> [!NOTE]
> Tüm dosya sistemleri, bu işlev tarafından döndürülen zaman damgasını uygulamak için aynı semantikleri kullanmaz. Bu işlev, temel dosya sistemi veya sunucu zaman özniteliğini tutmayı desteklemiyorsa, diğer zaman damgası işlevleri tarafından döndürülen aynı değeri döndürebilir. Zaman biçimleri hakkında bilgi için [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) yapıya bakın. Bazı işlem sistemlerinde, döndürülen saat dilimi içinde olan dosyanın bulunduğu makineye yereldir. Daha fazla bilgi için Win32 [FileTimeToLocalFileTime](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime) API'sine bakın.

### <a name="example"></a>Örnek

  CFileFind örneğine [bakın:GetLength](#getlength).

## <a name="cfilefindgetlastwritetime"></a><a name="getlastwritetime"></a>CFileFind::GetLastWriteTime

Dosyanın en son ne zaman değiştirildiğini almak için bu üye işlevini arayın.

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

Sıfırsız eğer başarılı; Başarısız olursa 0. `GetLastWriteTime`yalnızca [FindNextFile](#findnextfile) bu `CFileFind` nesneüzerinde hiç çağrılmadıysa 0 döndürür.

### <a name="remarks"></a>Açıklamalar

Aramadan önce [FindNextFile'ı](#findnextfile) `GetLastWriteTime`en az bir kez aramalısınız.

> [!NOTE]
> Tüm dosya sistemleri, bu işlev tarafından döndürülen zaman damgasını uygulamak için aynı semantikleri kullanmaz. Bu işlev, temel dosya sistemi veya sunucu zaman özniteliğini tutmayı desteklemiyorsa, diğer zaman damgası işlevleri tarafından döndürülen aynı değeri döndürebilir. Zaman biçimleri hakkında bilgi için [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) yapıya bakın. Bazı işlem sistemlerinde, döndürülen saat dilimi içinde olan dosyanın bulunduğu makineye yereldir. Daha fazla bilgi için Win32 [FileTimeToLocalFileTime](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime) API'sine bakın.

### <a name="example"></a>Örnek

  CFileFind örneğine [bakın:GetLength](#getlength).

## <a name="cfilefindgetlength"></a><a name="getlength"></a>CFileFind::GetLength

Bulunan dosyanın uzunluğunu baytlarla almak için bu üye işlevi arayın.

```
ULONGLONG GetLength() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bulunan dosyanın uzunluğu, baytlar halinde.

### <a name="remarks"></a>Açıklamalar

Aramadan önce [FindNextFile'ı](#findnextfile) `GetLength`en az bir kez aramalısınız.

`GetLength`dosya boyutunun değerini baytolarak almak ve döndürmek için [win32](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) yapısını WIN32_FIND_DATA kullanır.

> [!NOTE]
> MFC 7.0 itibariyle, `GetLength` 64 bit tümseci türlerini destekler. Kitaplığın bu yeni sürümüyle oluşturulmuş daha önce varolan kod, kesilme uyarılarına neden olabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#33](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_3.cpp)]

## <a name="cfilefindgetroot"></a><a name="getroot"></a>CFileFind::GetRoot

Bulunan dosyanın kökünü almak için bu üye işlevi arayın.

```
virtual CString GetRoot() const;
```

### <a name="return-value"></a>Dönüş Değeri

Etkin aramanın kökü.

### <a name="remarks"></a>Açıklamalar

Aramadan önce [FindNextFile'ı](#findnextfile) `GetRoot`en az bir kez aramalısınız.

Bu üye işlev, aramayı başlatmak için kullanılan sürücü belirticisini ve yol adını döndürür. Örneğin, boş bir `*.dat` dize `GetRoot` döndürme yle sonuçlanan [FindFile'ı](#findfile) aramak. Bir yol geçme `c:\windows\system\*.dll`gibi `FindFile` , `GetRoot` dönen `c:\windows\system\`sonuçlara .

### <a name="example"></a>Örnek

  CFileFind örneğine [bakın:GetFileName](#getfilename).

## <a name="cfilefindisarchived"></a><a name="isarchived"></a>CFileFind::Arşivlenmiş

Bulunan dosyanın arşivlendirilip arşivlmeyedilip arşivlmeysenine karar vermek için bu üye işlevini arayın.

```
BOOL IsArchived() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Uygulamalar, [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) yapısında tanımlanan bir dosya özniteliği yle birlikte, FILE_ATTRIBUTE_ARCHIVE yedeklenecek veya kaldırılacak bir arşiv dosyasını işaretler.

Aramadan önce [FindNextFile'ı](#findnextfile) `IsArchived`en az bir kez aramalısınız.

Dosya özniteliklerinin tam listesi için Üye işlev [MatchesMask'e](#matchesmask) bakın.

### <a name="example"></a>Örnek

  CFileFind örneğine [bakın:GetLength](#getlength).

## <a name="cfilefindiscompressed"></a><a name="iscompressed"></a>CFileFind::Sıkıştırılmış

Bulunan dosyanın sıkıştırılmış olup olmadığını belirlemek için bu üye işlevi arayın.

```
BOOL IsCompressed() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Sıkıştırılmış bir dosya, [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) yapısında tanımlanan bir dosya özniteliği olan FILE_ATTRIBUTE_COMPRESSED ile işaretlenir. Bir dosya için bu öznitelik, dosyadaki tüm verilerin sıkıştırılmış olduğunu gösterir. Bir dizin için bu öznitelik, sıkıştırmanın yeni oluşturulan dosyalar ve alt dizinler için varsayılan olduğunu gösterir.

Aramadan önce [FindNextFile'ı](#findnextfile) `IsCompressed`en az bir kez aramalısınız.

Dosya özniteliklerinin tam listesi için Üye işlev [MatchesMask'e](#matchesmask) bakın.

### <a name="example"></a>Örnek

  CFileFind örneğine [bakın:GetLength](#getlength).

## <a name="cfilefindisdirectory"></a><a name="isdirectory"></a>CFileFind::İşDirectory

Bulunan dosyanın bir dizin olup olmadığını belirlemek için bu üye işlevi arayın.

```
BOOL IsDirectory() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Dizin olan bir dosya, [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) yapısında tanımlanan bir dosya özniteliği FILE_ATTRIBUTE_DIRECTORY işaretlenir.

Aramadan önce [FindNextFile'ı](#findnextfile) `IsDirectory`en az bir kez aramalısınız.

Dosya özniteliklerinin tam listesi için Üye işlev [MatchesMask'e](#matchesmask) bakın.

### <a name="example"></a>Örnek

Bu küçük program C:\ her dizin recurses ve dizinin adını yazdırır.

[!code-cpp[NVC_MFCFiles#34](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_4.cpp)]

## <a name="cfilefindisdots"></a><a name="isdots"></a>CFileFind::IsDots

Dosyalar arasında yinelenen geçerli dizin ve üst dizin işaretçileri için test etmek için bu üye işlevi arayın.

```
virtual BOOL IsDots() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bulunan dosyada "." veya ".."adı varsa, bulunan dosyanın aslında bir dizin olduğunu gösterir. Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Aramadan önce [FindNextFile'ı](#findnextfile) `IsDots`en az bir kez aramalısınız.

### <a name="example"></a>Örnek

  CFileFind örneğine [bakın::IsDirectory](#isdirectory).

## <a name="cfilefindishidden"></a><a name="ishidden"></a>CFileFind::Gizli

Bulunan dosyanın gizli olup olmadığını belirlemek için bu üye işlevini arayın.

```
BOOL IsHidden() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

[WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) yapısında tanımlanan bir dosya özniteliği olan FILE_ATTRIBUTE_HIDDEN ile işaretlenmiş gizli dosyalar. Gizli bir dosya sıradan bir dizin listesine dahil edilmez.

Aramadan önce [FindNextFile'ı](#findnextfile) `IsHidden`en az bir kez aramalısınız.

Dosya özniteliklerinin tam listesi için Üye işlev [MatchesMask'e](#matchesmask) bakın.

### <a name="example"></a>Örnek

  CFileFind örneğine [bakın:GetLength](#getlength).

## <a name="cfilefindisnormal"></a><a name="isnormal"></a>CfileFind::Normal

Bulunan dosyanın normal bir dosya olup olmadığını belirlemek için bu üye işlevini arayın.

```
BOOL IsNormal() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

FILE_ATTRIBUTE_NORMAL ile işaretlenmiş dosyalar, [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) yapısında tanımlanan bir dosya özniteliği. Normal bir dosyanın başka öznitelikleri kümesi yoktur. Diğer tüm dosya öznitelikleri bu özniteliği geçersiz kılar.

Aramadan önce [FindNextFile'ı](#findnextfile) `IsNormal`en az bir kez aramalısınız.

Dosya özniteliklerinin tam listesi için Üye işlev [MatchesMask'e](#matchesmask) bakın.

### <a name="example"></a>Örnek

  CFileFind örneğine [bakın:GetLength](#getlength).

## <a name="cfilefindisreadonly"></a><a name="isreadonly"></a>CfileFind::Sadece IsreadOnly

Bulunan dosyanın salt okunup okunmayarak olmadığını belirlemek için bu üye işlevini arayın.

```
BOOL IsReadOnly() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Salt okunur dosya, [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) yapısında tanımlanan bir dosya özniteliği olan FILE_ATTRIBUTE_READONLY ile işaretlenir. Uygulamalar böyle bir dosyayı okuyabilir, ancak dosyaya yazamaz veya silemez.

Aramadan önce [FindNextFile'ı](#findnextfile) `IsReadOnly`en az bir kez aramalısınız.

Dosya özniteliklerinin tam listesi için Üye işlev [MatchesMask'e](#matchesmask) bakın.

### <a name="example"></a>Örnek

  CFileFind örneğine [bakın:GetLength](#getlength).

## <a name="cfilefindissystem"></a><a name="issystem"></a>CFileFind::IsSystem

Bulunan dosyanın bir sistem dosyası olup olmadığını belirlemek için bu üye işlevini arayın.

```
BOOL IsSystem() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Sistem dosyası, [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) yapısında tanımlanan bir dosya özniteliği olan FILE_ATTRIBUTE_SYSTEM ile işaretlenir. Sistem dosyası işletim sisteminin bir parçasıdır veya yalnızca bu sistem tarafından kullanılır.

Aramadan önce [FindNextFile'ı](#findnextfile) `IsSystem`en az bir kez aramalısınız.

Dosya özniteliklerinin tam listesi için Üye işlev [MatchesMask'e](#matchesmask) bakın.

### <a name="example"></a>Örnek

  CFileFind örneğine [bakın:GetLength](#getlength).

## <a name="cfilefindistemporary"></a><a name="istemporary"></a>CFileFind::IsTemporary

Bulunan dosyanın geçici bir dosya olup olmadığını belirlemek için bu üye işlevini arayın.

```
BOOL IsTemporary() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Geçici bir dosya, [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) yapısında tanımlanan bir dosya özniteliği olan FILE_ATTRIBUTE_TEMPORARY ile işaretlenir. Geçici depolama için geçici bir dosya kullanılır. Başvurular sadece kesinlikle gerekli yse dosyaya yazılmalıdır. Dosya yakında silineceği için dosyanın verilerinin çoğu ortama atılmadan bellekte kalır.

Aramadan önce [FindNextFile'ı](#findnextfile) `IsTemporary`en az bir kez aramalısınız.

Dosya özniteliklerinin tam listesi için Üye işlev [MatchesMask'e](#matchesmask) bakın.

### <a name="example"></a>Örnek

  CFileFind örneğine [bakın:GetLength](#getlength).

## <a name="cfilefindm_ptm"></a><a name="m_ptm"></a>CFileFind::m_pTM

Bir `CAtlTransactionManager` nesneye işaretçi.

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>Açıklamalar

## <a name="cfilefindmatchesmask"></a><a name="matchesmask"></a>CFileFind::Kibrit Maskesi

Bulunan dosya daki dosya özniteliklerini sınamak için bu üye işlevi arayın.

```
virtual BOOL MatchesMask(DWORD dwMask) const;
```

### <a name="parameters"></a>Parametreler

*Dwmask*<br/>
Bulunan dosya için [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) yapısında tanımlanan bir veya daha fazla dosya özniteliği belirtir. Birden çok öznitelik aramak için bityönünde VEYA (&#124;) işleci kullanın. Aşağıdaki özniteliklerin herhangi bir kombinasyonu kabul edilebilir:

- FILE_ATTRIBUTE_ARCHIVE Dosya bir arşiv dosyasıdır. Uygulamalar yedekleme veya kaldırma için dosyaları işaretlemek için bu özniteliği kullanır.

- FILE_ATTRIBUTE_COMPRESSED Dosya veya dizin sıkıştırılır. Bir dosya için bu, dosyadaki tüm verilerin sıkıştırılmış olduğu anlamına gelir. Bir dizin için bu, sıkıştırmanın yeni oluşturulan dosyalar ve alt dizinler için varsayılan olduğu anlamına gelir.

- FILE_ATTRIBUTE_DIRECTORY Dosya bir dizin.

- FILE_ATTRIBUTE_NORMAL Dosyanın başka öznitelikleri kümesi yoktur. Bu öznitelik yalnızca tek başına kullanıldığında geçerlidir. Diğer tüm dosya öznitelikleri bu özniteliği geçersiz kılar.

- FILE_ATTRIBUTE_HIDDEN Dosya gizlidir. Sıradan bir dizin listesine dahil edilmeyin.

- FILE_ATTRIBUTE_READONLY Dosya yalnızca okunur. Uygulamalar dosyayı okuyabilir, ancak dosyaya yazamaz veya silemez.

- FILE_ATTRIBUTE_SYSTEM Dosya yalnızca işletim sisteminin bir parçasıdır veya yalnızca bu sistem tarafından kullanılır.

- FILE_ATTRIBUTE_TEMPORARY Dosya geçici depolama için kullanılıyor. Başvurular sadece kesinlikle gerekli yse dosyaya yazılmalıdır. Dosya yakında silineceği için dosyanın verilerinin çoğu ortama atılmadan bellekte kalır.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0. Genişletilmiş hata bilgilerini almak için Win32 işlevini [getLastError'ı](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)arayın.

### <a name="remarks"></a>Açıklamalar

Aramadan önce [FindNextFile'ı](#findnextfile) `MatchesMask`en az bir kez aramalısınız.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#35](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_5.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CFtpFileFind Sınıf](../../mfc/reference/cftpfilefind-class.md)<br/>
[CGopherFileFind Sınıf](../../mfc/reference/cgopherfilefind-class.md)<br/>
[CInternetFile Sınıfı](../../mfc/reference/cinternetfile-class.md)<br/>
[CGopherFile Sınıfı](../../mfc/reference/cgopherfile-class.md)<br/>
[Chttpfile Sınıfı](../../mfc/reference/chttpfile-class.md)
