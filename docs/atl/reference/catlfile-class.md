---
title: CAtlFile sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAtlFile
- ATLFILE/ATL::CAtlFile
- ATLFILE/ATL::CAtlFile::CAtlFile
- ATLFILE/ATL::CAtlFile::Create
- ATLFILE/ATL::CAtlFile::Flush
- ATLFILE/ATL::CAtlFile::GetOverlappedResult
- ATLFILE/ATL::CAtlFile::GetPosition
- ATLFILE/ATL::CAtlFile::GetSize
- ATLFILE/ATL::CAtlFile::LockRange
- ATLFILE/ATL::CAtlFile::Read
- ATLFILE/ATL::CAtlFile::Seek
- ATLFILE/ATL::CAtlFile::SetSize
- ATLFILE/ATL::CAtlFile::UnlockRange
- ATLFILE/ATL::CAtlFile::Write
- ATLFILE/ATL::CAtlFile::m_pTM
helpviewer_keywords:
- CAtlFile class
ms.assetid: 93ed160b-af2a-448c-9cbe-e5fa46c199bb
ms.openlocfilehash: 60d645d8818a0d073e4f52f22d836b34da96694f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50524611"
---
# <a name="catlfile-class"></a>CAtlFile sınıfı

Bu sınıf, dosya işleme API Windows çevresinde ince bir sarmalayıcı sağlar.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CAtlFile : public CHandle
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAtlFile::CAtlFile](#catlfile)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAtlFile::Create](#create)|Bir dosyayı açmak veya oluşturmak için bu yöntemi çağırın.|
|[CAtlFile::Flush](#flush)|Dosya için arabellek temizleyin ve dosyaya yazılacak tüm arabelleğe alınan verileri neden için bu yöntemi çağırın.|
|[CAtlFile::GetOverlappedResult](#getoverlappedresult)|Dosya çakışan bir işlem sonuçlarını almak için bu yöntemi çağırın.|
|[CAtlFile::GetPosition](#getposition)|Geçerli dosya işaretçisi konumunu dosyasından almak için bu yöntemi çağırın.|
|[CAtlFile::GetSize](#getsize)|Dosyanın bayt cinsinden boyutunu almak için bu yöntemi çağırın.|
|[CAtlFile::LockRange](#lockrange)|Diğer işlemlerin erişimini engellemek için dosyanın bir bölgede kilitlemek için bu yöntemi çağırın.|
|[CAtlFile::Read](#read)|Dosya işaretçisi tarafından belirtilen konumda başlayan bir dosyadan veri okumak için bu yöntemi çağırın.|
|[CAtlFile::Seek](#seek)|Dosya işaretçisini dosyanın taşımak için bu yöntemi çağırın.|
|[CAtlFile::SetSize](#setsize)|Dosya boyutunu ayarlamak için bu yöntemi çağırın.|
|[CAtlFile::UnlockRange](#unlockrange)|Bir bölge dosyanın kilidini açmak için bu yöntemi çağırın.|
|[CAtlFile::Write](#write)|Dosya işaretçisi tarafından belirtilen konumda başlayarak dosyaya veri yazmak için bu yöntemi çağırın.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAtlFile::m_pTM](#m_ptm)|İşaretçi `CAtlTransactionManager` nesnesi|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, dosya işleme gereksinimlerini oldukça basittir ancak MFC bağımlılıklar dahil olmak üzere Windows API sağladığından daha fazla soyutlama gerekli olduğu durumlarda kullanın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CHandle](../../atl/reference/chandle-class.md)

`CAtlFile`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlfile.h

##  <a name="catlfile"></a>  CAtlFile::CAtlFile

Oluşturucu.

```
CAtlFile() throw();
CAtlFile(CAtlTransactionManager* pTM = NULL) throw();
CAtlFile(CAtlFile& file) throw();
explicit CAtlFile(HANDLE hFile) throw();
```

### <a name="parameters"></a>Parametreler

*Dosya*<br/>
Dosya nesnesi.

*Hfıle*<br/>
Dosya tanıtıcısı.

*pTM*<br/>
CAtlTransactionManager nesne işaretçisi

### <a name="remarks"></a>Açıklamalar

Kopya Oluşturucu, özgün dosya tanıtıcısı sahipliğini aktarır `CAtlFile` yeni oluşturulmuş nesne için nesne.

##  <a name="create"></a>  CAtlFile::Create

Bir dosyayı açmak veya oluşturmak için bu yöntemi çağırın.

```
HRESULT Create(
    LPCTSTR szFilename,
    DWORD dwDesiredAccess,
    DWORD dwShareMode,
    DWORD dwCreationDisposition,
    DWORD dwFlagsAndAttributes = FILE_ATTRIBUTE_NORMAL,
    LPSECURITY_ATTRIBUTES lpsa = NULL,
    HANDLE hTemplateFile = NULL) throw();
```

### <a name="parameters"></a>Parametreler

*szFilename*<br/>
Dosya adı.

*dwDesiredAccess*<br/>
İstenen erişim. Bkz: *dwDesiredAccess* içinde [CreateFile](/windows/desktop/api/fileapi/nf-fileapi-createfilea) Windows SDK.

*dwShareMode*<br/>
Paylaşım modu. Bkz: *dwShareMode* içinde `CreateFile`.

*dwCreationDisposition*<br/>
Oluşturma değerlendirme. Bkz: *dwCreationDisposition* içinde `CreateFile`.

*dwFlagsAndAttributes*<br/>
Bayraklar ve öznitelikleri. Bkz: *dwFlagsAndAttributes* içinde `CreateFile`.

*lpsa*<br/>
Güvenlik öznitelikleri. Bkz: *lpSecurityAttributes* içinde `CreateFile`.

*hTemplateFile*<br/>
Şablon dosyası. Bkz: *hTemplateFile* içinde `CreateFile`.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Çağrıları [CreateFile](/windows/desktop/api/fileapi/nf-fileapi-createfilea) oluşturma veya dosyasını açın.

##  <a name="flush"></a>  CAtlFile::Flush

Dosya için arabellek temizleyin ve dosyaya yazılacak tüm arabelleğe alınan verileri neden için bu yöntemi çağırın.

```
HRESULT Flush() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Çağrıları [FlushFileBuffers](/windows/desktop/api/fileapi/nf-fileapi-flushfilebuffers) dosyayı arabelleğe alınan verileri temizleyemedi.

##  <a name="getoverlappedresult"></a>  CAtlFile::GetOverlappedResult

Dosya çakışan bir işlem sonuçlarını almak için bu yöntemi çağırın.

```
HRESULT GetOverlappedResult(
    LPOVERLAPPED pOverlapped,
    DWORD& dwBytesTransferred,
    BOOL bWait) throw();
```

### <a name="parameters"></a>Parametreler

*pOverlapped*<br/>
Çakışan yapı. Bkz: *lpOverlapped* içinde [GetOverlappedResult](/windows/desktop/api/ioapiset/nf-ioapiset-getoverlappedresult) Windows SDK.

*dwBytesTransferred*<br/>
Bayt aktarıldı. Bkz: *lpNumberOfBytesTransferred* içinde `GetOverlappedResult`.

*bWait*<br/>
Bekleme seçeneği. Bkz: *bWait* içinde `GetOverlappedResult`.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Çağrıları [GetOverlappedResult](/windows/desktop/api/ioapiset/nf-ioapiset-getoverlappedresult) dosya çubuğunda çakışan bir işlem sonuçlarını almak için.

##  <a name="getposition"></a>  CAtlFile::GetPosition

Geçerli dosya işaretçisi konumunu almak için bu yöntemi çağırın.

```
HRESULT GetPosition(ULONGLONG& nPos) const throw();
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
Bayt cinsinden konumu.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Çağrıları [SetFilePointer](/windows/desktop/api/fileapi/nf-fileapi-setfilepointer) geçerli dosya işaretçisi konumunu almak için.

##  <a name="getsize"></a>  CAtlFile::GetSize

Dosyanın bayt cinsinden boyutunu almak için bu yöntemi çağırın.

```
HRESULT GetSize(ULONGLONG& nLen) const throw();
```

### <a name="parameters"></a>Parametreler

*nLen*<br/>
Dosyanın bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Çağrıları [GetFileSize](/windows/desktop/api/fileapi/nf-fileapi-getfilesize) dosyasının bayt cinsinden boyutunu almak için.

##  <a name="lockrange"></a>  CAtlFile::LockRange

Diğer işlemlerin erişimini engellemek için dosyanın bir bölgede kilitlemek için bu yöntemi çağırın.

```
HRESULT LockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
Kilit nerede başlayacağını dosyanın konumu.

*nCount*<br/>
Kilitlenecek bayt aralığı cinsinden uzunluğu.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Çağrıları [LockFile](/windows/desktop/api/fileapi/nf-fileapi-lockfile) bir bölgede dosyası kilitlenemiyor. Bir dosyadaki baytları kilitleme erişim için bu baytlardan başka işlemler tarafından engeller. Bir dosyanın birden fazla bölgeye kilitleyebilirsiniz ancak çakışan bölge izin verilir. Bir bölge kilidini kaldırdığında kullanarak [CAtlFile::UnlockRange](#unlockrange), bayt aralığı, önceden kilitli olan bölge tam olarak karşılık gelmelidir. `LockRange` bitişik bölgeleri birleştirmez; kilitli iki bölgeleri bitişikse, her ayrı olarak kilidini açmanız gerekir.

##  <a name="m_ptm"></a>  CAtlFile::m_pTM

İşaretçi bir `CAtlTransactionManager` nesne.

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>Açıklamalar

##  <a name="read"></a>  CAtlFile::Read

Dosya işaretçisi tarafından belirtilen konumda başlayan bir dosyadan veri okumak için bu yöntemi çağırın.

```
HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize) throw();

HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    DWORD& nBytesRead) throw();

HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    LPOVERLAPPED pOverlapped) throw();

HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    LPOVERLAPPED pOverlapped,
    LPOVERLAPPED_COMPLETION_ROUTINE pfnCompletionRoutine) throw();
```

### <a name="parameters"></a>Parametreler

*pBuffer*<br/>
Dosyadan okunan veriler alacak arabellek için işaretçi.

*nBufSize*<br/>
Arabellek boyutu bayt cinsinden.

*nBytesRead*<br/>
Okunan bayt sayısı.

*pOverlapped*<br/>
Çakışan yapı. Bkz: *lpOverlapped* içinde [ReadFile](/windows/desktop/api/fileapi/nf-fileapi-readfile) Windows SDK.

*pfnCompletionRoutine*<br/>
Tamamlama yordamı. Bkz: *lpCompletionRoutine* içinde [ReadFileEx](/windows/desktop/api/fileapi/nf-fileapi-readfileex) Windows SDK.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

İlk üç forms çağrı [ReadFile](/windows/desktop/api/fileapi/nf-fileapi-readfile), son [ReadFileEx](/windows/desktop/api/fileapi/nf-fileapi-readfileex) dosyasından veri okunamıyor. Kullanım [CAtlFile::Seek](#seek) dosya işaretçisini taşınır.

##  <a name="seek"></a>  CAtlFile::Seek

Dosya işaretçisini dosyanın taşımak için bu yöntemi çağırın.

```
HRESULT Seek(
    LONGLONG nOffset,
    DWORD dwFrom = FILE_CURRENT) throw();
```

### <a name="parameters"></a>Parametreler

*nOffset*<br/>
Başlangıç noktası tarafından verilen uzaklığı *dwFrom*.

*dwFrom*<br/>
Başlangıç noktası (FILE_BEGIN, FILE_CURRENT veya FILE_END).

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Çağrıları [SetFilePointer](/windows/desktop/api/fileapi/nf-fileapi-setfilepointer) dosya işaretçisini taşınır.

##  <a name="setsize"></a>  CAtlFile::SetSize

Dosya boyutunu ayarlamak için bu yöntemi çağırın.

```
HRESULT SetSize(ULONGLONG nNewLen) throw();
```

### <a name="parameters"></a>Parametreler

*nNewLen*<br/>
Yeni dosyanın bayt cinsinden uzunluğu.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Çağrıları [SetFilePointer](/windows/desktop/api/fileapi/nf-fileapi-setfilepointer) ve [SetEndOfFile](/windows/desktop/api/fileapi/nf-fileapi-setendoffile) dosyasının boyutunu ayarlamak için. Getirisi, dosya işaretçisini dosyanın sonunda konumlandırıldı.

##  <a name="unlockrange"></a>  CAtlFile::UnlockRange

Bir bölge dosyanın kilidini açmak için bu yöntemi çağırın.

```
HRESULT UnlockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
Kilit açma nerede başlayacağını dosya konumu.

*nCount*<br/>
Kilidinin açılması için bayt aralığı cinsinden uzunluğu.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Çağrıları [UnlockFile](/windows/desktop/api/fileapi/nf-fileapi-unlockfile) bir bölge dosyanın kilidini açmak için.

##  <a name="write"></a>  CAtlFile::Write

Dosya işaretçisi tarafından belirtilen konumda başlayarak dosyaya veri yazmak için bu yöntemi çağırın.

```
HRESULT Write(
    LPCVOID pBuffer,
    DWORD nBufSize,
    LPOVERLAPPED pOverlapped,
    LPOVERLAPPED_COMPLETION_ROUTINE pfnCompletionRoutine) throw();

HRESULT Write(
    LPCVOID pBuffer,
    DWORD nBufSize,
    DWORD* pnBytesWritten = NULL) throw();

HRESULT Write(
    LPCVOID pBuffer,
    DWORD nBufSize,
    LPOVERLAPPED pOverlapped) throw();
```

### <a name="parameters"></a>Parametreler

*pBuffer*<br/>
Dosyaya yazılacak veriler içeren arabellek.

*nBufSize*<br/>
Arabellekteki aktarılacak bayt sayısı.

*pOverlapped*<br/>
Çakışan yapı. Bkz: *lpOverlapped* içinde [WriteFile](/windows/desktop/api/fileapi/nf-fileapi-writefile) Windows SDK.

*pfnCompletionRoutine*<br/>
Tamamlama yordamı. Bkz: *lpCompletionRoutine* içinde [WriteFileEx](/windows/desktop/api/fileapi/nf-fileapi-writefileex) Windows SDK.

*pnBytesWritten*<br/>
Yazılan bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

İlk üç forms çağrı [WriteFile](/windows/desktop/api/fileapi/nf-fileapi-writefile), son çağrı [WriteFileEx](/windows/desktop/api/fileapi/nf-fileapi-writefileex) dosyaya veri yazmak için. Kullanım [CAtlFile::Seek](#seek) dosya işaretçisini taşınır.

## <a name="see-also"></a>Ayrıca Bkz.

[Kayan örnek](../../visual-cpp-samples.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)<br/>
[CHandle Sınıfı](../../atl/reference/chandle-class.md)
