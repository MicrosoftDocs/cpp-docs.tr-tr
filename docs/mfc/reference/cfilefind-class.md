---
description: 'Daha fazla bilgi edinin: CFileFind sınıfı'
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
ms.openlocfilehash: d47c45ac86386a6748ca212c569aeef568ca2a8a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184510"
---
# <a name="cfilefind-class"></a>CFileFind sınıfı

Yerel dosya aramalarını gerçekleştirir ve Internet dosya aramalarını gerçekleştiren [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) ve [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md)için temel sınıftır.

## <a name="syntax"></a>Syntax

```
class CFileFind : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CFileFind:: CFileFind](#cfilefind)|Bir `CFileFind` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CFileFind:: Close](#close)|Arama isteğini kapatır.|
|[CFileFind:: FindFile](#findfile)|Belirtilen dosya adı için bir dizin arar.|
|[CFileFind:: FindNextFile](#findnextfile)|Önceki bir [FindFile](#findfile)çağrısından bir dosya aramaya devam eder.|
|[CFileFind:: GetCreationTime](#getcreationtime)|Dosyanın oluşturulduğu saati alır.|
|[CFileFind:: GetFileName](#getfilename)|Bulunan dosyanın uzantısı da dahil olmak üzere adı alır|
|[CFileFind:: GetFilePath](#getfilepath)|Bulunan dosyanın tam yolunu alır.|
|[CFileFind:: GetFileTitle](#getfiletitle)|Bulunan dosyanın başlığını alır. Başlık uzantıyı içermez.|
|[CFileFind:: GetFileURL](#getfileurl)|Bulunan dosyanın dosya yolu da dahil olmak üzere URL 'YI alır.|
|[CFileFind:: GetLastAccessTime](#getlastaccesstime)|Dosyanın son erişildiği saati alır.|
|[CFileFind:: GetLastWriteTime](#getlastwritetime)|Dosyanın son değiştirilme ve kaydedilme süresini alır.|
|[CFileFind:: GetLength](#getlength)|Bulunan dosyanın uzunluğunu bayt cinsinden alır.|
|[CFileFind:: GetRoot](#getroot)|Bulunan dosyanın kök dizinini alır.|
|[CFileFind:: ısarşivlendi](#isarchived)|Bulunan dosyanın arşivlenip arşivlenmediğini belirler.|
|[CFileFind:: IsCompressed](#iscompressed)|Bulunan dosyanın sıkıştırılıp sıkıştırılmadığını belirler.|
|[CFileFind:: IsDirectory](#isdirectory)|Bulunan dosyanın bir dizin olup olmadığını belirler.|
|[CFileFind:: ısnoktalar](#isdots)|Bulunan dosyanın adının, gerçekten bir dizin olduğunu gösteren "." veya ".." adına sahip olup olmadığını belirler.|
|[CFileFind:: IsHidden](#ishidden)|Bulunan dosyanın gizlenip gizlenmediğini belirler.|
|[CFileFind:: IsNormal](#isnormal)|Bulunan dosyanın normal olup olmadığını belirler (başka bir deyişle, başka bir deyişle, diğer özniteliklere sahip değildir).|
|[CFileFind:: IsReadOnly](#isreadonly)|Bulunan dosyanın salt okunurdur belirler.|
|[CFileFind:: IsSystem](#issystem)|Bulunan dosyanın bir sistem dosyası olup olmadığını belirler.|
|[CFileFind:: Istesel önemli](#istemporary)|Bulunan dosyanın geçici olup olmadığını belirler.|
|[CFileFind:: MatchesMask](#matchesmask)|Bulunan dosyanın istenen dosya özniteliklerini gösterir.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CFileFind:: CloseContext](#closecontext)|Geçerli arama tanıtıcısı tarafından belirtilen dosyayı kapatır.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CFileFind:: m_pTM](#m_ptm)|Bir nesne işaretçisi `CAtlTransactionManager` .|

## <a name="remarks"></a>Açıklamalar

`CFileFind` bir aramayı başlatır, bir dosya bulur ve dosyanın başlığını, adını veya yolunu döndüren üye işlevlerini içerir. Internet aramalarında, [GetFileURL](#getfileurl) üye işlevi dosyanın URL 'sini döndürür.

`CFileFind` , özel sunucu türlerini aramak için tasarlanan iki diğer MFC sınıfının temel sınıfıdır: `CGopherFileFind` özel olarak Gopher sunucularıyla çalışıyor ve `CFtpFileFind` özellikle FTP sunucularıyla çalışıyor. Bu üç sınıf birlikte, bir yerel makinede veya uzak bir sunucuda Sunucu protokolüne, dosya türüne veya konumdan bağımsız olarak, istemcinin dosyaları bulması için sorunsuz bir mekanizma sağlar.

Aşağıdaki kod, her bir dosyanın adını yazdırarak geçerli dizindeki tüm dosyaları numaralandıracaktır:

[!code-cpp[NVC_MFCFiles#31](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_1.cpp)]

Örneği basit tutmak için, bu kod C++ standart kitaplık `cout` sınıfını kullanır. `cout`Satır, `CListBox::AddString` Örneğin grafik kullanıcı arabirimine sahip bir programda bir çağrısıyla değiştirilebilir.

Ve diğer WinINet sınıflarının kullanımı hakkında daha fazla bilgi için `CFileFind` bkz. [Wininet Ile Internet programlama](../../mfc/win32-internet-extensions-wininet.md)makalesi.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CFileFind`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="cfilefindcfilefind"></a><a name="cfilefind"></a> CFileFind:: CFileFind

Bu üye işlevi, bir nesne oluşturulduğunda çağrılır `CFileFind` .

```
CFileFind();
CFileFind(CAtlTransactionManager* pTM);
```

### <a name="parameters"></a>Parametreler

*pTM*<br/>
CAtlTransactionManager nesnesine yönelik işaretçi

### <a name="example"></a>Örnek

  [CFileFind:: GetFileName](#getfilename)örneğine bakın.

## <a name="cfilefindclose"></a><a name="close"></a> CFileFind:: Close

Aramayı sonlandırmak, bağlamı sıfırlamak ve tüm kaynakları serbest bırakmak için bu üye işlevini çağırın.

```cpp
void Close();
```

### <a name="remarks"></a>Açıklamalar

Çağrıldıktan sonra `Close` `CFileFind` Yeni bir aramaya başlamak Için [FindFile](#findfile) çağrılmadan önce yeni bir örnek oluşturmanız gerekmez.

### <a name="example"></a>Örnek

  [CFileFind:: GetFileName](#getfilename)örneğine bakın.

## <a name="cfilefindclosecontext"></a><a name="closecontext"></a> CFileFind:: CloseContext

Geçerli arama tanıtıcısı tarafından belirtilen dosyayı kapatır.

```
virtual void CloseContext();
```

### <a name="remarks"></a>Açıklamalar

Arama tanıtıcısının geçerli değeri tarafından belirtilen dosyayı kapatır. Varsayılan davranışı değiştirmek için bu işlevi geçersiz kılın.

Geçerli bir arama tanıtıcısını almak için [FindFile](#findfile) veya [FindNextFile](#findnextfile) işlevlerini en az bir kez çağırmanız gerekir. `FindFile`Ve `FindNextFile` işlevleri, belirli bir adla eşleşen adlara sahip dosyaları bulmak için arama tanıtıcısını kullanır.

## <a name="cfilefindfindfile"></a><a name="findfile"></a> CFileFind:: FindFile

Bir dosya aramasını açmak için bu üye işlevini çağırın.

```
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,
    DWORD dwUnused = 0);
```

### <a name="parameters"></a>Parametreler

*pstrName*<br/>
Bulunacak dosyanın adını içeren bir dize işaretçisi. *PstrName* için null geçirirseniz, `FindFile` bir joker karakter (*. \* ) arama yapar.

*Dwkullanılmamış*<br/>
`FindFile`Türetilmiş sınıflarla polimorfik hale getirmek için ayrılmıştır. 0 olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0. Genişletilmiş hata bilgilerini almak için, WIN32 [işlevini çağırın](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror).

### <a name="remarks"></a>Açıklamalar

`FindFile`Dosya aramasına başlamak için çağrıldıktan sonra, sonraki dosyaları almak Için [FindNextFile](#findnextfile) öğesini çağırın. `FindNextFile`Aşağıdaki öznitelik üye işlevlerinden birini çağırmadan önce en az bir kez çağırmanız gerekir:

- [GetCreationTime](#getcreationtime)

- [GetFileName](#getfilename)

- [GetFileTitle](#getfiletitle)

- [GetFilePath](#getfilepath)

- [GetFileURL](#getfileurl)

- [GetLastAccessTime](#getlastaccesstime)

- [GetLastWriteTime](#getlastwritetime)

- [GetLength](#getlength)

- [GetRoot](#getroot)

- [Iarşivlenen](#isarchived)

- [IsCompressed](#iscompressed)

- [IsDirectory](#isdirectory)

- [Ismik](#isdots)

- [IsHidden](#ishidden)

- [IsNormal](#isnormal)

- [IsReadOnly](#isreadonly)

- [IsSystem 'i](#issystem)

- [Istesel önemli](#istemporary)

- [MatchesMask](#matchesmask)

### <a name="example"></a>Örnek

  [CFileFind:: IsDirectory](#isdirectory)örneğine bakın.

## <a name="cfilefindfindnextfile"></a><a name="findnextfile"></a> CFileFind:: FindNextFile

Bu üye işlevini, önceki bir [FindFile](#findfile)çağrısından bir dosya aramasına devam etmek için çağırın.

```
virtual BOOL FindNextFile();
```

### <a name="return-value"></a>Dönüş Değeri

Daha fazla dosya varsa sıfır dışı; Dosya, dizinde sonuncu ise veya bir hata oluştuysa sıfır olur. Genişletilmiş hata bilgilerini almak için, WIN32 [işlevini çağırın](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror). Bulunan dosya dizindeki son dosya ise veya eşleşen dosya bulunamazsa, `GetLastError` işlev ERROR_NO_MORE_FILES döndürür.

### <a name="remarks"></a>Açıklamalar

`FindNextFile`Aşağıdaki öznitelik üye işlevlerinden birini çağırmadan önce en az bir kez çağırmanız gerekir:

- [GetCreationTime](#getcreationtime)

- [GetFileName](#getfilename)

- [GetFileTitle](#getfiletitle)

- [GetFilePath](#getfilepath)

- [GetFileURL](#getfileurl)

- [GetLastAccessTime](#getlastaccesstime)

- [GetLastWriteTime](#getlastwritetime)

- [GetLength](#getlength)

- [GetRoot](#getroot)

- [Iarşivlenen](#isarchived)

- [IsCompressed](#iscompressed)

- [IsDirectory](#isdirectory)

- [Ismik](#isdots)

- [IsHidden](#ishidden)

- [IsNormal](#isnormal)

- [IsReadOnly](#isreadonly)

- [IsSystem 'i](#issystem)

- [Istesel önemli](#istemporary)

- [MatchesMask](#matchesmask)

`FindNextFile` Win32 işlevi [FindNextFile dosyasını](/windows/win32/api/fileapi/nf-fileapi-findnextfilew)kaydırır.

### <a name="example"></a>Örnek

  [CFileFind:: IsDirectory](#isdirectory)örneğine bakın.

## <a name="cfilefindgetcreationtime"></a><a name="getcreationtime"></a> CFileFind:: GetCreationTime

Belirtilen dosyanın oluşturulduğu saati almak için bu üye işlevi çağırın.

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

Başarılı olursa sıfır dışı; başarısız ise 0. `GetCreationTime` Bu nesnede [FindNextFile](#findnextfile) hiç çağrılmadıysa 0 değerini döndürür `CFileFind` .

### <a name="remarks"></a>Açıklamalar

Çağrılmadan önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir `GetCreationTime` .

> [!NOTE]
> Tüm dosya sistemleri bu işlev tarafından döndürülen zaman damgasını uygulamak için aynı semantiğini kullanmaz. Bu işlev, temeldeki dosya sistemi veya sunucusu zaman özniteliğini tutmayı desteklemiyorsa, diğer zaman damgası işlevleri tarafından döndürülen değeri döndürebilir. Zaman biçimleri hakkında bilgi için [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) yapısına bakın. Bazı işletim sistemlerinde döndürülen süre, makinenin yerel olarak bulunduğu saat dilimindedir. Daha fazla bilgi için bkz. Win32 [FileTimeToLocalFileTime](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime) API.

### <a name="example"></a>Örnek

  [CFileFind:: GetLength](#getlength)örneğine bakın.

## <a name="cfilefindgetfilename"></a><a name="getfilename"></a> CFileFind:: GetFileName

Bulunan dosyanın adını almak için bu üye işlevini çağırın.

```
virtual CString GetFileName() const;
```

### <a name="return-value"></a>Dönüş Değeri

En son bulunan dosyanın adı.

### <a name="remarks"></a>Açıklamalar

GetFileName çağrısından önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir.

`GetFileName` , `CFileFind` Dosya adının bir biçimini döndüren üç üye işlevden biridir. Aşağıdaki listede, üç ve nasıl değişen açıklanmıştır:

- `GetFileName` Uzantı dahil olmak üzere dosya adını döndürür. Örneğin, `GetFileName` *c:\myhtml\myfile.txt* dosya hakkında bir kullanıcı iletisi oluşturmak için çağırmak *myfile.txt* dosya adını döndürür.

- [GetFilePath](#getfilepath) dosyanın tüm yolunu döndürür. Örneğin, `GetFilePath` *c:\myhtml\myfile.txt* dosya hakkında bir kullanıcı iletisi oluşturmak için çağırmak *c:\myhtml\myfile.txt* dosya yolunu döndürür.

- [GetFileTitle](#getfiletitle) , dosya uzantısını dışarıda bırakarak dosya adını döndürür. Örneğin, `GetFileTitle` dosya hakkında bir kullanıcı iletisi oluşturmak için çağırmak *c:\myhtml\myfile.txt* dosya başlığı *Dosyam*' ı döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#32](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_2.cpp)]

## <a name="cfilefindgetfilepath"></a><a name="getfilepath"></a> CFileFind:: GetFilePath

Belirtilen dosyanın tam yolunu almak için bu üye işlevi çağırın.

```
virtual CString GetFilePath() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belirtilen dosyanın yolu.

### <a name="remarks"></a>Açıklamalar

Çağrılmadan önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir `GetFilePath` .

`GetFilePath` , `CFileFind` Dosya adının bir biçimini döndüren üç üye işlevden biridir. Aşağıdaki listede, üç ve nasıl değişen açıklanmıştır:

- [GetFileName](#getfilename) , uzantısı da dahil olmak üzere dosya adını döndürür. Örneğin, `GetFileName` *c:\myhtml\myfile.txt* dosya hakkında bir kullanıcı iletisi oluşturmak için çağırmak *myfile.txt* dosya adını döndürür.

- `GetFilePath` dosyanın tüm yolunu döndürür. Örneğin, `GetFilePath` dosya hakkında bir kullanıcı iletisi oluşturmak için çağırmak `c:\myhtml\myfile.txt` dosya yolunu döndürür `c:\myhtml\myfile.txt` .

- [GetFileTitle](#getfiletitle) , dosya uzantısını dışarıda bırakarak dosya adını döndürür. Örneğin, `GetFileTitle` dosya hakkında bir kullanıcı iletisi oluşturmak için çağırmak *c:\myhtml\myfile.txt* dosya başlığı *Dosyam*' ı döndürür.

### <a name="example"></a>Örnek

  [CFileFind:: GetFileName](#getfilename)örneğine bakın.

## <a name="cfilefindgetfiletitle"></a><a name="getfiletitle"></a> CFileFind:: GetFileTitle

Bulunan dosyanın başlığını almak için bu üye işlevini çağırın.

```
virtual CString GetFileTitle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dosyanın başlığı.

### <a name="remarks"></a>Açıklamalar

Çağrılmadan önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir `GetFileTitle` .

`GetFileTitle` , `CFileFind` Dosya adının bir biçimini döndüren üç üye işlevden biridir. Aşağıdaki listede, üç ve nasıl değişen açıklanmıştır:

- [GetFileName](#getfilename) , uzantısı da dahil olmak üzere dosya adını döndürür. Örneğin, `GetFileName` *c:\myhtml\myfile.txt* dosya hakkında bir kullanıcı iletisi oluşturmak için çağırmak *myfile.txt* dosya adını döndürür.

- [GetFilePath](#getfilepath) dosyanın tüm yolunu döndürür. Örneğin, `GetFilePath` *c:\myhtml\myfile.txt* dosya hakkında bir kullanıcı iletisi oluşturmak için çağırmak *c:\myhtml\myfile.txt* dosya yolunu döndürür.

- `GetFileTitle` Dosya Uzantısı hariç dosya adını döndürür. Örneğin, `GetFileTitle` dosya hakkında bir kullanıcı iletisi oluşturmak için çağırmak *c:\myhtml\myfile.txt* dosya başlığı *Dosyam*' ı döndürür.

### <a name="example"></a>Örnek

  [CFileFind:: GetFileName](#getfilename)örneğine bakın.

## <a name="cfilefindgetfileurl"></a><a name="getfileurl"></a> CFileFind:: GetFileURL

Belirtilen URL 'YI almak için bu üye işlevini çağırın.

```
virtual CString GetFileURL() const;
```

### <a name="return-value"></a>Dönüş Değeri

URL 'nin tamamı.

### <a name="remarks"></a>Açıklamalar

Çağrılmadan önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir `GetFileURL` .

`GetFileURL` , formdaki URL 'YI döndürmesi dışında, [GetFilePath](#getfilepath)üye işlevine benzerdir `file://path` . Örneğin,myfile.txtURL 'sini `GetFileURL` almak için çağırmak, URL  'yi döndürür `file://c:\myhtml\myfile.txt` .

### <a name="example"></a>Örnek

  [CFileFind:: GetFileName](#getfilename)örneğine bakın.

## <a name="cfilefindgetlastaccesstime"></a><a name="getlastaccesstime"></a> CFileFind:: GetLastAccessTime

Belirtilen dosyanın son erişildiği saati almak için bu üye işlevini çağırın.

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

Başarılı olursa sıfır dışı; başarısız ise 0. `GetLastAccessTime` Bu nesnede [FindNextFile](#findnextfile) hiç çağrılmadıysa 0 değerini döndürür `CFileFind` .

### <a name="remarks"></a>Açıklamalar

Çağrılmadan önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir `GetLastAccessTime` .

> [!NOTE]
> Tüm dosya sistemleri bu işlev tarafından döndürülen zaman damgasını uygulamak için aynı semantiğini kullanmaz. Bu işlev, temeldeki dosya sistemi veya sunucusu zaman özniteliğini tutmayı desteklemiyorsa, diğer zaman damgası işlevleri tarafından döndürülen değeri döndürebilir. Zaman biçimleri hakkında bilgi için [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) yapısına bakın. Bazı işletim sistemlerinde döndürülen süre, makinenin yerel olarak bulunduğu saat dilimindedir. Daha fazla bilgi için bkz. Win32 [FileTimeToLocalFileTime](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime) API.

### <a name="example"></a>Örnek

  [CFileFind:: GetLength](#getlength)örneğine bakın.

## <a name="cfilefindgetlastwritetime"></a><a name="getlastwritetime"></a> CFileFind:: GetLastWriteTime

Dosyanın son değiştirildiği zamanı almak için bu üye işlevi çağırın.

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

Başarılı olursa sıfır dışı; başarısız ise 0. `GetLastWriteTime` Bu nesnede [FindNextFile](#findnextfile) hiç çağrılmadıysa 0 değerini döndürür `CFileFind` .

### <a name="remarks"></a>Açıklamalar

Çağrılmadan önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir `GetLastWriteTime` .

> [!NOTE]
> Tüm dosya sistemleri bu işlev tarafından döndürülen zaman damgasını uygulamak için aynı semantiğini kullanmaz. Bu işlev, temeldeki dosya sistemi veya sunucusu zaman özniteliğini tutmayı desteklemiyorsa, diğer zaman damgası işlevleri tarafından döndürülen değeri döndürebilir. Zaman biçimleri hakkında bilgi için [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) yapısına bakın. Bazı işletim sistemlerinde döndürülen süre, makinenin yerel olarak bulunduğu saat dilimindedir. Daha fazla bilgi için bkz. Win32 [FileTimeToLocalFileTime](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime) API.

### <a name="example"></a>Örnek

  [CFileFind:: GetLength](#getlength)örneğine bakın.

## <a name="cfilefindgetlength"></a><a name="getlength"></a> CFileFind:: GetLength

Bulunan dosyanın uzunluğunu bayt olarak almak için bu üye işlevini çağırın.

```
ULONGLONG GetLength() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bulunan dosyanın bayt cinsinden uzunluğu.

### <a name="remarks"></a>Açıklamalar

Çağrılmadan önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir `GetLength` .

`GetLength` dosya boyutunun değerini almak ve bayt cinsinden döndürmek için [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) Win32 yapısını kullanır.

> [!NOTE]
> MFC 7,0 itibariyle `GetLength` 64 bit tamsayı türlerini destekler. Kitaplığın bu yeni sürümüyle oluşturulmuş daha önceden varolan kod, kesme uyarılarına neden olabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#33](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_3.cpp)]

## <a name="cfilefindgetroot"></a><a name="getroot"></a> CFileFind:: GetRoot

Bulunan dosyanın kökünü almak için bu üye işlevini çağırın.

```
virtual CString GetRoot() const;
```

### <a name="return-value"></a>Dönüş Değeri

Etkin aramanın kökü.

### <a name="remarks"></a>Açıklamalar

Çağrılmadan önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir `GetRoot` .

Bu üye işlevi, bir aramayı başlatmak için kullanılan sürücü tanımlayıcısını ve yol adını döndürür. Örneğin, [FindFile](#findfile) öğesini `*.dat` `GetRoot` boş bir dize döndüren sonuçlarla çağırma. Bir yolu, örneğin `c:\windows\system\*.dll` , `FindFile` döndüren sonuçlara geçirme `GetRoot` `c:\windows\system\` .

### <a name="example"></a>Örnek

  [CFileFind:: GetFileName](#getfilename)örneğine bakın.

## <a name="cfilefindisarchived"></a><a name="isarchived"></a> CFileFind:: ısarşivlendi

Bulunan dosyanın arşivlenip arşivlenmediğini öğrenmek için bu üye işlevi çağırın.

```
BOOL IsArchived() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Uygulamalar, [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) yapısında tanımlanmış bir dosya özniteliği FILE_ATTRIBUTE_ARCHIVE, yedeklenecek veya kaldırılacak olan bir arşiv dosyasını işaretler.

Çağrılmadan önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir `IsArchived` .

Dosya özniteliklerinin tüm listesi için bkz. [MatchesMask](#matchesmask) üye işlevi.

### <a name="example"></a>Örnek

  [CFileFind:: GetLength](#getlength)örneğine bakın.

## <a name="cfilefindiscompressed"></a><a name="iscompressed"></a> CFileFind:: IsCompressed

Bulunan dosyanın sıkıştırılıp sıkıştırılmadığını öğrenmek için bu üye işlevi çağırın.

```
BOOL IsCompressed() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Sıkıştırılmış bir dosya, [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) yapısında tanımlanan bir dosya özniteliği FILE_ATTRIBUTE_COMPRESSED ile işaretlenir. Bir dosya için bu öznitelik, dosyadaki tüm verilerin sıkıştırıldığını gösterir. Bir dizin için bu öznitelik, yeni oluşturulan dosyalar ve alt dizinler için sıkıştırmanın varsayılan olduğunu gösterir.

Çağrılmadan önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir `IsCompressed` .

Dosya özniteliklerinin tüm listesi için bkz. [MatchesMask](#matchesmask) üye işlevi.

### <a name="example"></a>Örnek

  [CFileFind:: GetLength](#getlength)örneğine bakın.

## <a name="cfilefindisdirectory"></a><a name="isdirectory"></a> CFileFind:: IsDirectory

Bulunan dosyanın bir dizin olup olmadığını öğrenmek için bu üye işlevi çağırın.

```
BOOL IsDirectory() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir dizin olan dosya, [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) yapısında tanımlanan bir dosya özniteliğiyle FILE_ATTRIBUTE_DIRECTORY işaretlenir.

Çağrılmadan önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir `IsDirectory` .

Dosya özniteliklerinin tüm listesi için bkz. [MatchesMask](#matchesmask) üye işlevi.

### <a name="example"></a>Örnek

Bu küçük program, C:\ üzerindeki her dizini tekrarlayan dizinin adını sürücü olarak yazdırın ve yazdırır.

[!code-cpp[NVC_MFCFiles#34](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_4.cpp)]

## <a name="cfilefindisdots"></a><a name="isdots"></a> CFileFind:: ısnoktalar

Dosyalar arasında yineleme yaparken geçerli dizin ve üst dizin işaretçilerini sınamak için bu üye işlevi çağırın.

```
virtual BOOL IsDots() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bulunan dosyanın adı "." veya ".." ise, bulunan dosyanın gerçekten bir dizin olduğunu gösterir. Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Çağrılmadan önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir `IsDots` .

### <a name="example"></a>Örnek

  [CFileFind:: IsDirectory](#isdirectory)örneğine bakın.

## <a name="cfilefindishidden"></a><a name="ishidden"></a> CFileFind:: IsHidden

Bulunan dosyanın gizlenip gizlenmediğini öğrenmek için bu üye işlevini çağırın.

```
BOOL IsHidden() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

[WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) yapısında tanımlanmış bir dosya özniteliği FILE_ATTRIBUTE_HIDDEN ile işaretlenen gizli dosyalar. Gizli bir dosya sıradan bir dizin listesine dahil edilmez.

Çağrılmadan önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir `IsHidden` .

Dosya özniteliklerinin tüm listesi için bkz. [MatchesMask](#matchesmask) üye işlevi.

### <a name="example"></a>Örnek

  [CFileFind:: GetLength](#getlength)örneğine bakın.

## <a name="cfilefindisnormal"></a><a name="isnormal"></a> CFileFind:: IsNormal

Bulunan dosyanın normal bir dosya olup olmadığını öğrenmek için bu üye işlevini çağırın.

```
BOOL IsNormal() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

[WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) yapısında tanımlanmış bir dosya özniteliği FILE_ATTRIBUTE_NORMAL ile işaretlenmiş dosyalar. Normal bir dosyanın ayarlanmış başka bir özniteliği yok. Diğer tüm dosya öznitelikleri bu özniteliği geçersiz kılar.

Çağrılmadan önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir `IsNormal` .

Dosya özniteliklerinin tüm listesi için bkz. [MatchesMask](#matchesmask) üye işlevi.

### <a name="example"></a>Örnek

  [CFileFind:: GetLength](#getlength)örneğine bakın.

## <a name="cfilefindisreadonly"></a><a name="isreadonly"></a> CFileFind:: IsReadOnly

Bulunan dosyanın salt okunurdur olup olmadığını öğrenmek için bu üye işlevini çağırın.

```
BOOL IsReadOnly() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Salt okuma dosyası, [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) yapısında tanımlanan bir dosya özniteliği FILE_ATTRIBUTE_READONLY ile işaretlenir. Uygulamalar böyle bir dosyayı okuyabilir, ancak bunlara yazamaz veya silemez.

Çağrılmadan önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir `IsReadOnly` .

Dosya özniteliklerinin tüm listesi için bkz. [MatchesMask](#matchesmask) üye işlevi.

### <a name="example"></a>Örnek

  [CFileFind:: GetLength](#getlength)örneğine bakın.

## <a name="cfilefindissystem"></a><a name="issystem"></a> CFileFind:: IsSystem

Bulunan dosyanın bir sistem dosyası olup olmadığını öğrenmek için bu üye işlevi çağırın.

```
BOOL IsSystem() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir sistem dosyası FILE_ATTRIBUTE_SYSTEM, [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) yapısında tanımlanmış bir dosya özniteliği ile işaretlenir. Bir sistem dosyası, işletim sistemi tarafından bir parçasıdır veya yalnızca tarafından kullanılır.

Çağrılmadan önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir `IsSystem` .

Dosya özniteliklerinin tüm listesi için bkz. [MatchesMask](#matchesmask) üye işlevi.

### <a name="example"></a>Örnek

  [CFileFind:: GetLength](#getlength)örneğine bakın.

## <a name="cfilefindistemporary"></a><a name="istemporary"></a> CFileFind:: Istesel önemli

Bulunan dosyanın geçici bir dosya olup olmadığını anlamak için bu üye işlevi çağırın.

```
BOOL IsTemporary() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Geçici bir dosya, [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) yapısında tanımlanan bir dosya özniteliği FILE_ATTRIBUTE_TEMPORARY ile işaretlenir. Geçici depolama için geçici bir dosya kullanılır. Uygulamalar yalnızca kesinlikle gerekli olduğunda dosyaya yazmalıdır. Dosya yakında silineceğinden, dosyanın verilerinin çoğu medyaya boşaltılmadan bellekte kalır.

Çağrılmadan önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir `IsTemporary` .

Dosya özniteliklerinin tüm listesi için bkz. [MatchesMask](#matchesmask) üye işlevi.

### <a name="example"></a>Örnek

  [CFileFind:: GetLength](#getlength)örneğine bakın.

## <a name="cfilefindm_ptm"></a><a name="m_ptm"></a> CFileFind:: m_pTM

Bir nesne işaretçisi `CAtlTransactionManager` .

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>Açıklamalar

## <a name="cfilefindmatchesmask"></a><a name="matchesmask"></a> CFileFind:: MatchesMask

Dosya özniteliklerini bulunan dosyada sınamak için bu üye işlevini çağırın.

```
virtual BOOL MatchesMask(DWORD dwMask) const;
```

### <a name="parameters"></a>Parametreler

*dwMask*<br/>
Bulunan dosya için [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) yapısında tanımlanan bir veya daha fazla dosya özniteliği belirtir. Birden çok özniteliği aramak için bit düzeyinde OR (&#124;) işlecini kullanın. Aşağıdaki özniteliklerin herhangi bir birleşimi kabul edilebilir:

- FILE_ATTRIBUTE_ARCHIVE dosya bir arşiv dosyasıdır. Uygulamalar, dosyaları yedekleme veya kaldırma için işaretlemek üzere bu özniteliği kullanır.

- FILE_ATTRIBUTE_COMPRESSED dosya veya dizin sıkıştırılmış. Bir dosya için bu, dosyadaki tüm verilerin sıkıştırıldığı anlamına gelir. Bir dizin için bu, sıkıştırmanın yeni oluşturulan dosyalar ve alt dizinler için varsayılan değer olduğu anlamına gelir.

- Dosya bir dizin FILE_ATTRIBUTE_DIRECTORY.

- FILE_ATTRIBUTE_NORMAL dosyanın başka bir öznitelik ayarlanmamış. Bu öznitelik yalnızca tek başına kullanıldığında geçerlidir. Diğer tüm dosya öznitelikleri bu özniteliği geçersiz kılar.

- FILE_ATTRIBUTE_HIDDEN dosya gizli. Sıradan bir dizin listesine dahil edilmez.

- FILE_ATTRIBUTE_READONLY dosya salt okunurdur. Uygulamalar dosyayı okuyabilir, ancak yazamaz veya silemez.

- Dosyanın bir parçası olan veya yalnızca işletim sistemi tarafından kullanılan FILE_ATTRIBUTE_SYSTEM.

- FILE_ATTRIBUTE_TEMPORARY dosya geçici depolama için kullanılıyor. Uygulamalar yalnızca kesinlikle gerekli olduğunda dosyaya yazmalıdır. Dosya yakında silineceğinden, dosyanın verilerinin çoğu medyaya boşaltılmadan bellekte kalır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0. Genişletilmiş hata bilgilerini almak için, WIN32 [işlevini çağırın](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror).

### <a name="remarks"></a>Açıklamalar

Çağrılmadan önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir `MatchesMask` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#35](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_5.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CObject sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CFtpFileFind sınıfı](../../mfc/reference/cftpfilefind-class.md)<br/>
[CGopherFileFind sınıfı](../../mfc/reference/cgopherfilefind-class.md)<br/>
[CInternetFile sınıfı](../../mfc/reference/cinternetfile-class.md)<br/>
[CGopherFile sınıfı](../../mfc/reference/cgopherfile-class.md)<br/>
[CHttpFile sınıfı](../../mfc/reference/chttpfile-class.md)
