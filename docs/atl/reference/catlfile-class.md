---
title: CAtlFile Sınıfı
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
ms.openlocfilehash: 39f323874ccde5178722235b9beb34c2572407a1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318970"
---
# <a name="catlfile-class"></a>CAtlFile Sınıfı

Bu sınıf, Windows dosya işleme API etrafında ince bir sarıcı sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CAtlFile : public CHandle
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAtlFile::CAtlFile](#catlfile)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAtlFile::Oluştur](#create)|Bir dosya oluşturmak veya açmak için bu yöntemi arayın.|
|[CAtlFile::Flush](#flush)|Dosyanın arabelleklerini temizlemek ve arabelleğe alınan tüm verilerin dosyaya yazılmasına neden olmak için bu yöntemi arayın.|
|[CAtlFile::GetOverlappedResult](#getoverlappedresult)|Dosyada çakışan bir işlemin sonuçlarını almak için bu yöntemi arayın.|
|[CAtlFile::GetPosition](#getposition)|Geçerli dosya işaretçisi konumunu dosyadan almak için bu yöntemi arayın.|
|[CAtlFile::GetSize](#getsize)|Dosyanın baytboyutu almak için bu yöntemi arayın.|
|[CAtlFile::LockRange](#lockrange)|Diğer işlemlerin dosyaya erişmesini önlemek için dosyadaki bir bölgeyi kilitlemek için bu yöntemi çağırın.|
|[CAtlFile::Oku](#read)|Dosya işaretçisi tarafından belirtilen konumdan başlayan bir dosyadan verileri okumak için bu yöntemi arayın.|
|[CAtlFile::Ara](#seek)|Dosya işaretçisini taşımak için bu yöntemi çağırın.|
|[CAtlFile::SetSize](#setsize)|Dosyanın boyutunu ayarlamak için bu yöntemi arayın.|
|[CAtlFile::UnlockRange](#unlockrange)|Dosyanın bir bölgesinin kilidini açmak için bu yöntemi arayın.|
|[CAtlFile::Yaz](#write)|Dosya işaretçisi tarafından belirtilen konumdan başlayarak dosyaya veri yazmak için bu yöntemi arayın.|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CAtlFile::m_pTM](#m_ptm)|Nesneye `CAtlTransactionManager` işaretçi|

## <a name="remarks"></a>Açıklamalar

Dosya işleme gereksinimleri nispeten basit olduğunda, ancak MFC bağımlılıkları dahil edilmeden Windows API'nin sağladığından daha fazla soyutlama gerektiğinde bu sınıfı kullanın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CHandle](../../atl/reference/chandle-class.md)

`CAtlFile`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlfile.h

## <a name="catlfilecatlfile"></a><a name="catlfile"></a>CAtlFile::CAtlFile

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

*hFile*<br/>
Dosya tutamacı.

*pTM*<br/>
CAtlTransactionManager nesnesine işaretçi

### <a name="remarks"></a>Açıklamalar

Kopya oluşturucu, dosya tanıtıcısının sahipliğini özgün `CAtlFile` nesneden yeni oluşturulan nesneye aktarAbilir.

## <a name="catlfilecreate"></a><a name="create"></a>CAtlFile::Oluştur

Bir dosya oluşturmak veya açmak için bu yöntemi arayın.

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

*szDosya adı*<br/>
Dosya adı.

*dwDesiredAccess*<br/>
İstenilen erişim. Windows SDK'daki [CreateFile'da](/windows/win32/api/fileapi/nf-fileapi-createfilew) *dwDesiredAccess'e* bakın.

*dwShareMode*<br/>
Paylaşım modu. Bkz. *dwShareMode* içinde `CreateFile`.

*dwCreationDisposition*<br/>
Yaratılış eğilimi. Bkz. *dwCreationDisposition* içinde `CreateFile`.

*dwFlagsAndAttributes*<br/>
Bayraklar ve öznitelikler. Bkz. *dwFlagsAndAttributes* içinde `CreateFile`.

*lpsa*<br/>
Güvenlik öznitelikleri. Bkz. *lpSecurityAttributes* içinde. `CreateFile`

*hTemplateFile*<br/>
Şablon dosyası. Bkz. *hTemplateFile* içinde `CreateFile`.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Dosyayı oluşturmak veya açmak için [CreateFile'ı](/windows/win32/api/fileapi/nf-fileapi-createfilew) çağırır.

## <a name="catlfileflush"></a><a name="flush"></a>CAtlFile::Flush

Dosyanın arabelleklerini temizlemek ve arabelleğe alınan tüm verilerin dosyaya yazılmasına neden olmak için bu yöntemi arayın.

```
HRESULT Flush() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Arabelleğe alınan verileri dosyaya yıkamak için [FlushFileBuffers'ı](/windows/win32/api/fileapi/nf-fileapi-flushfilebuffers) çağırır.

## <a name="catlfilegetoverlappedresult"></a><a name="getoverlappedresult"></a>CAtlFile::GetOverlappedResult

Dosyada çakışan bir işlemin sonuçlarını almak için bu yöntemi arayın.

```
HRESULT GetOverlappedResult(
    LPOVERLAPPED pOverlapped,
    DWORD& dwBytesTransferred,
    BOOL bWait) throw();
```

### <a name="parameters"></a>Parametreler

*pOverlapped*<br/>
Örtüşen yapı. Windows [SDK'da GetOverlappedResult'da](/windows/win32/api/ioapiset/nf-ioapiset-getoverlappedresult) *lpOverlapped'e* bakın.

*dwBytesTransfer*<br/>
Baytlar transfer edildi. Bkz. *lpNumberOfBytesTransfer* içinde `GetOverlappedResult`.

*bBekleyin*<br/>
Bekleme seçeneği. Bkz. *bWait* içinde `GetOverlappedResult`.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Dosyada üst üste bindirilen bir işlemin sonuçlarını almak için [GetOverlappedResult'ı](/windows/win32/api/ioapiset/nf-ioapiset-getoverlappedresult) arar.

## <a name="catlfilegetposition"></a><a name="getposition"></a>CAtlFile::GetPosition

Geçerli dosya işaretçisi konumunu almak için bu yöntemi arayın.

```
HRESULT GetPosition(ULONGLONG& nPos) const throw();
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
Baytpozisyonu.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Geçerli dosya işaretçisi konumunu almak için [SetFilePointer'ı](/windows/win32/api/fileapi/nf-fileapi-setfilepointer) çağırır.

## <a name="catlfilegetsize"></a><a name="getsize"></a>CAtlFile::GetSize

Dosyanın baytboyutu almak için bu yöntemi arayın.

```
HRESULT GetSize(ULONGLONG& nLen) const throw();
```

### <a name="parameters"></a>Parametreler

*nLen*<br/>
Dosyadaki bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Dosyanın baytlarında boyutu almak için [GetFileSize'ı](/windows/win32/api/fileapi/nf-fileapi-getfilesize) arar.

## <a name="catlfilelockrange"></a><a name="lockrange"></a>CAtlFile::LockRange

Diğer işlemlerin dosyaya erişmesini önlemek için dosyadaki bir bölgeyi kilitlemek için bu yöntemi çağırın.

```
HRESULT LockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
Kilitin başlaması gereken dosyadaki konum.

*nSayısı*<br/>
Kilitlenecek bayt aralığının uzunluğu.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

[Dosyadaki](/windows/win32/api/fileapi/nf-fileapi-lockfile) bir bölgeyi kilitlemek için Kilit Dosya'yı çağırır. Bir dosyadaki baytların kilitlenerek diğer işlemler tarafından bu baytlara erişimi engeller. Bir dosyanın birden fazla bölgesini kilitleyebilirsiniz, ancak çakışan bölgelere izin verilmez. [CAtlFile::UnlockRange](#unlockrange)kullanarak bir bölgenin kilidini açtığınızda, bayt aralığı daha önce kilitlenmiş olan bölgeye tam olarak karşılık vermelidir. `LockRange`bitişik bölgeleri birleştirmez; iki kilitli bölge bitişikse, her birinin kilidini ayrı ayrı açmanız gerekir.

## <a name="catlfilem_ptm"></a><a name="m_ptm"></a>CAtlFile::m_pTM

Bir `CAtlTransactionManager` nesneye işaretçi.

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>Açıklamalar

## <a name="catlfileread"></a><a name="read"></a>CAtlFile::Oku

Dosya işaretçisi tarafından belirtilen konumdan başlayan bir dosyadan verileri okumak için bu yöntemi arayın.

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

*Pbuffer*<br/>
Dosyadan okunan verileri alacak arabelleğe işaretçi.

*nBufSize*<br/>
Arabellek boyutu baytlar içinde.

*nBytesRead*<br/>
Okunan bayt sayısı.

*pOverlapped*<br/>
Örtüşen yapı. Windows SDK'da [ReadFile'da](/windows/win32/api/fileapi/nf-fileapi-readfile) *lpOverlapped'e* bakın.

*pfnCompletionRoutine*<br/>
Tamamlama rutini. Windows SDK'daki [ReadFileEx'teki](/windows/win32/api/fileapi/nf-fileapi-readfileex) *lpCompletionRoutine'e* bakın.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

İlk üç form [ReadFile'ı](/windows/win32/api/fileapi/nf-fileapi-readfile)arar, dosyadaki verileri okumak için son [ReadFileEx'i](/windows/win32/api/fileapi/nf-fileapi-readfileex) arar. [CAtlFile kullanın::Dosya](#seek) işaretçisini taşımak için arayın.

## <a name="catlfileseek"></a><a name="seek"></a>CAtlFile::Ara

Dosya işaretçisini taşımak için bu yöntemi çağırın.

```
HRESULT Seek(
    LONGLONG nOffset,
    DWORD dwFrom = FILE_CURRENT) throw();
```

### <a name="parameters"></a>Parametreler

*nOffset*<br/>
*dwFrom*tarafından verilen başlangıç noktasından mahsup .

*dwKaynak*<br/>
Başlangıç noktası (FILE_BEGIN, FILE_CURRENT veya FILE_END).

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Dosya işaretçisini taşımak için [SetFilePointer'ı](/windows/win32/api/fileapi/nf-fileapi-setfilepointer) çağırır.

## <a name="catlfilesetsize"></a><a name="setsize"></a>CAtlFile::SetSize

Dosyanın boyutunu ayarlamak için bu yöntemi arayın.

```
HRESULT SetSize(ULONGLONG nNewLen) throw();
```

### <a name="parameters"></a>Parametreler

*nNewLen*<br/>
Baytlar halindeki dosyanın yeni uzunluğu.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Dosyanın boyutunu ayarlamak için [SetFilePointer](/windows/win32/api/fileapi/nf-fileapi-setfilepointer) ve [SetEndOfFile'ı](/windows/win32/api/fileapi/nf-fileapi-setendoffile) arar. Döndükten sonra, dosya işaretçisi dosyanın sonuna konumlandırılır.

## <a name="catlfileunlockrange"></a><a name="unlockrange"></a>CAtlFile::UnlockRange

Dosyanın bir bölgesinin kilidini açmak için bu yöntemi arayın.

```
HRESULT UnlockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```

### <a name="parameters"></a>Parametreler

*nPos*<br/>
Dosyadaki kilidin başlaması gereken konum.

*nSayısı*<br/>
Kilidi açılacak bayt aralığının uzunluğu.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Dosyanın bir bölgesinin kilidini açmak için [UnlockFile'ı](/windows/win32/api/fileapi/nf-fileapi-unlockfile) arar.

## <a name="catlfilewrite"></a><a name="write"></a>CAtlFile::Yaz

Dosya işaretçisi tarafından belirtilen konumdan başlayarak dosyaya veri yazmak için bu yöntemi arayın.

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

*Pbuffer*<br/>
Dosyaya yazılacak verileri içeren arabellek.

*nBufSize*<br/>
Arabellekten aktarılacak bayt sayısı.

*pOverlapped*<br/>
Örtüşen yapı. Windows SDK'da [WriteFile'da](/windows/win32/api/fileapi/nf-fileapi-writefile) *lpOverlapped'e* bakın.

*pfnCompletionRoutine*<br/>
Tamamlama rutini. Windows SDK'daki [WriteFileEx'te](/windows/win32/api/fileapi/nf-fileapi-writefileex) *lpCompletionRoutine'e* bakın.

*pnBytesYazılı*<br/>
Baytlar yazılmış.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

İlk üç form [WriteFile'ı](/windows/win32/api/fileapi/nf-fileapi-writefile)arar, son aramalar [WriteFileEx](/windows/win32/api/fileapi/nf-fileapi-writefileex) dosyaya veri yazmak için. [CAtlFile kullanın::Dosya](#seek) işaretçisini taşımak için arayın.

## <a name="see-also"></a>Ayrıca bkz.

[Marquee Örnek](../../overview/visual-cpp-samples.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)<br/>
[CHandle Sınıfı](../../atl/reference/chandle-class.md)
