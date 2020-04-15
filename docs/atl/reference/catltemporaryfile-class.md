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
ms.openlocfilehash: 605e4bcbe7208b18d8d1a50507e8e142a93bde5e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321315"
---
# <a name="catltemporaryfile-class"></a>CAtlTemporaryFile Sınıfı

Bu sınıf, geçici bir dosya oluşturma ve kullanma yöntemleri sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CAtlTemporaryFile
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)|Oluşturucu.|
|[CAtlTemporaryFile::~CAtlTemporaryFile](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAtlTemporaryFile::Kapat](#close)|Geçici bir dosyayı kapatmak ve içeriğini silmek veya belirtilen dosya adı altında depolamak için bu yöntemi arayın.|
|[CAtlTemporaryFile::Oluştur](#create)|Geçici bir dosya oluşturmak için bu yöntemi arayın.|
|[CAtlTemporaryFile::Flush](#flush)|Dosya arabelleğinde kalan verileri geçici dosyaya yazılmaya zorlamak için bu yöntemi arayın.|
|[CAtlTemporaryFile::GetPosition](#getposition)|Geçerli dosya işaretçisi konumunu almak için bu yöntemi arayın.|
|[CAtlTemporaryFile::GetSize](#getsize)|Geçici dosyanın baytlarında boyutu almak için bu yöntemi arayın.|
|[CAtlTemporaryFile::HandsOff](#handsoff)|Dosyayı `CAtlTemporaryFile` nesneden ayırmak için bu yöntemi çağırın.|
|[CAtlTemporaryFile::HandsOn](#handson)|Varolan geçici bir dosyayı açmak ve işaretçiyi dosyanın sonunda konumlandırmak için bu yöntemi çağırın.|
|[CAtlTemporaryFile::LockRange](#lockrange)|Diğer işlemlerin dosyaya erişmesini önlemek için dosyadaki bir bölgeyi kilitlemek için bu yöntemi çağırın.|
|[CAtlTemporaryFile::Oku](#read)|Dosya işaretçisi tarafından belirtilen konumdan başlayarak geçici dosyadan verileri okumak için bu yöntemi arayın.|
|[CAtlTemporaryFile::Ara](#seek)|Geçici dosyaişaretçisini taşımak için bu yöntemi çağırın.|
|[CAtlTemporaryFile::SetSize](#setsize)|Geçici dosyanın boyutunu ayarlamak için bu yöntemi arayın.|
|[CAtlTemporaryFile::TempFileName](#tempfilename)|Geçici dosyanın adını döndürmek için bu yöntemi arayın.|
|[CAtlTemporaryFile::UnlockRange](#unlockrange)|Geçici dosyanın bir bölgesinin kilidini açmak için bu yöntemi arayın.|
|[CAtlTemporaryFile::Yaz](#write)|Dosya işaretçisi tarafından belirtilen konumdan başlayarak geçici dosyaya veri yazmak için bu yöntemi arayın.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CAtlTemporaryFile::operatör KOLU](#operator_handle)|Geçici dosyaya bir tanıtıcı döndürür.|

## <a name="remarks"></a>Açıklamalar

`CAtlTemporaryFile`geçici bir dosya oluşturmayı ve kullanmayı kolaylaştırır. Dosya otomatik olarak adlandırılır, açılır, kapatılır ve silinir. Dosya kapatıldıktan sonra dosya içeriği gerekliyse, bunlar belirtilen ada sahip yeni bir dosyaya kaydedilebilir.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlfile.h

## <a name="example"></a>Örnek

[CAtlTemporaryFile örneğine bakın:CAtlTemporaryFile](#catltemporaryfile).

## <a name="catltemporaryfilecatltemporaryfile"></a><a name="catltemporaryfile"></a>CAtlTemporaryFile::CAtlTemporaryFile

Oluşturucu.

```
CAtlTemporaryFile() throw();
```

### <a name="remarks"></a>Açıklamalar

[CAtlTemporaryFile'a](#create)arama yapılına kadar bir dosya aslında açılmaz::Oluştur .

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#73](../../atl/codesnippet/cpp/catltemporaryfile-class_1.cpp)]

## <a name="catltemporaryfilecatltemporaryfile"></a><a name="dtor"></a>CAtlTemporaryFile::~CAtlTemporaryFile

Yıkıcı.

```
~CAtlTemporaryFile() throw();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı [CAtlTemporaryFile çağırır::Kapat](#close).

## <a name="catltemporaryfileclose"></a><a name="close"></a>CAtlTemporaryFile::Kapat

Geçici bir dosyayı kapatmak ve içeriğini silmek veya belirtilen dosya adı altında depolamak için bu yöntemi arayın.

```
HRESULT Close(LPCTSTR szNewName = NULL) throw();
```

### <a name="parameters"></a>Parametreler

*szNewName*<br/>
Geçici dosyanın içeriğini depolamak için yeni dosyanın adı. Bu bağımsız değişken NULL ise, geçici dosyanın içeriği silinir.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="example"></a>Örnek

[CAtlTemporaryFile örneğine bakın:CAtlTemporaryFile](#catltemporaryfile).

## <a name="catltemporaryfilecreate"></a><a name="create"></a>CAtlTemporaryFile::Oluştur

Geçici bir dosya oluşturmak için bu yöntemi arayın.

```
HRESULT Create(LPCTSTR pszDir = NULL, DWORD dwDesiredAccess = GENERIC_WRITE) throw();
```

### <a name="parameters"></a>Parametreler

*pszDir*<br/>
Geçici dosyanın yolu. Bu NULL ise, [GetTempPath](/windows/win32/api/fileapi/nf-fileapi-gettemppathw) bir yol atamak için çağrılacaktır.

*dwDesiredAccess*<br/>
İstenilen erişim. Windows SDK'daki [CreateFile'da](/windows/win32/api/fileapi/nf-fileapi-createfilew) *dwDesiredAccess'e* bakın.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="example"></a>Örnek

[CAtlTemporaryFile örneğine bakın:CAtlTemporaryFile](#catltemporaryfile).

## <a name="catltemporaryfileflush"></a><a name="flush"></a>CAtlTemporaryFile::Flush

Dosya arabelleğinde kalan verileri geçici dosyaya yazılmaya zorlamak için bu yöntemi arayın.

```
HRESULT Flush() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

[CAtlTemporaryFile benzer::HandsOff](#handsoff), dosya kapalı olmaması dışında.

### <a name="example"></a>Örnek

[CAtlTemporaryFile örneğine bakın:CAtlTemporaryFile](#catltemporaryfile).

## <a name="catltemporaryfilegetposition"></a><a name="getposition"></a>CAtlTemporaryFile::GetPosition

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

Dosya işaretçisi konumunu değiştirmek için [CAtlTemporaryFile kullanın::Seek](#seek).

## <a name="catltemporaryfilegetsize"></a><a name="getsize"></a>CAtlTemporaryFile::GetSize

Geçici dosyanın baytlarında boyutu almak için bu yöntemi arayın.

```
HRESULT GetSize(ULONGLONG& nLen) const throw();
```

### <a name="parameters"></a>Parametreler

*nLen*<br/>
Dosyadaki bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="catltemporaryfilehandsoff"></a><a name="handsoff"></a>CAtlTemporaryFile::HandsOff

Dosyayı `CAtlTemporaryFile` nesneden ayırmak için bu yöntemi çağırın.

```
HRESULT HandsOff() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

`HandsOff`ve [CAtlTemporaryFile::HandsOn](#handson) dosyayı nesneden ayırmak ve gerekirse yeniden takmak için kullanılır. `HandsOff`dosya arabelleğinde kalan tüm verileri geçici dosyaya yazılmaya zorlar ve sonra dosyayı kapatır. Dosyayı kalıcı olarak kapatıp silmek istiyorsanız veya belirli bir adla dosyanın içeriğini kapatıp saklamak istiyorsanız [CAtlTemporaryFile::Kapat](#close)' ı kullanın.

## <a name="catltemporaryfilehandson"></a><a name="handson"></a>CAtlTemporaryFile::HandsOn

Varolan geçici bir dosyayı açmak ve işaretçiyi dosyanın sonunda konumlandırmak için bu yöntemi çağırın.

```
HRESULT HandsOn() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

[CAtlTemporaryFile::HandsOff](#handsoff) `HandsOn` ve nesneden dosyayı ayırmak ve gerekirse yeniden takmak için kullanılır.

## <a name="catltemporaryfilelockrange"></a><a name="lockrange"></a>CAtlTemporaryFile::LockRange

Diğer işlemlerin bu yönteme erişmesini önlemek için geçici dosyadaki bir bölgeyi kilitlemek için bu yöntemi çağırın.

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

Bir dosyadaki baytların kilitlenerek diğer işlemler tarafından bu baytlara erişimi engeller. Bir dosyanın birden fazla bölgesini kilitleyebilirsiniz, ancak çakışan bölgelere izin verilmez. Bir bölgenin kilidini başarıyla açmak için [CAtlTemporaryFile::UnlockRange'i](#unlockrange)kullanın, bayt aralığının daha önce kilitlenmiş olan bölgeye tam olarak karşılık geldiğini sağlamak. `LockRange`bitişik bölgeleri birleştirmez; iki kilitli bölge bitişikse, her birinin kilidini ayrı ayrı açmanız gerekir.

## <a name="catltemporaryfileoperator-handle"></a><a name="operator_handle"></a>CAtlTemporaryFile::operatör KOLU

Geçici dosyaya bir tanıtıcı döndürür.

```
operator HANDLE() throw();
```

## <a name="catltemporaryfileread"></a><a name="read"></a>CAtlTemporaryFile::Oku

Dosya işaretçisi tarafından belirtilen konumdan başlayarak geçici dosyadan verileri okumak için bu yöntemi arayın.

```
HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    DWORD& nBytesRead) throw();
```

### <a name="parameters"></a>Parametreler

*Pbuffer*<br/>
Dosyadan okunan verileri alacak arabelleğe işaretçi.

*nBufSize*<br/>
Arabellek boyutu baytlar içinde.

*nBytesRead*<br/>
Okunan bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Aramalar [CAtlFile::Oku](../../atl/reference/catlfile-class.md#read). Dosya işaretçisinin konumunu değiştirmek için [CAtlTemporaryFile'ı arayın::Ara.](#seek)

### <a name="example"></a>Örnek

[CAtlTemporaryFile örneğine bakın:CAtlTemporaryFile](#catltemporaryfile).

## <a name="catltemporaryfileseek"></a><a name="seek"></a>CAtlTemporaryFile::Ara

Geçici dosyaişaretçisini taşımak için bu yöntemi çağırın.

```
HRESULT Seek(LONGLONG nOffset, DWORD dwFrom = FILE_CURRENT) throw();
```

### <a name="parameters"></a>Parametreler

*nOffset*<br/>
Ofset, bayt, *dwFrom* tarafından verilen başlangıç noktasından.

*dwKaynak*<br/>
Başlangıç noktası (FILE_BEGIN, FILE_CURRENT veya FILE_END).

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Aramalar [CAtlFile::Seek](../../atl/reference/catlfile-class.md#seek). Geçerli dosya işaretçisi konumunu almak için [CAtlTemporaryFile'ı arayın::GetPosition](#getposition).

### <a name="example"></a>Örnek

[CAtlTemporaryFile örneğine bakın:CAtlTemporaryFile](#catltemporaryfile).

## <a name="catltemporaryfilesetsize"></a><a name="setsize"></a>CAtlTemporaryFile::SetSize

Geçici dosyanın boyutunu ayarlamak için bu yöntemi arayın.

```
HRESULT SetSize(ULONGLONG nNewLen) throw();
```

### <a name="parameters"></a>Parametreler

*nNewLen*<br/>
Baytlar halindeki dosyanın yeni uzunluğu.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

[CAtlFile'ı Arar::SetSize](../../atl/reference/catlfile-class.md#setsize). Döndükten sonra, dosya işaretçisi dosyanın sonuna konumlandırılır.

## <a name="catltemporaryfiletempfilename"></a><a name="tempfilename"></a>CAtlTemporaryFile::TempFileName

Geçici dosyanın adını döndürmek için bu yöntemi arayın.

```
LPCTSTR TempFileName() throw();
```

### <a name="return-value"></a>Dönüş Değeri

LpCTSTR dosya adını gösteren döndürür.

### <a name="remarks"></a>Açıklamalar

Dosya adı [CAtlTemporaryFile oluşturulur::CAtlTemporaryFile](#catltemporaryfile) [GetTempFile](/windows/win32/api/fileapi/nf-fileapi-gettempfilenamew)Windows SDK işlevine bir çağrı ile. Dosya uzantısı her zaman geçici dosya için "TFR" olacaktır.

## <a name="catltemporaryfileunlockrange"></a><a name="unlockrange"></a>CAtlTemporaryFile::UnlockRange

Geçici dosyanın bir bölgesinin kilidini açmak için bu yöntemi arayın.

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

[CAtlFile'ı Arar:UnlockRange](../../atl/reference/catlfile-class.md#unlockrange).

## <a name="catltemporaryfilewrite"></a><a name="write"></a>CAtlTemporaryFile::Yaz

Dosya işaretçisi tarafından belirtilen konumdan başlayarak geçici dosyaya veri yazmak için bu yöntemi arayın.

```
HRESULT Write(
    LPCVOID pBuffer,
    DWORD nBufSize,
    DWORD* pnBytesWritten = NULL) throw();
```

### <a name="parameters"></a>Parametreler

*Pbuffer*<br/>
Dosyaya yazılacak verileri içeren arabellek.

*nBufSize*<br/>
Arabellekten aktarılacak bayt sayısı.

*pnBytesYazılı*<br/>
Yazılan bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Aramalar [CAtlFile::Yaz](../../atl/reference/catlfile-class.md#write).

### <a name="example"></a>Örnek

[CAtlTemporaryFile örneğine bakın:CAtlTemporaryFile](#catltemporaryfile).

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)<br/>
[CAtlFile Sınıfı](../../atl/reference/catlfile-class.md)
