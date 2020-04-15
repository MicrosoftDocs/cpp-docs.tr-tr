---
title: CGopherLocator Sınıf
ms.date: 11/04/2016
f1_keywords:
- CGopherLocator
- AFXINET/CGopherLocator
- AFXINET/CGopherLocator::CGopherLocator
- AFXINET/CGopherLocator::GetLocatorType
helpviewer_keywords:
- CGopherLocator [MFC], CGopherLocator
- CGopherLocator [MFC], GetLocatorType
ms.assetid: 6fcc015f-5ae6-4959-b936-858634c71019
ms.openlocfilehash: d23ef3dad68c62e74ec64454953ca372b8c31114
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373674"
---
# <a name="cgopherlocator-class"></a>CGopherLocator Sınıf

Bir gopher sunucusundan bir gopher "bulucu" alır, bulucu türünü belirler ve bulucu [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md)için kullanılabilir hale getirir.

> [!NOTE]
> Sınıflar `CGopherConnection`, `CGopherFile` `CGopherFileFind`, `CGopherLocator` , , windows xp platformunda çalışmıyor çünkü onların üyeleri küçümsenmiş, ancak önceki platformlarda çalışmaya devam edecektir.

## <a name="syntax"></a>Sözdizimi

```
class CGopherLocator : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CGopherLocator::CGopherLocator](#cgopherlocator)|Bir `CGopherLocator` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CGopherLocator::GetLocatorType](#getlocatortype)|Parses bir gopher bulucu ve özniteliklerini belirler.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CGopherLocator::operatör LPCTSTR](#operator_lpctstr)|C stili dize olarak `CGopherLocator` bir nesnede depolanan karakterlere doğrudan erişir.|

## <a name="remarks"></a>Açıklamalar

Bir uygulama, bu sunucudan bilgi alabilene kadar bir gopher sunucusunun yer belirleyicisini almalıdır. Bir kez bulucatör var, opak bir belirteç olarak bulucu tedavi etmelidir.

Her gopher bulucu, bulunan dosya veya sunucu türünü belirleyen özniteliklere sahiptir. Goher yer bulucularının türlerinin listesi için [GetLocatorType'a](#getlocatortype) bakın.

Bir uygulama normalde CGopherFileFind aramaları için yer belirleyici [kullanır::FindFile](../../mfc/reference/cgopherfilefind-class.md#findfile) belirli bir bilgi parçası almak için.

Diğer MFC `CGopherLocator` Internet sınıfları ile nasıl çalıştığı hakkında daha fazla bilgi edinmek için [WinInet ile internet programlama](../../mfc/win32-internet-extensions-wininet.md)makalesine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CGopherLocator`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxinet.h

## <a name="cgopherlocatorcgopherlocator"></a><a name="cgopherlocator"></a>CGopherLocator::CGopherLocator

Bu üye işlev bir `CGopherLocator` nesne oluşturmak için çağrılır.

```
CGopherLocator(const CGopherLocator& ref);
```

### <a name="parameters"></a>Parametreler

*ref*<br/>
Sabit `CGopherLocator` bir nesneye başvuru.

### <a name="remarks"></a>Açıklamalar

Hiçbir `CGopherLocator` nesneyi doğrudan oluşturmazsınız. Bunun yerine, [CGopherConnection::CreateLocator'u](../../mfc/reference/cgopherconnection-class.md#createlocator) arayarak `CGopherLocator` bir işaretçi oluşturun ve nesneye döndürün.

## <a name="cgopherlocatorgetlocatortype"></a><a name="getlocatortype"></a>CGopherLocator::GetLocatorType

Yer bulucu türünü almak için bu üye işlevi arayın.

```
BOOL GetLocatorType(DWORD& dwRef) const;
```

### <a name="parameters"></a>Parametreler

*dwRef*<br/>
Yer bulucu türünü alacak bir DWORD başvurusu. Yer bulucu türleri tablosu için **Açıklamalar'a** bakın.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0. Arama başarısız olursa, hatanın nedenini belirlemek için Win32 işlevi [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) çağrılabilir.

### <a name="remarks"></a>Açıklamalar

Olası türleri aşağıdaki gibidir:

|Değer|Anlamı|
|-----------|-------------|
|GOPHER_TYPE_TEXT_FILE|ASCII metin dosyası.|
|GOPHER_TYPE_DIRECTORY|Ek Gopher öğelerinin dizini.|
|GOPHER_TYPE_CSO|Bir CSO telefon rehberi sunucusu.|
|GOPHER_TYPE_ERROR|Bir hata durumunu gösterir.|
|GOPHER_TYPE_MAC_BINHEX|BINHEX formatında bir Macintosh dosyası.|
|GOPHER_TYPE_DOS_ARCHIVE|DoS arşiv dosyası.|
|GOPHER_TYPE_UNIX_UUENCODED|UUENCODED dosyası.|
|GOPHER_TYPE_INDEX_SERVER|Dizin sunucusu.|
|GOPHER_TYPE_TELNET|Bir Telnet Sunucusu.|
|GOPHER_TYPE_BINARY|İkili bir dosya.|
|GOPHER_TYPE_REDUNDANT|Yinelenen bir sunucu. İçerdeki bilgiler birincil sunucunun bir kopyasıdır. Birincil sunucu, GOPHER_TYPE_REDUNDANT türü olmayan son dizin girişidir.|
|GOPHER_TYPE_TN3270|Bir TN3270 sunucusu.|
|GOPHER_TYPE_GIF|Bir GIF grafik dosyası.|
|GOPHER_TYPE_IMAGE|Bir resim dosyası.|
|GOPHER_TYPE_BITMAP|Bir bitmap dosyası.|
|GOPHER_TYPE_MOVIE|Bir film dosyası.|
|GOPHER_TYPE_SOUND|Bir ses dosyası.|
|GOPHER_TYPE_HTML|Bir HTML belgesi.|
|GOPHER_TYPE_PDF|Bir PDF dosyası.|
|GOPHER_TYPE_CALENDAR|Bir takvim dosyası.|
|GOPHER_TYPE_INLINE|Satır lı bir dosya.|
|GOPHER_TYPE_UNKNOWN|Öğe türü bilinmiyor.|
|GOPHER_TYPE_ASK|Ask+ öğesi.|
|GOPHER_TYPE_GOPHER_PLUS|Bir Gopher+ öğesi.|

## <a name="cgopherlocatoroperator-lpctstr"></a><a name="operator_lpctstr"></a>CGopherLocator::operatör LPCTSTR

Bu kullanışlı döküm işleci, bir nesnede bulunan null-terminated C dizesine erişmek için etkili bir `CGopherLocator` yöntem sağlar.

```
operator LPCTSTR () const;
```

### <a name="return-value"></a>Dönüş Değeri

Dize verilerine bir karakter işaretçisi.

### <a name="remarks"></a>Açıklamalar

Hiçbir karakter kopyalanır; yalnızca bir işaretçi döndürülür.

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CGopherFileFind Sınıf](../../mfc/reference/cgopherfilefind-class.md)
