---
title: CAtlTemporaryFile sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
dev_langs:
- C++
helpviewer_keywords:
- CAtlTemporaryFile class
ms.assetid: 05f0f2a5-94f6-4594-8dae-b114292ff5f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c8d32094dd8ee55cdd76fc21f51a2f809b1b341d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46034934"
---
# <a name="catltemporaryfile-class"></a>CAtlTemporaryFile sınıfı

Bu sınıf, oluşturulmasını ve kullanımını geçici bir dosya için yöntemler sağlar.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CAtlTemporaryFile
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)|Oluşturucu.|
|[CAtlTemporaryFile:: ~ CAtlTemporaryFile](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAtlTemporaryFile::Close](#close)|Geçici bir dosya kapatmak için bu yöntemi çağırın ve ya da içeriğini silin veya bunları altında belirtilen dosya adı depolar.|
|[CAtlTemporaryFile::Create](#create)|Geçici bir dosya oluşturmak için bu yöntemi çağırın.|
|[CAtlTemporaryFile::Flush](#flush)|Geçici bir dosyaya yazılacak dosya arabelleğinde kalan herhangi bir veri zorlamak için bu yöntemi çağırın.|
|[CAtlTemporaryFile::GetPosition](#getposition)|Geçerli dosya işaretçisi konumunu almak için bu yöntemi çağırın.|
|[CAtlTemporaryFile::GetSize](#getsize)|Geçici dosya bir bayt cinsinden boyutunu almak için bu yöntemi çağırın.|
|[CAtlTemporaryFile::HandsOff](#handsoff)|Dosyadan ilişkisini kaldırmak için bu yöntemi çağırın `CAtlTemporaryFile` nesne.|
|[CAtlTemporaryFile::HandsOn](#handson)|Var olan geçici dosyasını açın ve dosyanın sonuna işaretçiyi için bu yöntemi çağırın.|
|[CAtlTemporaryFile::LockRange](#lockrange)|Diğer işlemlerin erişimini engellemek için dosyanın bir bölgede kilitlemek için bu yöntemi çağırın.|
|[CAtlTemporaryFile::Read](#read)|Dosya işaretçisi tarafından belirtilen konumda başlayarak geçici dosyadan veri okumak için bu yöntemi çağırın.|
|[CAtlTemporaryFile::Seek](#seek)|Geçici dosya, dosya işaretçisini taşımak için bu yöntemi çağırın.|
|[CAtlTemporaryFile::SetSize](#setsize)|Geçici dosya boyutunu ayarlamak için bu yöntemi çağırın.|
|[CAtlTemporaryFile::TempFileName](#tempfilename)|Geçici dosya adını döndürmek için bu yöntemi çağırın.|
|[CAtlTemporaryFile::UnlockRange](#unlockrange)|Bir bölge geçici dosyanın kilidini açmak için bu yöntemi çağırın.|
|[CAtlTemporaryFile::Write](#write)|Dosya işaretçisi tarafından belirtilen konumda başlayarak geçici dosya verileri yazmak için bu yöntemi çağırın.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CAtlTemporaryFile::operator TANITICISI](#operator_handle)|Geçici dosya için bir tanıtıcı döndürür.|

## <a name="remarks"></a>Açıklamalar

`CAtlTemporaryFile` geçici bir dosya oluşturup kullanacağınızı kolaylaştırır. Dosya otomatik olarak adlandırılmış, kapalı, silinen ve açıldı. Dosya kapatıldıktan sonra dosya içeriklerini gerekliyse, belirtilen ada sahip yeni bir dosyaya kaydedilebilir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlfile.h

## <a name="example"></a>Örnek

Örneğin bakın [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).

##  <a name="catltemporaryfile"></a>  CAtlTemporaryFile::CAtlTemporaryFile

Oluşturucu.

```
CAtlTemporaryFile() throw();
```

### <a name="remarks"></a>Açıklamalar

İçin bir çağrı yapılır kadar bir dosya gerçekten açılmadı [CAtlTemporaryFile::Create](#create).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#73](../../atl/codesnippet/cpp/catltemporaryfile-class_1.cpp)]

##  <a name="dtor"></a>  CAtlTemporaryFile:: ~ CAtlTemporaryFile

Yıkıcı.

```
~CAtlTemporaryFile() throw();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı çağrıları [CAtlTemporaryFile::Close](#close).

##  <a name="close"></a>  CAtlTemporaryFile::Close

Geçici bir dosya kapatmak için bu yöntemi çağırın ve ya da içeriğini silin veya bunları altında belirtilen dosya adı depolar.

```
HRESULT Close(LPCTSTR szNewName = NULL) throw();
```

### <a name="parameters"></a>Parametreler

*szNewName*<br/>
Geçici dosya içeriği depolamak yeni bir dosya adı. Bu bağımsız değişken NULL ise, geçici dosya içeriği silinir.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="example"></a>Örnek

Örneğin bakın [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).

##  <a name="create"></a>  CAtlTemporaryFile::Create

Geçici bir dosya oluşturmak için bu yöntemi çağırın.

```
HRESULT Create(LPCTSTR pszDir = NULL, DWORD dwDesiredAccess = GENERIC_WRITE) throw();
```

### <a name="parameters"></a>Parametreler

*pszDir*<br/>
Geçici dosya yolu. Bu, NULL ise [GetTempPath](/windows/desktop/api/fileapi/nf-fileapi-gettemppatha) yol atamak için çağrılır.

*dwDesiredAccess*<br/>
İstenen erişim. Bkz: *dwDesiredAccess* içinde [CreateFile](/windows/desktop/api/fileapi/nf-fileapi-createfilea) Windows SDK.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="example"></a>Örnek

Örneğin bakın [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).

##  <a name="flush"></a>  CAtlTemporaryFile::Flush

Geçici bir dosyaya yazılacak dosya arabelleğinde kalan herhangi bir veri zorlamak için bu yöntemi çağırın.

```
HRESULT Flush() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Benzer şekilde [CAtlTemporaryFile::HandsOff](#handsoff)dışında dosya kapatılmadı.

### <a name="example"></a>Örnek

Örneğin bakın [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).

##  <a name="getposition"></a>  CAtlTemporaryFile::GetPosition

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

Dosya işaretçisi konumunu değiştirmek için kullanın [CAtlTemporaryFile::Seek](#seek).

##  <a name="getsize"></a>  CAtlTemporaryFile::GetSize

Geçici dosya bir bayt cinsinden boyutunu almak için bu yöntemi çağırın.

```
HRESULT GetSize(ULONGLONG& nLen) const throw();
```

### <a name="parameters"></a>Parametreler

*nLen*<br/>
Dosyanın bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="handsoff"></a>  CAtlTemporaryFile::HandsOff

Dosyadan ilişkisini kaldırmak için bu yöntemi çağırın `CAtlTemporaryFile` nesne.

```
HRESULT HandsOff() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

`HandsOff` ve [CAtlTemporaryFile::HandsOn](#handson) dosyanın bir nesne ilişkisini keser ve gerekirse yeniden kullanılır. `HandsOff` , geçici bir dosyaya yazılacak dosya arabelleğinde kalan herhangi bir veri zorlamak ve dosyayı kaydedip kapatın. Kapatın ve dosyayı kalıcı olarak silmek isterseniz ya da kapatmak ve belirli bir ada sahip bir dosyanın içeriğini korumak kullanmak istediğiniz varsa [CAtlTemporaryFile::Close](#close).

##  <a name="handson"></a>  CAtlTemporaryFile::HandsOn

Var olan geçici dosyasını açın ve dosyanın sonuna işaretçiyi için bu yöntemi çağırın.

```
HRESULT HandsOn() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

[CAtlTemporaryFile::HandsOff](#handsoff) ve `HandsOn` dosyanın bir nesne ilişkisini keser ve gerekirse yeniden kullanılır.

##  <a name="lockrange"></a>  CAtlTemporaryFile::LockRange

Bir bölgede diğer işlemlerin erişimini önlemek için geçici dosya kilitleme için bu yöntemi çağırın.

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

Bir dosyadaki baytları kilitleme erişim için bu baytlardan başka işlemler tarafından engeller. Bir dosyanın birden fazla bölgeye kilitleyebilirsiniz ancak çakışan bölge izin verilir. Bir bölge başarıyla kilidini açmak için kullanmak [CAtlTemporaryFile::UnlockRange](#unlockrange), bayt aralığı sağlayarak daha önce kilitli olan bölge tam olarak karşılık gelir. `LockRange` bitişik bölgeleri birleştirmez; kilitli iki bölgeleri bitişikse, her ayrı olarak kilidini açmanız gerekir.

##  <a name="operator_handle"></a>  CAtlTemporaryFile::operator TANITICISI

Geçici dosya için bir tanıtıcı döndürür.

```
operator HANDLE() throw();
```

##  <a name="read"></a>  CAtlTemporaryFile::Read

Dosya işaretçisi tarafından belirtilen konumda başlayarak geçici dosyadan veri okumak için bu yöntemi çağırın.

```
HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    DWORD& nBytesRead) throw();
```

### <a name="parameters"></a>Parametreler

*pBuffer*<br/>
Dosyadan okunan veriler alacak arabellek için işaretçi.

*nBufSize*<br/>
Arabellek boyutu bayt cinsinden.

*nBytesRead*<br/>
Okunan bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Çağrıları [CAtlFile::Read](../../atl/reference/catlfile-class.md#read). Dosya işaretçisi konumunu değiştirmek için çağrı [CAtlTemporaryFile::Seek](#seek).

### <a name="example"></a>Örnek

Örneğin bakın [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).

##  <a name="seek"></a>  CAtlTemporaryFile::Seek

Geçici dosya, dosya işaretçisini taşımak için bu yöntemi çağırın.

```
HRESULT Seek(LONGLONG nOffset, DWORD dwFrom = FILE_CURRENT) throw();
```

### <a name="parameters"></a>Parametreler

*nOffset*<br/>
Başlangıç noktası tarafından verilen, bayt uzaklığı *dwFrom.*

*dwFrom*<br/>
Başlangıç noktası (FILE_BEGIN, FILE_CURRENT veya FILE_END).

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Çağrıları [CAtlFile::Seek](../../atl/reference/catlfile-class.md#seek). Geçerli dosya işaretçisi konumunu almak için çağrı [CAtlTemporaryFile::GetPosition](#getposition).

### <a name="example"></a>Örnek

Örneğin bakın [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).

##  <a name="setsize"></a>  CAtlTemporaryFile::SetSize

Geçici dosya boyutunu ayarlamak için bu yöntemi çağırın.

```
HRESULT SetSize(ULONGLONG nNewLen) throw();
```

### <a name="parameters"></a>Parametreler

*nNewLen*<br/>
Yeni dosyanın bayt cinsinden uzunluğu.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Çağrıları [CAtlFile::SetSize](../../atl/reference/catlfile-class.md#setsize). Getirisi, dosya işaretçisini dosyanın sonunda konumlandırıldı.

##  <a name="tempfilename"></a>  CAtlTemporaryFile::TempFileName

Geçici dosya adını döndürmek için bu yöntemi çağırın.

```
LPCTSTR TempFileName() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dosya adına işaret eden LPCTSTR döndürür.

### <a name="remarks"></a>Açıklamalar

Dosya adı içinde oluşturulan [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile) çağrısıyla [GetTempFile](/windows/desktop/api/fileapi/nf-fileapi-gettempfilenamea)Windows SDK'sı işlevi. Dosya uzantısı, her zaman için geçici dosya "TFR" olur.

##  <a name="unlockrange"></a>  CAtlTemporaryFile::UnlockRange

Bir bölge geçici dosyanın kilidini açmak için bu yöntemi çağırın.

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

Çağrıları [CAtlFile::UnlockRange](../../atl/reference/catlfile-class.md#unlockrange).

##  <a name="write"></a>  CAtlTemporaryFile::Write

Dosya işaretçisi tarafından belirtilen konumda başlayarak geçici dosya verileri yazmak için bu yöntemi çağırın.

```
HRESULT Write(
    LPCVOID pBuffer,
    DWORD nBufSize,
    DWORD* pnBytesWritten = NULL) throw();
```

### <a name="parameters"></a>Parametreler

*pBuffer*<br/>
Dosyaya yazılacak veriler içeren arabellek.

*nBufSize*<br/>
Arabellekteki aktarılacak bayt sayısı.

*pnBytesWritten*<br/>
Yazılan bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Çağrıları [CAtlFile::Write](../../atl/reference/catlfile-class.md#write).

### <a name="example"></a>Örnek

Örneğin bakın [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)<br/>
[CAtlFile Sınıfı](../../atl/reference/catlfile-class.md)
