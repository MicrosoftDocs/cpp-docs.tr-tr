---
title: CAtlFile sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CAtlFile class
ms.assetid: 93ed160b-af2a-448c-9cbe-e5fa46c199bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 43ee71aae842ca7100f70af67cd8845d31e39a96
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="catlfile-class"></a>CAtlFile sınıfı
Bu sınıf Windows çevresinde ince bir sarmalayıcı dosya işleme API sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
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
|[CAtlFile::Create](#create)|Oluşturmak veya bir dosyayı açmak için bu yöntemi çağırın.|  
|[CAtlFile::Flush](#flush)|Dosya için arabellek temizleyip dosyasına yazılacak olan tüm arabelleğe alınan verilerin neden için bu yöntemi çağırın.|  
|[CAtlFile::GetOverlappedResult](#getoverlappedresult)|Dosya çakışan bir işlem sonuçları almak için bu yöntemi çağırın.|  
|[CAtlFile::GetPosition](#getposition)|Geçerli dosya işaretçisini konumu dosyadan almak için bu yöntemi çağırın.|  
|[CAtlFile::GetSize](#getsize)|Dosyanın bayt cinsinden boyutu almak için bu yöntemi çağırın.|  
|[CAtlFile::LockRange](#lockrange)|Bir bölgede başka bir işlem, erişimini engellemek için dosyayı kilitlemek için bu yöntemi çağırın.|  
|[CAtlFile::Read](#read)|Dosya işaretçisini tarafından belirtilen konumda başlayarak bir dosyadan verileri okumak için bu yöntemi çağırın.|  
|[CAtlFile::Seek](#seek)|Dosyanın dosya işaretçisini taşımak için bu yöntemi çağırın.|  
|[CAtlFile::SetSize](#setsize)|Dosyanın boyutunu ayarlamak için bu yöntemi çağırın.|  
|[CAtlFile::UnlockRange](#unlockrange)|Bir bölge dosyanın kilidini açmak için bu yöntemi çağırın.|  
|[CAtlFile::Write](#write)|Dosya işaretçisini tarafından belirtilen konumda başlayan dosya verileri yazmak için bu yöntemi çağırın.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlFile::m_pTM](#m_ptm)|İşaretçi `CAtlTransactionManager` nesnesi|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf, dosya işleme gereksinimlerini görece basit ancak MFC bağımlılıklar dahil olmak üzere olmadan Windows API sağladığından daha fazla soyutlama gerekli olduğu durumlarda kullanın.  
  
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
 `file`  
 Dosya nesnesi.  
  
 `hFile`  
 Dosya tanıtıcısı.  
  
 `pTM`  
 CAtlTransactionManager nesnesine işaretçi  
  
### <a name="remarks"></a>Açıklamalar  
 Kopya Oluşturucu özgün dosya tanıtıcısı sahipliğini aktarır `CAtlFile` yeni oluşturulan nesnesini.  
  
##  <a name="create"></a>  CAtlFile::Create  
 Oluşturmak veya bir dosyayı açmak için bu yöntemi çağırın.  
  
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
 *szFilename*  
 Dosya adı.  
  
 `dwDesiredAccess`  
 İstenen erişim. Bkz: `dwDesiredAccess` içinde [CreateFile](http://msdn.microsoft.com/library/windows/desktop/aa363858) Windows SDK.  
  
 `dwShareMode`  
 Paylaşım modu. Bkz: `dwShareMode` içinde **CreateFile**.  
  
 `dwCreationDisposition`  
 Oluşturma değerlendirme. Bkz: `dwCreationDisposition` içinde **CreateFile**.  
  
 `dwFlagsAndAttributes`  
 Bayrakları ve öznitelikleri. Bkz: `dwFlagsAndAttributes` içinde **CreateFile**.  
  
 `lpsa`  
 Güvenlik öznitelikleri. Bkz: *lpSecurityAttributes* içinde **CreateFile**.  
  
 `hTemplateFile`  
 Şablon dosyası. Bkz: `hTemplateFile` içinde **CreateFile**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK` başarı veya hata `HRESULT` hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrıları [CreateFile](http://msdn.microsoft.com/library/windows/desktop/aa363858) oluşturmak veya dosyayı açmak için.  
  
##  <a name="flush"></a>  CAtlFile::Flush  
 Dosya için arabellek temizleyip dosyasına yazılacak olan tüm arabelleğe alınan verilerin neden için bu yöntemi çağırın.  
  
```
HRESULT Flush() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK` başarı veya hata `HRESULT` hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrıları [FlushFileBuffers](http://msdn.microsoft.com/library/windows/desktop/aa364439) dosyayı arabelleğe alınan verileri temizlemek için.  
  
##  <a name="getoverlappedresult"></a>  CAtlFile::GetOverlappedResult  
 Dosya çakışan bir işlem sonuçları almak için bu yöntemi çağırın.  
  
```
HRESULT GetOverlappedResult(
    LPOVERLAPPED pOverlapped,
    DWORD& dwBytesTransferred,
    BOOL bWait) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pOverlapped`  
 Çakışan yapısı. Bkz: `lpOverlapped` içinde [GetOverlappedResult](http://msdn.microsoft.com/library/windows/desktop/ms683209) Windows SDK.  
  
 *dwBytesTransferred*  
 Aktarılan bayt sayısı. Bkz: *lpNumberOfBytesTransferred* içinde `GetOverlappedResult`.  
  
 `bWait`  
 Bekleme seçeneği. Bkz: `bWait` içinde `GetOverlappedResult`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK` başarı veya hata `HRESULT` hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrıları [GetOverlappedResult](http://msdn.microsoft.com/library/windows/desktop/ms683209) dosyasında çakışan bir işlem sonuçları elde etmek için.  
  
##  <a name="getposition"></a>  CAtlFile::GetPosition  
 Geçerli dosya işaretçisini konumunu almak için bu yöntemi çağırın.  
  
```
HRESULT GetPosition(ULONGLONG& nPos) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nPos`  
 Bayt konumu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK` başarı veya hata `HRESULT` hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrıları [SetFilePointer](http://msdn.microsoft.com/library/windows/desktop/aa365541) geçerli dosya işaretçisini konumunu almak için.  
  
##  <a name="getsize"></a>  CAtlFile::GetSize  
 Dosyanın bayt cinsinden boyutu almak için bu yöntemi çağırın.  
  
```
HRESULT GetSize(ULONGLONG& nLen) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nLen`  
 Dosyanın bayt sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK` başarı veya hata `HRESULT` hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrıları [GetFileSize](http://msdn.microsoft.com/library/windows/desktop/aa364955) dosyasının bayt cinsinden boyutu alınamıyor.  
  
##  <a name="lockrange"></a>  CAtlFile::LockRange  
 Bir bölgede başka bir işlem, erişimini engellemek için dosyayı kilitlemek için bu yöntemi çağırın.  
  
```
HRESULT LockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nPos`  
 Kilit nerede başlaması gerektiğini dosyanın konumu.  
  
 `nCount`  
 Kilitlenecek bayt aralığı uzunluğu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK` başarı veya hata `HRESULT` hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrıları [LockFile](http://msdn.microsoft.com/library/windows/desktop/aa365202) dosyayı bir bölgede kilitlenemiyor. Bir dosyada baytları kilitleme erişimi başka işlemler tarafından bu bayt engeller. Bir dosyanın birden fazla bölge kilitleyebilirsiniz ancak hiç çakışan bölge izin verilir. Bir bölge kilidini kullandığınızda [CAtlFile::UnlockRange](#unlockrange), bayt aralığı önceden kilitli olan bölge tam olarak eşleşmelidir. `LockRange` bitişik bölgeler birleştirmez; iki kilitli bölgeler bitişikse, her ayrı olarak kilidini açmanız gerekir.  
  
##  <a name="m_ptm"></a>  CAtlFile::m_pTM  
 İşaretçi bir `CAtlTransactionManager` nesnesi.  
  
```
CAtlTransactionManager* m_pTM;
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="read"></a>  CAtlFile::Read  
 Dosya işaretçisini tarafından belirtilen konumda başlayarak bir dosyadan verileri okumak için bu yöntemi çağırın.  
  
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
 `pBuffer`  
 Dosyadan okunan veriler alacak arabellek işaretçi.  
  
 `nBufSize`  
 Bayt cinsinden arabellek boyutu.  
  
 `nBytesRead`  
 Okunan bayt sayısı.  
  
 `pOverlapped`  
 Çakışan yapısı. Bkz: `lpOverlapped` içinde [ReadFile](http://msdn.microsoft.com/library/windows/desktop/aa365467) Windows SDK.  
  
 `pfnCompletionRoutine`  
 Tamamlama yordamı. Bkz: *lpCompletionRoutine* içinde [ReadFileEx](http://msdn.microsoft.com/library/windows/desktop/aa365468) Windows SDK'sındaki.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK` başarı veya hata `HRESULT` hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk üç forms çağrısı [ReadFile](http://msdn.microsoft.com/library/windows/desktop/aa365467), son [ReadFileEx](http://msdn.microsoft.com/library/windows/desktop/aa365468) dosyasından veri okunamıyor. Kullanım [CAtlFile::Seek](#seek) dosya işaretçisini taşımak için.  
  
##  <a name="seek"></a>  CAtlFile::Seek  
 Dosyanın dosya işaretçisini taşımak için bu yöntemi çağırın.  
  
```
HRESULT Seek(
    LONGLONG nOffset,
    DWORD dwFrom = FILE_CURRENT) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nOffset`  
 Başlangıç noktası tarafından verilen uzaklığı `dwFrom`.  
  
 `dwFrom`  
 Başlangıç noktası (FILE_BEGIN, FILE_CURRENT veya FILE_END).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK` başarı veya hata `HRESULT` hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrıları [SetFilePointer](http://msdn.microsoft.com/library/windows/desktop/aa365541) dosya işaretçisini taşımak için.  
  
##  <a name="setsize"></a>  CAtlFile::SetSize  
 Dosyanın boyutunu ayarlamak için bu yöntemi çağırın.  
  
```
HRESULT SetSize(ULONGLONG nNewLen) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nNewLen`  
 Yeni dosyanın bayt cinsinden uzunluğu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK` başarı veya hata `HRESULT` hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrıları [SetFilePointer](http://msdn.microsoft.com/library/windows/desktop/aa365541) ve [SetEndOfFile](http://msdn.microsoft.com/library/windows/desktop/aa365531) dosyasının boyutunu ayarlamak için. Getirisi, dosya işaretçisini dosyanın sonunda konumlandırıldı.  
  
##  <a name="unlockrange"></a>  CAtlFile::UnlockRange  
 Bir bölge dosyanın kilidini açmak için bu yöntemi çağırın.  
  
```
HRESULT UnlockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nPos`  
 Unlock nerede başlaması gerektiğini dosyanın konumu.  
  
 `nCount`  
 Kilidi açılacak bayt aralığı uzunluğu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK` başarı veya hata `HRESULT` hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrıları [UnlockFile](http://msdn.microsoft.com/library/windows/desktop/aa365715) bir bölge dosyanın kilidini açmak için.  
  
##  <a name="write"></a>  CAtlFile::Write  
 Dosya işaretçisini tarafından belirtilen konumda başlayan dosya verileri yazmak için bu yöntemi çağırın.  
  
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
 `pBuffer`  
 Dosyasına yazılacak veriler içeren bir arabellek.  
  
 `nBufSize`  
 Arabellekteki aktarılacak bayt sayısı.  
  
 `pOverlapped`  
 Çakışan yapısı. Bkz: `lpOverlapped` içinde [WriteFile](http://msdn.microsoft.com/library/windows/desktop/aa365747) Windows SDK.  
  
 `pfnCompletionRoutine`  
 Tamamlama yordamı. Bkz: *lpCompletionRoutine* içinde [WriteFileEx](http://msdn.microsoft.com/library/windows/desktop/aa365748) Windows SDK'sındaki.  
  
 `pnBytesWritten`  
 Yazılan bayt sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK` başarı veya hata `HRESULT` hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk üç forms çağrısı [WriteFile](http://msdn.microsoft.com/library/windows/desktop/aa365747), son çağrıları [WriteFileEx](http://msdn.microsoft.com/library/windows/desktop/aa365748) dosyaya veri yazmak için. Kullanım [CAtlFile::Seek](#seek) dosya işaretçisini taşımak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayan örnek](../../visual-cpp-samples.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)   
 [CHandle Sınıfı](../../atl/reference/chandle-class.md)
