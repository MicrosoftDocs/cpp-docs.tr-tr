---
description: 'Daha fazla bilgi edinin: CAtlFile sınıfı'
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
ms.openlocfilehash: d38ab3ad894a589fb59fe03691d6c764414cc8b1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147400"
---
# <a name="catlfile-class"></a>CAtlFile sınıfı

Bu sınıf, Windows dosya işleme API 'SI etrafında ince bir sarmalayıcı sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Syntax

```cpp
class CAtlFile : public CHandle
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAtlFile:: CAtlFile](#catlfile)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAtlFile:: Create](#create)|Bir dosya oluşturmak veya açmak için bu yöntemi çağırın.|
|[CAtlFile:: Flush](#flush)|Dosya için arabellekleri temizlemek ve tüm arabelleğe alınmış verilerin dosyaya yazılmasına neden olmak için bu yöntemi çağırın.|
|[CAtlFile:: GetOverlappedResult](#getoverlappedresult)|Dosyadaki bir çakışan işlemin sonuçlarını almak için bu yöntemi çağırın.|
|[CAtlFile:: GetPosition](#getposition)|Dosyadan geçerli dosya işaretçisi konumunu almak için bu yöntemi çağırın.|
|[CAtlFile:: GetSize](#getsize)|Dosyanın bayt cinsinden boyutunu almak için bu yöntemi çağırın.|
|[CAtlFile:: LockRange](#lockrange)|Diğer işlemlerin bu işleme erişmesini engellemek için dosyadaki bir bölgeyi kilitlemek üzere bu yöntemi çağırın.|
|[CAtlFile:: Read](#read)|Dosya işaretçisi tarafından belirtilen konumdan başlayarak bir dosyadaki verileri okumak için bu yöntemi çağırın.|
|[CAtlFile:: Seek](#seek)|Dosyanın dosya işaretçisini taşımak için bu yöntemi çağırın.|
|[CAtlFile:: SetSize](#setsize)|Dosyanın boyutunu ayarlamak için bu yöntemi çağırın.|
|[CAtlFile:: UnlockRange](#unlockrange)|Dosyanın bir bölgesinin kilidini açmak için bu yöntemi çağırın.|
|[CAtlFile:: Write](#write)|Dosya işaretçisi tarafından belirtilen konumdan başlayarak dosyaya veri yazmak için bu yöntemi çağırın.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAtlFile:: m_pTM](#m_ptm)|Nesne işaretçisi `CAtlTransactionManager`|

## <a name="remarks"></a>Açıklamalar

Dosya işleme ihtiyaçları nispeten basit olduğunda bu sınıfı kullanın, ancak Windows API 'nin sağladığı daha fazla soyutlama, MFC bağımlılıklarını dahil etmeden gereklidir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CHandle](../../atl/reference/chandle-class.md)

`CAtlFile`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlfile. h

## <a name="catlfilecatlfile"></a><a name="catlfile"></a> CAtlFile:: CAtlFile

Oluşturucu.

```cpp
CAtlFile() throw();
CAtlFile(CAtlTransactionManager* pTM = NULL) throw();
CAtlFile(CAtlFile& file) throw();
explicit CAtlFile(HANDLE hFile) throw();
```

### <a name="parameters"></a>Parametreler

*dosyasýný*<br/>
Dosya nesnesi.

*hFile*<br/>
Dosya tanıtıcısı.

*pTM*<br/>
CAtlTransactionManager nesnesine yönelik işaretçi

### <a name="remarks"></a>Açıklamalar

Kopya Oluşturucu, dosya tutamacının sahipliğini özgün `CAtlFile` nesneden yeni oluşturulan nesneye aktarır.

## <a name="catlfilecreate"></a><a name="create"></a> CAtlFile:: Create

Bir dosya oluşturmak veya açmak için bu yöntemi çağırın.

```cpp
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
İstenen erişim. Windows SDK [CreateFile](/windows/win32/api/fileapi/nf-fileapi-createfilew) öğesinde *dwDesiredAccess* öğesine bakın.

*dwShareMode*<br/>
Paylaşma modu. Bkz. *dwShareMode* `CreateFile` .

*dwCreationDisposition*<br/>
Oluşturma eğilimi. İçindeki *dwCreationDisposition* öğesine bakın `CreateFile` .

*dwFlagsAndAttributes*<br/>
Bayraklar ve öznitelikler. Bkz. *dwFlagsAndAttributes* ın `CreateFile` .

*lpsa*<br/>
Güvenlik öznitelikleri. İçindeki *lpSecurityAttributes* öğesine bakın `CreateFile` .

*hTemplateFile*<br/>
Şablon dosyası. İçindeki *HTemplateFile* bölümüne bakın `CreateFile` .

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Dosyayı oluşturmak veya açmak için [CreateFile](/windows/win32/api/fileapi/nf-fileapi-createfilew) öğesini çağırır.

## <a name="catlfileflush"></a><a name="flush"></a> CAtlFile:: Flush

Dosya için arabellekleri temizlemek ve tüm arabelleğe alınmış verilerin dosyaya yazılmasına neden olmak için bu yöntemi çağırın.

```cpp
HRESULT Flush() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Arabelleğe alınan verileri dosyaya temizlemek için [FlushFileBuffers](/windows/win32/api/fileapi/nf-fileapi-flushfilebuffers) çağırır.

## <a name="catlfilegetoverlappedresult"></a><a name="getoverlappedresult"></a> CAtlFile:: GetOverlappedResult

Dosyadaki bir çakışan işlemin sonuçlarını almak için bu yöntemi çağırın.

```cpp
HRESULT GetOverlappedResult(
    LPOVERLAPPED pOverlapped,
    DWORD& dwBytesTransferred,
    BOOL bWait) throw();
```

### <a name="parameters"></a>Parametreler

*Polatik*<br/>
Çakışan yapı. Windows SDK için bkz. [GetOverlappedResult](/windows/win32/api/ioapiset/nf-ioapiset-getoverlappedresult) Içindeki *Lpoverlafinresult* .

*dwBytesTransferred*<br/>
Aktarılan baytlar. Bkz. *lpNumberOfBytesTransferred* `GetOverlappedResult` .

*bWait*<br/>
Bekle seçeneği. Bkz. *Bwait* `GetOverlappedResult` .

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Dosyadaki bir çakışan işlemin sonuçlarını almak için [GetOverlappedResult](/windows/win32/api/ioapiset/nf-ioapiset-getoverlappedresult) öğesini çağırır.

## <a name="catlfilegetposition"></a><a name="getposition"></a> CAtlFile:: GetPosition

Geçerli dosya işaretçisi konumunu almak için bu yöntemi çağırın.

```cpp
HRESULT GetPosition(ULONGLONG& nPos) const throw();
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
Bayt cinsinden konum.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Geçerli dosya işaretçisi konumunu almak için [SetFilePointer](/windows/win32/api/fileapi/nf-fileapi-setfilepointer) çağırır.

## <a name="catlfilegetsize"></a><a name="getsize"></a> CAtlFile:: GetSize

Dosyanın bayt cinsinden boyutunu almak için bu yöntemi çağırın.

```cpp
HRESULT GetSize(ULONGLONG& nLen) const throw();
```

### <a name="parameters"></a>Parametreler

*nLen*<br/>
Dosyadaki bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Dosyanın bayt cinsinden boyutunu almak için [GetFileSize](/windows/win32/api/fileapi/nf-fileapi-getfilesize) çağırır.

## <a name="catlfilelockrange"></a><a name="lockrange"></a> CAtlFile:: LockRange

Diğer işlemlerin bu işleme erişmesini engellemek için dosyadaki bir bölgeyi kilitlemek üzere bu yöntemi çağırın.

```cpp
HRESULT LockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
Dosyadaki kilidin başlayacağı konum.

*nCount*<br/>
Kilitlenecek bayt aralığının uzunluğu.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Dosyadaki bir bölgeyi kilitlemek için [LockFile](/windows/win32/api/fileapi/nf-fileapi-lockfile) çağırır. Bir dosyadaki kilitleme baytları diğer işlemlere göre bu baytlara erişimi engeller. Bir dosyanın birden fazla bölgesini kilitleyebilmeniz, ancak çakışan bölgelere izin verilmez. Bir bölgenin kilidini açarken, [CAtlFile:: UnlockRange](#unlockrange)kullanarak, bayt aralığı tam olarak kilitlenen bölgeye karşılık gelmelidir. `LockRange` bitişik bölgeleri birleştirmez; iki kilitli bölge bitişik ise, her birinin kilidini ayrı olarak açmanız gerekir.

## <a name="catlfilem_ptm"></a><a name="m_ptm"></a> CAtlFile:: m_pTM

Bir nesne işaretçisi `CAtlTransactionManager` .

```cpp
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>Açıklamalar

## <a name="catlfileread"></a><a name="read"></a> CAtlFile:: Read

Dosya işaretçisi tarafından belirtilen konumdan başlayarak bir dosyadaki verileri okumak için bu yöntemi çağırın.

```cpp
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
Dosyadan okunan verileri alacak olan arabelleğin işaretçisi.

*nBufSize*<br/>
Bayt cinsinden arabellek boyutu.

*nBytesRead*<br/>
Okunan bayt sayısı.

*Polatik*<br/>
Çakışan yapı. Windows SDK için bkz. [ReadFile](/windows/win32/api/fileapi/nf-fileapi-readfile) Içinde *Lpoverladın* .

*pfnCompletionRoutine*<br/>
Tamamlama yordamı. Windows SDK [ReadFileEx](/windows/win32/api/fileapi/nf-fileapi-readfileex) Içindeki *lpcompletionroutine* bölümüne bakın.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

İlk üç form [ReadFile](/windows/win32/api/fileapi/nf-fileapi-readfile)çağırır, son [ReadFileEx](/windows/win32/api/fileapi/nf-fileapi-readfileex) , dosyadaki verileri okur. Dosya işaretçisini taşımak için [CAtlFile:: Seek](#seek) kullanın.

## <a name="catlfileseek"></a><a name="seek"></a> CAtlFile:: Seek

Dosyanın dosya işaretçisini taşımak için bu yöntemi çağırın.

```cpp
HRESULT Seek(
    LONGLONG nOffset,
    DWORD dwFrom = FILE_CURRENT) throw();
```

### <a name="parameters"></a>Parametreler

*nKonum*<br/>
*DwFrom* tarafından verilen başlangıç noktasından olan fark.

*dwFrom*<br/>
Başlangıç noktası (FILE_BEGIN, FILE_CURRENT veya FILE_END).

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Dosya işaretçisini taşımak için [SetFilePointer](/windows/win32/api/fileapi/nf-fileapi-setfilepointer) çağırır.

## <a name="catlfilesetsize"></a><a name="setsize"></a> CAtlFile:: SetSize

Dosyanın boyutunu ayarlamak için bu yöntemi çağırın.

```cpp
HRESULT SetSize(ULONGLONG nNewLen) throw();
```

### <a name="parameters"></a>Parametreler

*nNewLen*<br/>
Dosyanın bayt cinsinden yeni uzunluğu.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Dosya boyutunu ayarlamak için [SetFilePointer](/windows/win32/api/fileapi/nf-fileapi-setfilepointer) ve [SetEndOfFile](/windows/win32/api/fileapi/nf-fileapi-setendoffile) öğesini çağırır. Dönüş sırasında dosya işaretçisi dosyanın sonuna yerleştirilir.

## <a name="catlfileunlockrange"></a><a name="unlockrange"></a> CAtlFile:: UnlockRange

Dosyanın bir bölgesinin kilidini açmak için bu yöntemi çağırın.

```cpp
HRESULT UnlockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
Dosyadaki kilidinin başlayacağı konum.

*nCount*<br/>
Kilidinin açılacağı bayt aralığının uzunluğu.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Dosyanın bir bölgesinin kilidini açmak için [UnlockFile](/windows/win32/api/fileapi/nf-fileapi-unlockfile) öğesini çağırır.

## <a name="catlfilewrite"></a><a name="write"></a> CAtlFile:: Write

Dosya işaretçisi tarafından belirtilen konumdan başlayarak dosyaya veri yazmak için bu yöntemi çağırın.

```cpp
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
Dosyaya yazılacak verileri içeren arabellek.

*nBufSize*<br/>
Arabellekten aktarılacak bayt sayısı.

*Polatik*<br/>
Çakışan yapı. Windows SDK için bkz. [WriteFile](/windows/win32/api/fileapi/nf-fileapi-writefile) 'de *Lpoverladın* .

*pfnCompletionRoutine*<br/>
Tamamlama yordamı. Windows SDK, [WriteFileEx](/windows/win32/api/fileapi/nf-fileapi-writefileex) Içindeki *lpcompletionroutine* bölümüne bakın.

*pnBytesWritten*<br/>
Yazılan bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

İlk üç form [WriteFile](/windows/win32/api/fileapi/nf-fileapi-writefile)çağrısı, son, dosyadaki verileri yazmak Için [WriteFileEx](/windows/win32/api/fileapi/nf-fileapi-writefileex) öğesini çağırır. Dosya işaretçisini taşımak için [CAtlFile:: Seek](#seek) kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Kayan yazı örneği](../../overview/visual-cpp-samples.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[CHandle sınıfı](../../atl/reference/chandle-class.md)
