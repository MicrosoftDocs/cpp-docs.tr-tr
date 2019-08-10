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
ms.openlocfilehash: f2dfd3421d2154b4894b62b71d7993c483a77c53
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68916132"
---
# <a name="cfilefind-class"></a>CFileFind sınıfı

Yerel dosya aramalarını gerçekleştirir ve Internet dosya aramalarını gerçekleştiren [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) ve [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md)için temel sınıftır.

## <a name="syntax"></a>Sözdizimi

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
|[CFileFind:: m_pTM](#m_ptm)|Bir `CAtlTransactionManager` nesne işaretçisi.|

## <a name="remarks"></a>Açıklamalar

`CFileFind`bir aramayı başlatır, bir dosya bulur ve dosyanın başlığını, adını veya yolunu döndüren üye işlevlerini içerir. Internet aramalarında, [GetFileURL](#getfileurl) üye işlevi dosyanın URL 'sini döndürür.

`CFileFind`, özel sunucu türlerini aramak için tasarlanan iki diğer mfc sınıfının temel sınıfıdır: `CGopherFileFind` özel olarak Gopher sunucularıyla çalışıyor ve `CFtpFileFind` özellikle FTP sunucularıyla çalışıyor. Bu üç sınıf birlikte, bir yerel makinede veya uzak bir sunucuda Sunucu protokolüne, dosya türüne veya konumdan bağımsız olarak, istemcinin dosyaları bulması için sorunsuz bir mekanizma sağlar.

Aşağıdaki kod, her bir dosyanın adını yazdırarak geçerli dizindeki tüm dosyaları numaralandıracaktır:

[!code-cpp[NVC_MFCFiles#31](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_1.cpp)]

Örneği basit tutmak için, bu kod C++ standart kitaplık `cout` sınıfını kullanır. Satır, örneğin grafik kullanıcı arabirimine sahip bir programda `CListBox::AddString`bir çağrısıyla değiştirilebilir. `cout`

Ve diğer WinINet sınıflarının kullanımı `CFileFind` hakkında daha fazla bilgi için bkz. [Wininet ile Internet programlama](../../mfc/win32-internet-extensions-wininet.md)makalesi.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CFileFind`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

##  <a name="cfilefind"></a>CFileFind:: CFileFind

Bu üye işlevi, bir `CFileFind` nesne oluşturulduğunda çağrılır.

```
CFileFind();
CFileFind(CAtlTransactionManager* pTM);
```

### <a name="parameters"></a>Parametreler

*pTM*<br/>
CAtlTransactionManager nesnesine yönelik işaretçi

### <a name="example"></a>Örnek

  [CFileFind:: GetFileName](#getfilename)örneğine bakın.

##  <a name="close"></a>CFileFind:: Close

Aramayı sonlandırmak, bağlamı sıfırlamak ve tüm kaynakları serbest bırakmak için bu üye işlevini çağırın.

```
void Close();
```

### <a name="remarks"></a>Açıklamalar

Çağrıldıktan `Close`sonra yeni bir aramaya başlamak için [FindFile](#findfile) çağrılmadan önce `CFileFind` yeni bir örnek oluşturmanız gerekmez.

### <a name="example"></a>Örnek

  [CFileFind:: GetFileName](#getfilename)örneğine bakın.

##  <a name="closecontext"></a>CFileFind:: CloseContext

Geçerli arama tanıtıcısı tarafından belirtilen dosyayı kapatır.

```
virtual void CloseContext();
```

### <a name="remarks"></a>Açıklamalar

Arama tanıtıcısının geçerli değeri tarafından belirtilen dosyayı kapatır. Varsayılan davranışı değiştirmek için bu işlevi geçersiz kılın.

Geçerli bir arama tanıtıcısını almak için [FindFile](#findfile) veya [FindNextFile](#findnextfile) işlevlerini en az bir kez çağırmanız gerekir. `FindFile` Ve`FindNextFile` işlevleri, belirli bir adla eşleşen adlara sahip dosyaları bulmak için arama tanıtıcısını kullanır.

##  <a name="findfile"></a>CFileFind:: FindFile

Bir dosya aramasını açmak için bu üye işlevini çağırın.

```
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,
    DWORD dwUnused = 0);
```

### <a name="parameters"></a>Parametreler

*pstrName*<br/>
Bulunacak dosyanın adını içeren bir dize işaretçisi. *PstrName*için null geçirirseniz, `FindFile` bir joker karakter (*.\*) arama yapar.

*Dwkullanılmamış*<br/>
Türetilmiş sınıflarla polimorfik hale getirmek `FindFile` için ayrılmıştır. 0 olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0. Genişletilmiş hata bilgilerini almak için, WIN32 işlevini çağırın [](/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror).

### <a name="remarks"></a>Açıklamalar

Dosya aramasına `FindFile` başlamak için çağrıldıktan sonra, sonraki dosyaları almak için [FindNextFile](#findnextfile) öğesini çağırın. Aşağıdaki öznitelik üye `FindNextFile` işlevlerinden birini çağırmadan önce en az bir kez çağırmanız gerekir:

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

##  <a name="findnextfile"></a>CFileFind:: FindNextFile

Bu üye işlevini, önceki bir [FindFile](#findfile)çağrısından bir dosya aramasına devam etmek için çağırın.

```
virtual BOOL FindNextFile();
```

### <a name="return-value"></a>Dönüş Değeri

Daha fazla dosya varsa sıfır dışı; Dosya, dizinde sonuncu ise veya bir hata oluştuysa sıfır olur. Genişletilmiş hata bilgilerini almak için, WIN32 işlevini çağırın [](/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror). Bulunan dosya dizindeki son dosya ise veya eşleşen dosya bulunamazsa `GetLastError` , işlev ERROR_NO_MORE_FILES döndürür.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki öznitelik üye `FindNextFile` işlevlerinden birini çağırmadan önce en az bir kez çağırmanız gerekir:

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

`FindNextFile`Win32 işlevi [FindNextFile dosyasını](/windows/desktop/api/fileapi/nf-fileapi-findnextfilea)kaydırır.

### <a name="example"></a>Örnek

  [CFileFind:: IsDirectory](#isdirectory)örneğine bakın.

##  <a name="getcreationtime"></a>CFileFind:: GetCreationTime

Belirtilen dosyanın oluşturulduğu saati almak için bu üye işlevi çağırın.

```
virtual BOOL GetCreationTime(FILETIME* pTimeStamp) const;
virtual BOOL GetCreationTime(CTime& refTime) const;
```

### <a name="parameters"></a>Parametreler

*pTimeStamp*<br/>
Dosya oluşturulduğu saati içeren bir [filetime](/windows/desktop/api/minwinbase/ns-minwinbase-filetime) yapısına yönelik işaretçi.

*refTime*<br/>
[CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesine bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; başarısız ise 0. `GetCreationTime`Bu`CFileFind` nesnede [FindNextFile](#findnextfile) hiç çağrılmadıysa 0 değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Çağrılmadan`GetCreationTime`önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir.

> [!NOTE]
>  Tüm dosya sistemleri bu işlev tarafından döndürülen zaman damgasını uygulamak için aynı semantiğini kullanmaz. Bu işlev, temeldeki dosya sistemi veya sunucusu zaman özniteliğini tutmayı desteklemiyorsa, diğer zaman damgası işlevleri tarafından döndürülen değeri döndürebilir. Zaman biçimleri hakkında bilgi için bkz. [Win32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-win32_find_dataa) yapısı. Bazı işletim sistemlerinde döndürülen süre, makinenin yerel olarak bulunduğu saat dilimindedir. Daha fazla bilgi için bkz. Win32 [FileTimeToLocalFileTime](/windows/desktop/api/fileapi/nf-fileapi-filetimetolocalfiletime) API.

### <a name="example"></a>Örnek

  [CFileFind:: GetLength](#getlength)örneğine bakın.

##  <a name="getfilename"></a>CFileFind:: GetFileName

Bulunan dosyanın adını almak için bu üye işlevini çağırın.

```
virtual CString GetFileName() const;
```

### <a name="return-value"></a>Dönüş Değeri

En son bulunan dosyanın adı.

### <a name="remarks"></a>Açıklamalar

GetFileName çağrısından önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir.

`GetFileName`, dosya adının bir `CFileFind` biçimini döndüren üç üye işlevden biridir. Aşağıdaki listede, üç ve nasıl değişen açıklanmıştır:

- `GetFileName`Uzantı dahil olmak üzere dosya adını döndürür. Örneğin, `GetFileName` *c:\myhtml\mydosyadosyaları* hakkında bir kullanıcı iletisi oluşturmak için çağırmak *Dosyam. txt*dosya adını döndürür.

- [GetFilePath](#getfilepath) dosyanın tüm yolunu döndürür. Örneğin, `GetFilePath` *c:\myhtml\mydosya.txt* dosyası hakkında bir kullanıcı iletisi oluşturmak için çağırmak *c:\myhtml\my.txt*dosya yolunu döndürür.

- [GetFileTitle](#getfiletitle) , dosya uzantısını dışarıda bırakarak dosya adını döndürür. Örneğin, `GetFileTitle` *c:\myhtml\mydosya.txt* dosyası hakkında bir kullanıcı iletisi oluşturmak için çağırmak dosya başlığı *Dosyam*' ı döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#32](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_2.cpp)]

##  <a name="getfilepath"></a>CFileFind:: GetFilePath

Belirtilen dosyanın tam yolunu almak için bu üye işlevi çağırın.

```
virtual CString GetFilePath() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belirtilen dosyanın yolu.

### <a name="remarks"></a>Açıklamalar

Çağrılmadan`GetFilePath`önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir.

`GetFilePath`, dosya adının bir `CFileFind` biçimini döndüren üç üye işlevden biridir. Aşağıdaki listede, üç ve nasıl değişen açıklanmıştır:

- [GetFileName](#getfilename) , uzantısı da dahil olmak üzere dosya adını döndürür. Örneğin, `GetFileName` *c:\myhtml\mydosyadosyaları* hakkında bir kullanıcı iletisi oluşturmak için çağırmak *Dosyam. txt*dosya adını döndürür.

- `GetFilePath`dosyanın tüm yolunu döndürür. Örneğin, dosya `c:\myhtml\myfile.txt` hakkında `GetFilePath` bir kullanıcı iletisi oluşturmak için çağırmak dosya yolunu `c:\myhtml\myfile.txt`döndürür.

- [GetFileTitle](#getfiletitle) , dosya uzantısını dışarıda bırakarak dosya adını döndürür. Örneğin, `GetFileTitle` *c:\myhtml\mydosya.txt* dosyası hakkında bir kullanıcı iletisi oluşturmak için çağırmak dosya başlığı *Dosyam*' ı döndürür.

### <a name="example"></a>Örnek

  [CFileFind:: GetFileName](#getfilename)örneğine bakın.

##  <a name="getfiletitle"></a>CFileFind:: GetFileTitle

Bulunan dosyanın başlığını almak için bu üye işlevini çağırın.

```
virtual CString GetFileTitle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dosyanın başlığı.

### <a name="remarks"></a>Açıklamalar

Çağrılmadan`GetFileTitle`önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir.

`GetFileTitle`, dosya adının bir `CFileFind` biçimini döndüren üç üye işlevden biridir. Aşağıdaki listede, üç ve nasıl değişen açıklanmıştır:

- [GetFileName](#getfilename) , uzantısı da dahil olmak üzere dosya adını döndürür. Örneğin, `GetFileName` *c:\myhtml\mydosyadosyaları* hakkında bir kullanıcı iletisi oluşturmak için çağırmak *Dosyam. txt*dosya adını döndürür.

- [GetFilePath](#getfilepath) dosyanın tüm yolunu döndürür. Örneğin, `GetFilePath` *c:\myhtml\mydosya.txt* dosyası hakkında bir kullanıcı iletisi oluşturmak için çağırmak *c:\myhtml\my.txt*dosya yolunu döndürür.

- `GetFileTitle`Dosya Uzantısı hariç dosya adını döndürür. Örneğin, `GetFileTitle` *c:\myhtml\mydosya.txt* dosyası hakkında bir kullanıcı iletisi oluşturmak için çağırmak dosya başlığı *Dosyam*' ı döndürür.

### <a name="example"></a>Örnek

  [CFileFind:: GetFileName](#getfilename)örneğine bakın.

##  <a name="getfileurl"></a>CFileFind:: GetFileURL

Belirtilen URL 'YI almak için bu üye işlevini çağırın.

```
virtual CString GetFileURL() const;
```

### <a name="return-value"></a>Dönüş Değeri

URL 'nin tamamı.

### <a name="remarks"></a>Açıklamalar

Çağrılmadan`GetFileURL`önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir.

`GetFileURL`, formdaki `file://path`URL 'yi döndürmesi dışında, [GetFilePath](#getfilepath)üye işlevine benzerdir. Örneğin, *Dosyam. txt* URL 'sini almak için çağırmak `file://c:\myhtml\myfile.txt` `GetFileURL` , URL 'yi döndürür.

### <a name="example"></a>Örnek

  [CFileFind:: GetFileName](#getfilename)örneğine bakın.

##  <a name="getlastaccesstime"></a>CFileFind:: GetLastAccessTime

Belirtilen dosyanın son erişildiği saati almak için bu üye işlevini çağırın.

```
virtual BOOL GetLastAccessTime(CTime& refTime) const;
virtual BOOL GetLastAccessTime(FILETIME* pTimeStamp) const;
```

### <a name="parameters"></a>Parametreler

*refTime*<br/>
[CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesine bir başvuru.

*pTimeStamp*<br/>
Dosyanın son erişildiği saati içeren bir [filetime](/windows/desktop/api/minwinbase/ns-minwinbase-filetime) yapısına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; başarısız ise 0. `GetLastAccessTime`Bu`CFileFind` nesnede [FindNextFile](#findnextfile) hiç çağrılmadıysa 0 değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Çağrılmadan`GetLastAccessTime`önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir.

> [!NOTE]
>  Tüm dosya sistemleri bu işlev tarafından döndürülen zaman damgasını uygulamak için aynı semantiğini kullanmaz. Bu işlev, temeldeki dosya sistemi veya sunucusu zaman özniteliğini tutmayı desteklemiyorsa, diğer zaman damgası işlevleri tarafından döndürülen değeri döndürebilir. Zaman biçimleri hakkında bilgi için bkz. [Win32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-win32_find_dataa) yapısı. Bazı işletim sistemlerinde döndürülen süre, makinenin yerel olarak bulunduğu saat dilimindedir. Daha fazla bilgi için bkz. Win32 [FileTimeToLocalFileTime](/windows/desktop/api/fileapi/nf-fileapi-filetimetolocalfiletime) API.

### <a name="example"></a>Örnek

  [CFileFind:: GetLength](#getlength)örneğine bakın.

##  <a name="getlastwritetime"></a>CFileFind:: GetLastWriteTime

Dosyanın son değiştirildiği zamanı almak için bu üye işlevi çağırın.

```
virtual BOOL GetLastWriteTime(FILETIME* pTimeStamp) const;
virtual BOOL GetLastWriteTime(CTime& refTime) const;
```

### <a name="parameters"></a>Parametreler

*pTimeStamp*<br/>
Dosyanın son yazıldığı saati içeren bir [filetime](/windows/desktop/api/minwinbase/ns-minwinbase-filetime) yapısına yönelik işaretçi.

*refTime*<br/>
[CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesine bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; başarısız ise 0. `GetLastWriteTime`Bu`CFileFind` nesnede [FindNextFile](#findnextfile) hiç çağrılmadıysa 0 değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Çağrılmadan`GetLastWriteTime`önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir.

> [!NOTE]
>  Tüm dosya sistemleri bu işlev tarafından döndürülen zaman damgasını uygulamak için aynı semantiğini kullanmaz. Bu işlev, temeldeki dosya sistemi veya sunucusu zaman özniteliğini tutmayı desteklemiyorsa, diğer zaman damgası işlevleri tarafından döndürülen değeri döndürebilir. Zaman biçimleri hakkında bilgi için bkz. [Win32_Find_Data](/windows/desktop/api/minwinbase/ns-minwinbase-win32_find_dataa) yapısı. Bazı işletim sistemlerinde döndürülen süre, makinenin yerel olarak bulunduğu saat dilimindedir. Daha fazla bilgi için bkz. Win32 [FileTimeToLocalFileTime](/windows/desktop/api/fileapi/nf-fileapi-filetimetolocalfiletime) API.

### <a name="example"></a>Örnek

  [CFileFind:: GetLength](#getlength)örneğine bakın.

##  <a name="getlength"></a>CFileFind:: GetLength

Bulunan dosyanın uzunluğunu bayt olarak almak için bu üye işlevini çağırın.

```
ULONGLONG GetLength() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bulunan dosyanın bayt cinsinden uzunluğu.

### <a name="remarks"></a>Açıklamalar

Çağrılmadan`GetLength`önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir.

`GetLength`dosya boyutunun değerini almak ve bayt cinsinden döndürmek için [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-win32_find_dataa) Win32 yapısını kullanır.

> [!NOTE]
>  MFC 7,0 `GetLength` itibariyle 64 bit tamsayı türlerini destekler. Kitaplığın bu yeni sürümüyle oluşturulmuş daha önceden varolan kod, kesme uyarılarına neden olabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#33](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_3.cpp)]

##  <a name="getroot"></a>CFileFind:: GetRoot

Bulunan dosyanın kökünü almak için bu üye işlevini çağırın.

```
virtual CString GetRoot() const;
```

### <a name="return-value"></a>Dönüş Değeri

Etkin aramanın kökü.

### <a name="remarks"></a>Açıklamalar

Çağrılmadan`GetRoot`önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir.

Bu üye işlevi, bir aramayı başlatmak için kullanılan sürücü tanımlayıcısını ve yol adını döndürür. Örneğin, [FindFile](#findfile) `*.dat` öğesini boş bir dize `GetRoot` döndüren sonuçlarla çağırma. `c:\windows\system\*.dll`Bir yolu, örneğin `FindFile` , döndüren `GetRoot` `c:\windows\system\`sonuçlara geçirme.

### <a name="example"></a>Örnek

  [CFileFind:: GetFileName](#getfilename)örneğine bakın.

##  <a name="isarchived"></a>CFileFind:: ısarşivlendi

Bulunan dosyanın arşivlenip arşivlenmediğini öğrenmek için bu üye işlevi çağırın.

```
BOOL IsArchived() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Uygulamalar, [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-win32_find_dataa) yapısında tanımlanan bir dosya ÖZNITELIĞI olan FILE_ATTRIBUTE_ARCHIVE ile yedeklenecek veya kaldırılacak olan bir arşiv dosyasını işaretler.

Çağrılmadan`IsArchived`önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir.

Dosya özniteliklerinin tüm listesi için bkz. [MatchesMask](#matchesmask) üye işlevi.

### <a name="example"></a>Örnek

  [CFileFind:: GetLength](#getlength)örneğine bakın.

##  <a name="iscompressed"></a>CFileFind:: IsCompressed

Bulunan dosyanın sıkıştırılıp sıkıştırılmadığını öğrenmek için bu üye işlevi çağırın.

```
BOOL IsCompressed() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Sıkıştırılmış bir dosya, [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-win32_find_dataa) yapısında tanımlanan bir dosya ÖZNITELIĞI olan FILE_ATTRIBUTE_COMPRESSED ile işaretlenir. Bir dosya için bu öznitelik, dosyadaki tüm verilerin sıkıştırıldığını gösterir. Bir dizin için bu öznitelik, yeni oluşturulan dosyalar ve alt dizinler için sıkıştırmanın varsayılan olduğunu gösterir.

Çağrılmadan`IsCompressed`önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir.

Dosya özniteliklerinin tüm listesi için bkz. [MatchesMask](#matchesmask) üye işlevi.

### <a name="example"></a>Örnek

  [CFileFind:: GetLength](#getlength)örneğine bakın.

##  <a name="isdirectory"></a>CFileFind:: IsDirectory

Bulunan dosyanın bir dizin olup olmadığını öğrenmek için bu üye işlevi çağırın.

```
BOOL IsDirectory() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir dizin olan dosya, [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-win32_find_dataa) yapısında tanımlanan FILE_ATTRIBUTE_DIRECTORY a File özniteliğiyle işaretlenir.

Çağrılmadan`IsDirectory`önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir.

Dosya özniteliklerinin tüm listesi için bkz. [MatchesMask](#matchesmask) üye işlevi.

### <a name="example"></a>Örnek

Bu küçük program, C:\ üzerindeki her dizini tekrarlayan dizinin adını sürücü olarak yazdırın ve yazdırır.

[!code-cpp[NVC_MFCFiles#34](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_4.cpp)]

##  <a name="isdots"></a>CFileFind:: ısnoktalar

Dosyalar arasında yineleme yaparken geçerli dizin ve üst dizin işaretçilerini sınamak için bu üye işlevi çağırın.

```
virtual BOOL IsDots() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bulunan dosyanın adı "." veya ".." ise, bulunan dosyanın gerçekten bir dizin olduğunu gösterir. Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Çağrılmadan`IsDots`önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir.

### <a name="example"></a>Örnek

  [CFileFind:: IsDirectory](#isdirectory)örneğine bakın.

##  <a name="ishidden"></a>CFileFind:: IsHidden

Bulunan dosyanın gizlenip gizlenmediğini öğrenmek için bu üye işlevini çağırın.

```
BOOL IsHidden() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

[WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-win32_find_dataa) yapısında tanımlanan bir dosya ÖZNITELIĞI olan FILE_ATTRIBUTE_HIDDEN ile işaretlenen gizli dosyalar. Gizli bir dosya sıradan bir dizin listesine dahil edilmez.

Çağrılmadan`IsHidden`önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir.

Dosya özniteliklerinin tüm listesi için bkz. [MatchesMask](#matchesmask) üye işlevi.

### <a name="example"></a>Örnek

  [CFileFind:: GetLength](#getlength)örneğine bakın.

##  <a name="isnormal"></a>CFileFind:: IsNormal

Bulunan dosyanın normal bir dosya olup olmadığını öğrenmek için bu üye işlevini çağırın.

```
BOOL IsNormal() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

[WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-win32_find_dataa) yapısında tanımlanan bir dosya ÖZNITELIĞI olan FILE_ATTRIBUTE_NORMAL ile işaretlenmiş dosyalar. Normal bir dosyanın ayarlanmış başka bir özniteliği yok. Diğer tüm dosya öznitelikleri bu özniteliği geçersiz kılar.

Çağrılmadan`IsNormal`önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir.

Dosya özniteliklerinin tüm listesi için bkz. [MatchesMask](#matchesmask) üye işlevi.

### <a name="example"></a>Örnek

  [CFileFind:: GetLength](#getlength)örneğine bakın.

##  <a name="isreadonly"></a>CFileFind:: IsReadOnly

Bulunan dosyanın salt okunurdur olup olmadığını öğrenmek için bu üye işlevini çağırın.

```
BOOL IsReadOnly() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Salt okunurdur bir dosya özniteliği, [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-win32_find_dataa) yapısında tanımlanan bir dosya ÖZNITELIĞI olan FILE_ATTRIBUTE_READONLY ile işaretlenir. Uygulamalar böyle bir dosyayı okuyabilir, ancak bunlara yazamaz veya silemez.

Çağrılmadan`IsReadOnly`önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir.

Dosya özniteliklerinin tüm listesi için bkz. [MatchesMask](#matchesmask) üye işlevi.

### <a name="example"></a>Örnek

  [CFileFind:: GetLength](#getlength)örneğine bakın.

##  <a name="issystem"></a>CFileFind:: IsSystem

Bulunan dosyanın bir sistem dosyası olup olmadığını öğrenmek için bu üye işlevi çağırın.

```
BOOL IsSystem() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir sistem dosyası, [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-win32_find_dataa) yapısında tanımlanan bir dosya ÖZNITELIĞI olan FILE_ATTRIBUTE_SYSTEM ile işaretlenir. Bir sistem dosyası, işletim sistemi tarafından bir parçasıdır veya yalnızca tarafından kullanılır.

Çağrılmadan`IsSystem`önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir.

Dosya özniteliklerinin tüm listesi için bkz. [MatchesMask](#matchesmask) üye işlevi.

### <a name="example"></a>Örnek

  [CFileFind:: GetLength](#getlength)örneğine bakın.

##  <a name="istemporary"></a>CFileFind:: Istesel önemli

Bulunan dosyanın geçici bir dosya olup olmadığını anlamak için bu üye işlevi çağırın.

```
BOOL IsTemporary() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Geçici bir dosya, [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-win32_find_dataa) yapısında tanımlanan bir dosya ÖZNITELIĞI olan FILE_ATTRIBUTE_TEMPORARY ile işaretlenir. Geçici depolama için geçici bir dosya kullanılır. Uygulamalar yalnızca kesinlikle gerekli olduğunda dosyaya yazmalıdır. Dosya yakında silineceğinden, dosyanın verilerinin çoğu medyaya boşaltılmadan bellekte kalır.

Çağrılmadan`IsTemporary`önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir.

Dosya özniteliklerinin tüm listesi için bkz. [MatchesMask](#matchesmask) üye işlevi.

### <a name="example"></a>Örnek

  [CFileFind:: GetLength](#getlength)örneğine bakın.

##  <a name="m_ptm"></a>CFileFind:: m_pTM

Bir `CAtlTransactionManager` nesne işaretçisi.

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>Açıklamalar

##  <a name="matchesmask"></a>CFileFind:: MatchesMask

Dosya özniteliklerini bulunan dosyada sınamak için bu üye işlevini çağırın.

```
virtual BOOL MatchesMask(DWORD dwMask) const;
```

### <a name="parameters"></a>Parametreler

*dwMask*<br/>
Bulunan dosya için [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-win32_find_dataa) yapısında tanımlanan bir veya daha fazla dosya özniteliği belirtir. Birden çok özniteliği aramak için bit düzeyinde OR (&#124;) işlecini kullanın. Aşağıdaki özniteliklerin herhangi bir birleşimi kabul edilebilir:

- FILE_ATTRIBUTE_ARCHIVE dosya bir arşiv dosyasıdır. Uygulamalar, dosyaları yedekleme veya kaldırma için işaretlemek üzere bu özniteliği kullanır.

- FILE_ATTRIBUTE_COMPRESSED dosya veya dizin sıkıştırıldı. Bir dosya için bu, dosyadaki tüm verilerin sıkıştırıldığı anlamına gelir. Bir dizin için bu, sıkıştırmanın yeni oluşturulan dosyalar ve alt dizinler için varsayılan değer olduğu anlamına gelir.

- FILE_ATTRIBUTE_DIRECTORY, dosya bir dizindir.

- FILE_ATTRIBUTE_NORMAL dosyanın ayarlanmış başka bir özniteliği yok. Bu öznitelik yalnızca tek başına kullanıldığında geçerlidir. Diğer tüm dosya öznitelikleri bu özniteliği geçersiz kılar.

- FILE_ATTRIBUTE_HIDDEN, dosya gizlidir. Sıradan bir dizin listesine dahil edilmez.

- FILE_ATTRIBUTE_READONLY dosya salt okunurdur. Uygulamalar dosyayı okuyabilir, ancak yazamaz veya silemez.

- FILE_ATTRIBUTE_SYSTEM, dosyanın bir parçasıdır veya yalnızca işletim sistemi tarafından kullanılır.

- FILE_ATTRIBUTE_TEMPORARY dosya geçici depolama için kullanılıyor. Uygulamalar yalnızca kesinlikle gerekli olduğunda dosyaya yazmalıdır. Dosya yakında silineceğinden, dosyanın verilerinin çoğu medyaya boşaltılmadan bellekte kalır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0. Genişletilmiş hata bilgilerini almak için, WIN32 işlevini çağırın [](/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror).

### <a name="remarks"></a>Açıklamalar

Çağrılmadan`MatchesMask`önce [FindNextFile](#findnextfile) öğesini en az bir kez çağırmanız gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#35](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_5.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CFtpFileFind Sınıfı](../../mfc/reference/cftpfilefind-class.md)<br/>
[CGopherFileFind Sınıfı](../../mfc/reference/cgopherfilefind-class.md)<br/>
[CInternetFile Sınıfı](../../mfc/reference/cinternetfile-class.md)<br/>
[CGopherFile Sınıfı](../../mfc/reference/cgopherfile-class.md)<br/>
[CHttpFile Sınıfı](../../mfc/reference/chttpfile-class.md)
