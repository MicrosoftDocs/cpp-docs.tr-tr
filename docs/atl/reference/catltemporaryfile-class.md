---
title: "CAtlTemporaryFile sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlTemporaryFile
- ATLFILE/ATL::CAtlTemporaryFile
- ATLFILE/ATL::CAtlTemporaryFile::CAtlTemporaryFile
- ATLFILE/ATL::CAtlTemporaryFile::Close
- ATLFILE/ATL::CAtlTemporaryFile::Create
- ATLFILE/ATL::CAtlTemporaryFile::Flush
- ATLFILE/ATL::CAtlTemporaryFile::GetPosition
- ATLFILE/ATL::CAtlTemporaryFile::GetSize
- ATLFILE/ATL::CAtlTemporaryFile::HandsOff
- ATLFILE/ATL::CAtlTemporaryFile::HandsOn
- ATLFILE/ATL::CAtlTemporaryFile::LockRange
- ATLFILE/ATL::CAtlTemporaryFile::Read
- ATLFILE/ATL::CAtlTemporaryFile::Seek
- ATLFILE/ATL::CAtlTemporaryFile::SetSize
- ATLFILE/ATL::CAtlTemporaryFile::TempFileName
- ATLFILE/ATL::CAtlTemporaryFile::UnlockRange
- ATLFILE/ATL::CAtlTemporaryFile::Write
dev_langs: C++
helpviewer_keywords: CAtlTemporaryFile class
ms.assetid: 05f0f2a5-94f6-4594-8dae-b114292ff5f9
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5911de856d13d9d66e8c950d446083a36811f535
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="catltemporaryfile-class"></a>CAtlTemporaryFile sınıfı
Bu sınıf, oluşturma ve geçici bir dosya kullanımı için yöntemleri sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CAtlTemporaryFile
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)|Oluşturucu.|  
|[CAtlTemporaryFile:: ~ CAtlTemporaryFile](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlTemporaryFile::Close](#close)|Geçici bir dosya kapatmak için bu yöntemi çağırın ve ya da içeriğini silin veya belirtilen dosya adıyla depolar.|  
|[CAtlTemporaryFile::Create](#create)|Geçici bir dosya oluşturmak için bu yöntemi çağırın.|  
|[CAtlTemporaryFile::Flush](#flush)|Geçici dosyasına yazılacak olan dosya arabelleği kalan herhangi bir veri zorlamak için bu yöntemi çağırın.|  
|[CAtlTemporaryFile::GetPosition](#getposition)|Geçerli dosya işaretçisini konumunu almak için bu yöntemi çağırın.|  
|[CAtlTemporaryFile::GetSize](#getsize)|Geçici dosya bayt cinsinden boyutu almak için bu yöntemi çağırın.|  
|[CAtlTemporaryFile::HandsOff](#handsoff)|Dosyadan ilişkisini kaldırmak için bu yöntemi çağırın `CAtlTemporaryFile` nesnesi.|  
|[CAtlTemporaryFile::HandsOn](#handson)|Mevcut bir geçici dosyasını açın ve dosyanın sonunda işaretçiyi için bu yöntemi çağırın.|  
|[CAtlTemporaryFile::LockRange](#lockrange)|Bir bölgede başka bir işlem, erişimini engellemek için dosyayı kilitlemek için bu yöntemi çağırın.|  
|[CAtlTemporaryFile::Read](#read)|Dosya işaretçisini tarafından belirtilen konumda başlayarak geçici dosya verilerini okumak için bu yöntemi çağırın.|  
|[CAtlTemporaryFile::Seek](#seek)|Dosya işaretçisini geçici dosyasının taşımak için bu yöntemi çağırın.|  
|[CAtlTemporaryFile::SetSize](#setsize)|Geçici dosya boyutunu ayarlamak için bu yöntemi çağırın.|  
|[CAtlTemporaryFile::TempFileName](#tempfilename)|Geçici dosya adını döndürmek için bu yöntemi çağırın.|  
|[CAtlTemporaryFile::UnlockRange](#unlockrange)|Bir bölge geçici dosyanın kilidini açmak için bu yöntemi çağırın.|  
|[CAtlTemporaryFile::Write](#write)|Dosya işaretçisini tarafından belirtilen konumda başlayarak geçici dosya verileri yazmak için bu yöntemi çağırın.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlTemporaryFile::operator TANITICISI](#operator_handle)|Geçici dosya için bir işleyici döner.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CAtlTemporaryFile`geçici dosyası oluşturma ve kullanma daha kolay hale getirir. Dosya otomatik olarak adlandırılan, açılan, silinmiş ve kapatılır. Dosyanın kapatıldıktan sonra dosya içeriğini gerekirse, belirtilen ada sahip yeni bir dosyaya kaydedilebilir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlfile.h  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).  
  
##  <a name="catltemporaryfile"></a>CAtlTemporaryFile::CAtlTemporaryFile  
 Oluşturucu.  
  
```
CAtlTemporaryFile() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir dosya için bir çağrı yapılır kadar gerçekte açılmadı [CAtlTemporaryFile::Create](#create).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#73](../../atl/codesnippet/cpp/catltemporaryfile-class_1.cpp)]  
  
##  <a name="dtor"></a>CAtlTemporaryFile:: ~ CAtlTemporaryFile  
 Yok Edicisi.  
  
```
~CAtlTemporaryFile() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yıkıcı çağrıları [CAtlTemporaryFile::Close](#close).  
  
##  <a name="close"></a>CAtlTemporaryFile::Close  
 Geçici bir dosya kapatmak için bu yöntemi çağırın ve ya da içeriğini silin veya belirtilen dosya adıyla depolar.  
  
```
HRESULT Close(LPCTSTR szNewName = NULL) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *szNewName*  
 Geçici dosya içeriğini depolamak için yeni dosya adı. Bu bağımsız değişken NULL ise, geçici dosyasının içeriği silinir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK` başarı veya hata `HRESULT` hatasında.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).  
  
##  <a name="create"></a>CAtlTemporaryFile::Create  
 Geçici bir dosya oluşturmak için bu yöntemi çağırın.  
  
```
HRESULT Create(LPCTSTR pszDir = NULL, DWORD dwDesiredAccess = GENERIC_WRITE) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pszDir`  
 Geçici dosya yolu. Bu NULL ise [GetTempPath](http://msdn.microsoft.com/library/windows/desktop/aa364992) bir yol atamak için çağrılır.  
  
 `dwDesiredAccess`  
 İstenen erişim. Bkz: `dwDesiredAccess` içinde [CreateFile](http://msdn.microsoft.com/library/windows/desktop/aa363858) Windows SDK.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK` başarı veya hata `HRESULT` hatasında.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).  
  
##  <a name="flush"></a>CAtlTemporaryFile::Flush  
 Geçici dosyasına yazılacak olan dosya arabelleği kalan herhangi bir veri zorlamak için bu yöntemi çağırın.  
  
```
HRESULT Flush() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK` başarı veya hata `HRESULT` hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 Benzer şekilde [CAtlTemporaryFile::HandsOff](#handsoff), dosya kapatılmadı dışında.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).  
  
##  <a name="getposition"></a>CAtlTemporaryFile::GetPosition  
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
 Dosya işaretçisini konumu değiştirmek için kullanın [CAtlTemporaryFile::Seek](#seek).  
  
##  <a name="getsize"></a>CAtlTemporaryFile::GetSize  
 Geçici dosya bayt cinsinden boyutu almak için bu yöntemi çağırın.  
  
```
HRESULT GetSize(ULONGLONG& nLen) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nLen`  
 Dosyanın bayt sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK` başarı veya hata `HRESULT` hatasında.  
  
##  <a name="handsoff"></a>CAtlTemporaryFile::HandsOff  
 Dosyadan ilişkisini kaldırmak için bu yöntemi çağırın `CAtlTemporaryFile` nesnesi.  
  
```
HRESULT HandsOff() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK` başarı veya hata `HRESULT` hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 `HandsOff`ve [CAtlTemporaryFile::HandsOn](#handson) nesne dosyanın ilişkisini kaldırın ve gerekirse yeniden için kullanılır. `HandsOff`geçici dosyasına yazılacak olan dosya arabelleği kalan herhangi bir veri zorlamak ve dosyayı kaydedip kapatın. Kapatın ve dosyayı kalıcı olarak silmek istiyorsanız veya kapatmak ve belirli bir ada sahip dosyasının içeriği korumak için kullanmak istiyorsanız, [CAtlTemporaryFile::Close](#close).  
  
##  <a name="handson"></a>CAtlTemporaryFile::HandsOn  
 Mevcut bir geçici dosyasını açın ve dosyanın sonunda işaretçiyi için bu yöntemi çağırın.  
  
```
HRESULT HandsOn() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK` başarı veya hata `HRESULT` hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 [CAtlTemporaryFile::HandsOff](#handsoff) ve `HandsOn` nesne dosyanın ilişkisini kaldırın ve gerekirse yeniden için kullanılır.  
  
##  <a name="lockrange"></a>CAtlTemporaryFile::LockRange  
 Bir bölgede başka bir işlem, erişimini önlemek için geçici dosyayı kilitlemek için bu yöntemi çağırın.  
  
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
 Bir dosyada baytları kilitleme erişimi başka işlemler tarafından bu bayt engeller. Bir dosyanın birden fazla bölge kilitleyebilirsiniz ancak hiç çakışan bölge izin verilir. Başarıyla bir bölge kilidini açmak için kullanmak [CAtlTemporaryFile::UnlockRange](#unlockrange), karşılık gelen daha önce kilitli olan bölge tam olarak bayt aralığı sağlama. `LockRange`bitişik bölgeler birleştirmez; iki kilitli bölgeler bitişikse, her ayrı olarak kilidini açmanız gerekir.  
  
##  <a name="operator_handle"></a>CAtlTemporaryFile::operator TANITICISI  
 Geçici dosya için bir işleyici döner.  
  
```  
operator HANDLE() throw();
```  
  
##  <a name="read"></a>CAtlTemporaryFile::Read  
 Dosya işaretçisini tarafından belirtilen konumda başlayarak geçici dosya verilerini okumak için bu yöntemi çağırın.  
  
```
HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    DWORD& nBytesRead) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pBuffer`  
 Dosyadan okunan veriler alacak arabellek işaretçi.  
  
 `nBufSize`  
 Bayt cinsinden arabellek boyutu.  
  
 `nBytesRead`  
 Okunan bayt sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK` başarı veya hata `HRESULT` hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrıları [CAtlFile::Read](../../atl/reference/catlfile-class.md#read). Dosya işaretçisini konumunu değiştirmek için çağrı [CAtlTemporaryFile::Seek](#seek).  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).  
  
##  <a name="seek"></a>CAtlTemporaryFile::Seek  
 Dosya işaretçisini geçici dosyasının taşımak için bu yöntemi çağırın.  
  
```
HRESULT Seek(LONGLONG nOffset, DWORD dwFrom = FILE_CURRENT) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nOffset`  
 Tarafından verilen başlangıç noktasından bayt cinsinden uzaklık *dwFrom.*  
  
 `dwFrom`  
 Başlangıç noktası (FILE_BEGIN, FILE_CURRENT veya FILE_END).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK` başarı veya hata `HRESULT` hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrıları [CAtlFile::Seek](../../atl/reference/catlfile-class.md#seek). Geçerli dosya işaretçisini konumu elde etmek için arama [CAtlTemporaryFile::GetPosition](#getposition).  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).  
  
##  <a name="setsize"></a>CAtlTemporaryFile::SetSize  
 Geçici dosya boyutunu ayarlamak için bu yöntemi çağırın.  
  
```
HRESULT SetSize(ULONGLONG nNewLen) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nNewLen`  
 Yeni dosyanın bayt cinsinden uzunluğu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK` başarı veya hata `HRESULT` hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrıları [CAtlFile::SetSize](../../atl/reference/catlfile-class.md#setsize). Getirisi, dosya işaretçisini dosyanın sonunda konumlandırıldı.  
  
##  <a name="tempfilename"></a>CAtlTemporaryFile::TempFileName  
 Geçici dosya adını döndürmek için bu yöntemi çağırın.  
  
```
LPCTSTR TempFileName() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `LPCTSTR` dosya adına işaret eden.  
  
### <a name="remarks"></a>Açıklamalar  
 Dosya adı üretildi [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile) çağrısıyla [GetTempFile](http://msdn.microsoft.com/library/windows/desktop/aa364991)Windows SDK işlevi. Dosya uzantısı için geçici dosyayı her zaman "TFR" olur.  
  
##  <a name="unlockrange"></a>CAtlTemporaryFile::UnlockRange  
 Bir bölge geçici dosyanın kilidini açmak için bu yöntemi çağırın.  
  
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
 Çağrıları [CAtlFile::UnlockRange](../../atl/reference/catlfile-class.md#unlockrange).  
  
##  <a name="write"></a>CAtlTemporaryFile::Write  
 Dosya işaretçisini tarafından belirtilen konumda başlayarak geçici dosya verileri yazmak için bu yöntemi çağırın.  
  
```
HRESULT Write(  
    LPCVOID pBuffer,
    DWORD nBufSize,
    DWORD* pnBytesWritten = NULL) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pBuffer`  
 Dosyasına yazılacak veriler içeren bir arabellek.  
  
 `nBufSize`  
 Arabellekteki aktarılacak bayt sayısı.  
  
 `pnBytesWritten`  
 Yazılan bayt sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK` başarı veya hata `HRESULT` hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrıları [CAtlFile::Write](../../atl/reference/catlfile-class.md#write).  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)   
 [CAtlFile Sınıfı](../../atl/reference/catlfile-class.md)
