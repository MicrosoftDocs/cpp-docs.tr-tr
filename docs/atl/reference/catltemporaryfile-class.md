---
title: CAtlTemporaryFile Sınıfı
ms.date: 11/04/2016
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
helpviewer_keywords:
- CAtlTemporaryFile class
ms.assetid: 05f0f2a5-94f6-4594-8dae-b114292ff5f9
ms.openlocfilehash: f3d0be66bf0b5a6c07a72c8ae6cc9c90e176728f
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2020
ms.locfileid: "82167896"
---
# <a name="catltemporaryfile-class"></a>CAtlTemporaryFile Sınıfı

Bu sınıf, geçici bir dosyanın oluşturulması ve kullanılması için yöntemler sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```cpp
class CAtlTemporaryFile
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)|Oluşturucu.|
|[CAtlTemporaryFile:: ~ CAtlTemporaryFile](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAtlTemporaryFile:: Close](#close)|Geçici bir dosyayı kapatmak ve içeriğini silmek ya da belirtilen dosya adı altında depolamak için bu yöntemi çağırın.|
|[CAtlTemporaryFile:: Create](#create)|Geçici bir dosya oluşturmak için bu yöntemi çağırın.|
|[CAtlTemporaryFile:: Flush](#flush)|Dosya arabelleğinde kalan tüm verileri geçici dosyaya yazılmasına zorlamak için bu yöntemi çağırın.|
|[CAtlTemporaryFile:: GetPosition](#getposition)|Geçerli dosya işaretçisi konumunu almak için bu yöntemi çağırın.|
|[CAtlTemporaryFile:: GetSize](#getsize)|Geçici dosyanın bayt cinsinden boyutunu almak için bu yöntemi çağırın.|
|[CAtlTemporaryFile:: HandsOff](#handsoff)|Dosyanın `CAtlTemporaryFile` nesneden ilişkilendirmesini kaldırmak için bu yöntemi çağırın.|
|[CAtlTemporaryFile:: HandsOn](#handson)|Varolan geçici bir dosyayı açmak ve işaretçiyi dosyanın sonuna yerleştirmek için bu yöntemi çağırın.|
|[CAtlTemporaryFile:: LockRange](#lockrange)|Diğer işlemlerin bu işleme erişmesini engellemek için dosyadaki bir bölgeyi kilitlemek üzere bu yöntemi çağırın.|
|[CAtlTemporaryFile:: Read](#read)|Dosya işaretçisi tarafından belirtilen konumdan başlayarak geçici dosyadaki verileri okumak için bu yöntemi çağırın.|
|[CAtlTemporaryFile:: Seek](#seek)|Geçici dosyanın dosya işaretçisini taşımak için bu yöntemi çağırın.|
|[CAtlTemporaryFile:: SetSize](#setsize)|Geçici dosyanın boyutunu ayarlamak için bu yöntemi çağırın.|
|[CAtlTemporaryFile:: TempFileName](#tempfilename)|Geçici dosyanın adını döndürmek için bu yöntemi çağırın.|
|[CAtlTemporaryFile:: UnlockRange](#unlockrange)|Geçici dosyanın bir bölgesinin kilidini açmak için bu yöntemi çağırın.|
|[CAtlTemporaryFile:: Write](#write)|Dosya işaretçisi tarafından belirtilen konumdan başlayarak geçici dosyaya veri yazmak için bu yöntemi çağırın.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CAtlTemporaryFile:: operator işleci](#operator_handle)|Geçici dosyaya bir tanıtıcı döndürür.|

## <a name="remarks"></a>Açıklamalar

`CAtlTemporaryFile`geçici bir dosya oluşturmayı ve kullanmayı kolaylaştırır. Dosya otomatik olarak adlandırılır, açılır, kapatılır ve silinir. Dosya kapatıldıktan sonra dosya içeriği gerekliyse, belirtilen ada sahip yeni bir dosyaya kaydedilebilir.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlfile. h

## <a name="example"></a>Örnek

[CAtlTemporaryFile:: CAtlTemporaryFile](#catltemporaryfile)için örneğe bakın.

## <a name="catltemporaryfilecatltemporaryfile"></a><a name="catltemporaryfile"></a>CAtlTemporaryFile::CAtlTemporaryFile

Oluşturucu.

```cpp
CAtlTemporaryFile() throw();
```

### <a name="remarks"></a>Açıklamalar

Bir dosya, [CAtlTemporaryFile:: Create](#create)öğesine bir çağrı yapana kadar aslında açılmaz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#73](../../atl/codesnippet/cpp/catltemporaryfile-class_1.cpp)]

## <a name="catltemporaryfilecatltemporaryfile"></a><a name="dtor"></a>CAtlTemporaryFile:: ~ CAtlTemporaryFile

Yok edicisi.

```cpp
~CAtlTemporaryFile() throw();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı [CAtlTemporaryFile:: Close](#close)çağırır.

## <a name="catltemporaryfileclose"></a><a name="close"></a>CAtlTemporaryFile:: Close

Geçici bir dosyayı kapatmak ve içeriğini silmek ya da belirtilen dosya adı altında depolamak için bu yöntemi çağırın.

```cpp
HRESULT Close(LPCTSTR szNewName = NULL) throw();
```

### <a name="parameters"></a>Parametreler

*Szyeniad*<br/>
İçindeki geçici dosyanın içeriğini depolayan yeni dosyanın adı. Bu bağımsız değişken NULL ise, geçici dosyanın içeriği silinir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="example"></a>Örnek

[CAtlTemporaryFile:: CAtlTemporaryFile](#catltemporaryfile)için örneğe bakın.

## <a name="catltemporaryfilecreate"></a><a name="create"></a>CAtlTemporaryFile:: Create

Geçici bir dosya oluşturmak için bu yöntemi çağırın.

```cpp
HRESULT Create(LPCTSTR pszDir = NULL, DWORD dwDesiredAccess = GENERIC_WRITE) throw();
```

### <a name="parameters"></a>Parametreler

*pszDir*<br/>
Geçici dosyanın yolu. Bu NULL ise, bir yol atamak için [GetTempPath](/windows/win32/api/fileapi/nf-fileapi-gettemppathw) çağırılır.

*dwDesiredAccess*<br/>
İstenen erişim. Windows SDK [CreateFile](/windows/win32/api/fileapi/nf-fileapi-createfilew) öğesinde *dwDesiredAccess* öğesine bakın.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="example"></a>Örnek

[CAtlTemporaryFile:: CAtlTemporaryFile](#catltemporaryfile)için örneğe bakın.

## <a name="catltemporaryfileflush"></a><a name="flush"></a>CAtlTemporaryFile:: Flush

Dosya arabelleğinde kalan tüm verileri geçici dosyaya yazılmasına zorlamak için bu yöntemi çağırın.

```cpp
HRESULT Flush() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

[CAtlTemporaryFile:: HandsOff](#handsoff)ile benzer, dosyanın kapanmamış olması gerekir.

### <a name="example"></a>Örnek

[CAtlTemporaryFile:: CAtlTemporaryFile](#catltemporaryfile)için örneğe bakın.

## <a name="catltemporaryfilegetposition"></a><a name="getposition"></a>CAtlTemporaryFile:: GetPosition

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

Dosya işaretçisi konumunu değiştirmek için [CAtlTemporaryFile:: Seek](#seek)kullanın.

## <a name="catltemporaryfilegetsize"></a><a name="getsize"></a>CAtlTemporaryFile:: GetSize

Geçici dosyanın bayt cinsinden boyutunu almak için bu yöntemi çağırın.

```cpp
HRESULT GetSize(ULONGLONG& nLen) const throw();
```

### <a name="parameters"></a>Parametreler

*nLen*<br/>
Dosyadaki bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

## <a name="catltemporaryfilehandsoff"></a><a name="handsoff"></a>CAtlTemporaryFile:: HandsOff

Dosyanın `CAtlTemporaryFile` nesneden ilişkilendirmesini kaldırmak için bu yöntemi çağırın.

```cpp
HRESULT HandsOff() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

`HandsOff`ve [CAtlTemporaryFile:: HandsOn](#handson) , dosyanın nesneyle ilişkisini kaldırmak ve gerekirse yeniden iliştirmek için kullanılır. `HandsOff`dosya arabelleğinde kalan tüm verileri geçici dosyaya yazılacak şekilde zorlar ve sonra dosyayı kapatır. Dosyayı kalıcı olarak kapatmak ve silmek istiyorsanız veya dosyanın içeriğini belirli bir adla kapatmak ve sürdürmek istiyorsanız, [CAtlTemporaryFile:: Close](#close)kullanın.

## <a name="catltemporaryfilehandson"></a><a name="handson"></a>CAtlTemporaryFile:: HandsOn

Varolan geçici bir dosyayı açmak ve işaretçiyi dosyanın sonuna yerleştirmek için bu yöntemi çağırın.

```cpp
HRESULT HandsOn() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

[CAtlTemporaryFile:: HandsOff](#handsoff) ve `HandsOn` dosyanın nesneyle ilişkisi için kullanılır ve gerekirse yeniden ekleyin.

## <a name="catltemporaryfilelockrange"></a><a name="lockrange"></a>CAtlTemporaryFile:: LockRange

Başka işlemlerin bu işleme erişmesini engellemek için geçici dosyadaki bir bölgeyi kilitlemek üzere bu yöntemi çağırın.

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

Bir dosyadaki kilitleme baytları diğer işlemlere göre bu baytlara erişimi engeller. Bir dosyanın birden fazla bölgesini kilitleyebilmeniz, ancak çakışan bölgelere izin verilmez. Bir bölgenin kilidini başarıyla açmak için, [CAtlTemporaryFile:: UnlockRange](#unlockrange)kullanın. Bu, bayt aralığının daha önce kilitlenen bölgeye tam olarak karşılık gelmesini sağlamaktır. `LockRange`bitişik bölgeleri birleştirmez; iki kilitli bölge bitişik ise, her birinin kilidini ayrı olarak açmanız gerekir.

## <a name="catltemporaryfileoperator-handle"></a><a name="operator_handle"></a>CAtlTemporaryFile:: operator işleci

Geçici dosyaya bir tanıtıcı döndürür.

```cpp
operator HANDLE() throw();
```

## <a name="catltemporaryfileread"></a><a name="read"></a>CAtlTemporaryFile:: Read

Dosya işaretçisi tarafından belirtilen konumdan başlayarak geçici dosyadaki verileri okumak için bu yöntemi çağırın.

```cpp
HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    DWORD& nBytesRead) throw();
```

### <a name="parameters"></a>Parametreler

*pBuffer*<br/>
Dosyadan okunan verileri alacak olan arabelleğin işaretçisi.

*nBufSize*<br/>
Bayt cinsinden arabellek boyutu.

*nBytesRead*<br/>
Okunan bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

[CAtlFile:: Read](../../atl/reference/catlfile-class.md#read)çağırır. Dosya işaretçisinin konumunu değiştirmek için [CAtlTemporaryFile:: Seek](#seek)çağırın.

### <a name="example"></a>Örnek

[CAtlTemporaryFile:: CAtlTemporaryFile](#catltemporaryfile)için örneğe bakın.

## <a name="catltemporaryfileseek"></a><a name="seek"></a>CAtlTemporaryFile:: Seek

Geçici dosyanın dosya işaretçisini taşımak için bu yöntemi çağırın.

```cpp
HRESULT Seek(LONGLONG nOffset, DWORD dwFrom = FILE_CURRENT) throw();
```

### <a name="parameters"></a>Parametreler

*nKonum*<br/>
*DwFrom* tarafından verilen başlangıç noktasından bayt cinsinden fark.

*dwFrom*<br/>
Başlangıç noktası (FILE_BEGIN, FILE_CURRENT veya FILE_END).

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

[CAtlFile:: Seek](../../atl/reference/catlfile-class.md#seek)çağırır. Geçerli dosya işaretçisi konumunu almak için, [CAtlTemporaryFile:: GetPosition](#getposition)çağırın.

### <a name="example"></a>Örnek

[CAtlTemporaryFile:: CAtlTemporaryFile](#catltemporaryfile)için örneğe bakın.

## <a name="catltemporaryfilesetsize"></a><a name="setsize"></a>CAtlTemporaryFile:: SetSize

Geçici dosyanın boyutunu ayarlamak için bu yöntemi çağırın.

```cpp
HRESULT SetSize(ULONGLONG nNewLen) throw();
```

### <a name="parameters"></a>Parametreler

*nNewLen*<br/>
Dosyanın bayt cinsinden yeni uzunluğu.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

[CAtlFile:: SetSize](../../atl/reference/catlfile-class.md#setsize)çağırır. Dönüş sırasında dosya işaretçisi dosyanın sonuna yerleştirilir.

## <a name="catltemporaryfiletempfilename"></a><a name="tempfilename"></a>CAtlTemporaryFile:: TempFileName

Geçici dosyanın adını döndürmek için bu yöntemi çağırın.

```cpp
LPCTSTR TempFileName() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dosya adına işaret eden LPCTSTR döndürür.

### <a name="remarks"></a>Açıklamalar

Dosya adı [CAtlTemporaryFile:: CAtlTemporaryFile](#catltemporaryfile) ' de [gettempfile](/windows/win32/api/fileapi/nf-fileapi-gettempfilenamew)Windows SDK işlevine yapılan bir çağrıda oluşturulur. Dosya Uzantısı her zaman geçici dosya için "TFR" olacaktır.

## <a name="catltemporaryfileunlockrange"></a><a name="unlockrange"></a>CAtlTemporaryFile:: UnlockRange

Geçici dosyanın bir bölgesinin kilidini açmak için bu yöntemi çağırın.

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

[CAtlFile:: UnlockRange](../../atl/reference/catlfile-class.md#unlockrange)öğesini çağırır.

## <a name="catltemporaryfilewrite"></a><a name="write"></a>CAtlTemporaryFile:: Write

Dosya işaretçisi tarafından belirtilen konumdan başlayarak geçici dosyaya veri yazmak için bu yöntemi çağırın.

```cpp
HRESULT Write(
    LPCVOID pBuffer,
    DWORD nBufSize,
    DWORD* pnBytesWritten = NULL) throw();
```

### <a name="parameters"></a>Parametreler

*pBuffer*<br/>
Dosyaya yazılacak verileri içeren arabellek.

*nBufSize*<br/>
Arabellekten aktarılacak bayt sayısı.

*pnBytesWritten*<br/>
Yazılan bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

[CAtlFile:: Write](../../atl/reference/catlfile-class.md#write)öğesini çağırır.

### <a name="example"></a>Örnek

[CAtlTemporaryFile:: CAtlTemporaryFile](#catltemporaryfile)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[CAtlFile Sınıfı](../../atl/reference/catlfile-class.md)
