---
description: 'Daha fazla bilgi edinin: CGopherLocator sınıfı'
title: CGopherLocator sınıfı
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
ms.openlocfilehash: f615ce6fbda150d923f6664acff207fdebdbba3f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184029"
---
# <a name="cgopherlocator-class"></a>CGopherLocator sınıfı

Gopher sunucusundan bir gopher "Bulucu" alır, bulucunun türünü belirler ve Konumlandırıcı 'yı [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md)için kullanılabilir hale getirir.

> [!NOTE]
> Sınıflar `CGopherConnection` , `CGopherFile` , `CGopherFileFind` `CGopherLocator` ve üyeleri Windows XP platformunda çalışmadıklarından kullanım dışı bırakılmıştır, ancak önceki platformlarda çalışmaya devam ederler.

## <a name="syntax"></a>Syntax

```
class CGopherLocator : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CGopherLocator:: CGopherLocator](#cgopherlocator)|Bir `CGopherLocator` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CGopherLocator:: GetLocatorType](#getlocatortype)|Bir gopher Bulucu ayrıştırır ve özniteliklerini belirler.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CGopherLocator:: operator LPCTSTR](#operator_lpctstr)|Bir nesnede depolanan karakterlere doğrudan `CGopherLocator` C stili dize olarak erişir.|

## <a name="remarks"></a>Açıklamalar

Bir uygulamanın bu sunucudan bilgi alabilmesi için bir Gopher sunucusunun Bulucu alması gerekir. Bulucuya sahip olduktan sonra, Konumlandırıcı 'yı donuk bir belirteç olarak değerlendirmelidir.

Her bir gopher Konumlandırıcı, bulunan dosya veya sunucu türünü belirleyecek özniteliklere sahiptir. Gopher Konumlandırıcı türlerinin listesi için bkz. [GetLocatorType](#getlocatortype) .

Bir uygulama, belirli bir bilgi parçasını almak için normalde, [CGopherFileFind:: FindFile](../../mfc/reference/cgopherfilefind-class.md#findfile) çağrıları için bulucu kullanır.

Diğer MFC Internet sınıflarıyla nasıl çalıştığı hakkında daha fazla bilgi edinmek için `CGopherLocator` bkz. [Winınet Ile Internet programlama](../../mfc/win32-internet-extensions-wininet.md)makalesi.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CGopherLocator`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFXINET. h

## <a name="cgopherlocatorcgopherlocator"></a><a name="cgopherlocator"></a> CGopherLocator:: CGopherLocator

Bu üye işlevi bir nesne oluşturmak için çağırılır `CGopherLocator` .

```
CGopherLocator(const CGopherLocator& ref);
```

### <a name="parameters"></a>Parametreler

*ref*<br/>
Sabit bir `CGopherLocator` nesneye başvuru.

### <a name="remarks"></a>Açıklamalar

Hiçbir şekilde doğrudan bir nesne oluşturmamanız gerekir `CGopherLocator` . Bunun yerine, nesnesine bir işaretçi oluşturmak ve döndürmek için [CGopherConnection:: CreateLocator](../../mfc/reference/cgopherconnection-class.md#createlocator) ' ı çağırın `CGopherLocator` .

## <a name="cgopherlocatorgetlocatortype"></a><a name="getlocatortype"></a> CGopherLocator:: GetLocatorType

Konumlandırıcı türünü almak için bu üye işlevini çağırın.

```
BOOL GetLocatorType(DWORD& dwRef) const;
```

### <a name="parameters"></a>Parametreler

*dwRef*<br/>
Bulucu türünü alacak bir DWORD başvurusu. Konumlandırıcı türleri tablosunun **açıklamalarını** inceleyin.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0. Çağrı başarısız olursa, hatanın nedenini öğrenmek için WIN32 [Win32 işlevi çağrılabilir](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) .

### <a name="remarks"></a>Açıklamalar

Olası türler şunlardır:

|Değer|Anlamı|
|-----------|-------------|
|GOPHER_TYPE_TEXT_FILE|ASCII metin dosyası.|
|GOPHER_TYPE_DIRECTORY|Ek Gopher öğelerinin dizini.|
|GOPHER_TYPE_CSO|Bir CSO telefon book sunucusu.|
|GOPHER_TYPE_ERROR|Bir hata koşulunu gösterir.|
|GOPHER_TYPE_MAC_BINHEX|BINHEX biçimindeki bir Macintosh dosyası.|
|GOPHER_TYPE_DOS_ARCHIVE|Bir DOS arşiv dosyası.|
|GOPHER_TYPE_UNIX_UUENCODED|Bir UUENCODED dosyası.|
|GOPHER_TYPE_INDEX_SERVER|Bir dizin sunucusu.|
|GOPHER_TYPE_TELNET|Bir Telnet sunucusu.|
|GOPHER_TYPE_BINARY|İkili dosya.|
|GOPHER_TYPE_REDUNDANT|Yinelenen bir sunucu. İçinde yer alan bilgiler, birincil sunucunun yinelemesi olur. Birincil sunucu, GOPHER_TYPE_REDUNDANT türüne sahip olmayan son dizin girişi.|
|GOPHER_TYPE_TN3270|Bir TN3270 sunucusu.|
|GOPHER_TYPE_GIF|Bir GIF grafik dosyası.|
|GOPHER_TYPE_IMAGE|Bir görüntü dosyası.|
|GOPHER_TYPE_BITMAP|Bir bit eşlem dosyası.|
|GOPHER_TYPE_MOVIE|Bir film dosyası.|
|GOPHER_TYPE_SOUND|Bir ses dosyası.|
|GOPHER_TYPE_HTML|Bir HTML belgesi.|
|GOPHER_TYPE_PDF|PDF dosyası.|
|GOPHER_TYPE_CALENDAR|Bir takvim dosyası.|
|GOPHER_TYPE_INLINE|Satır içi bir dosya.|
|GOPHER_TYPE_UNKNOWN|Öğe türü bilinmiyor.|
|GOPHER_TYPE_ASK|Bir ask ve öğesi.|
|GOPHER_TYPE_GOPHER_PLUS|Gopher + öğesi.|

## <a name="cgopherlocatoroperator-lpctstr"></a><a name="operator_lpctstr"></a> CGopherLocator:: operator LPCTSTR

Bu kullanışlı atama işleci, bir nesnede bulunan null ile sonlandırılmış C dizesine erişmek için verimli bir yöntem sağlar `CGopherLocator` .

```
operator LPCTSTR () const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizenin verilerine yönelik bir karakter işaretçisi.

### <a name="remarks"></a>Açıklamalar

Hiçbir karakter kopyalanmaz; yalnızca bir işaretçi döndürülür.

## <a name="see-also"></a>Ayrıca bkz.

[CObject sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CGopherFileFind sınıfı](../../mfc/reference/cgopherfilefind-class.md)
