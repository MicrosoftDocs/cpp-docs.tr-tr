---
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
ms.openlocfilehash: f25273f1d982092adc8b8010cc60818e7c0e24a2
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66503662"
---
# <a name="cgopherlocator-class"></a>CGopherLocator sınıfı

Bir gopher sunucusundan "Konum Belirleyicisi" alır, konum belirleyicinin türünü ve Bulucu kullanılabilmesini [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md).

> [!NOTE]
>  Sınıfları `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` ve üyeleri bırakılmıştır, Windows XP platformu üzerinde çalışmaz, ancak önceki platformları üzerinde çalışmaya devam eder.

## <a name="syntax"></a>Sözdizimi

```
class CGopherLocator : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CGopherLocator::CGopherLocator](#cgopherlocator)|Oluşturur bir `CGopherLocator` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CGopherLocator::GetLocatorType](#getlocatortype)|Bir gopher Bulucu ayrıştırır ve özniteliklerini belirler.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CGopherLocator::operator LPCTSTR](#operator_lpctstr)|İçinde depolanan karakterlerin doğrudan erişir bir `CGopherLocator` C stili dize olarak nesnesi.|

## <a name="remarks"></a>Açıklamalar

Bir uygulama, o sunucudan bilgi almadan önce bir gopher sunucunun Bulucu almanız gerekir. Bulucu olduğunda, bu Bulucu donuk bir belirteç olarak ele almanız gerekir.

Her bir gopher Bulucu dosya ya da sunucu bulundu türünü belirleyen özniteliklere sahiptir. Bkz: [GetLocatorType](#getlocatortype) gopher Bulucuyu türleri listesi.

Bir uygulamanın Bulucu çağrılar için normalde kullandığı [CGopherFileFind::FindFile](../../mfc/reference/cgopherfilefind-class.md#findfile) belirli bir bilgi alınamadı.

Hakkında daha fazla bilgi edinmek için `CGopherLocator` diğer Internet MFC sınıfları ile çalışır, başlıklı makaleye bakın [Winınet'in Internet programlama](../../mfc/win32-internet-extensions-wininet.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CGopherLocator`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxinet.h

##  <a name="cgopherlocator"></a>  CGopherLocator::CGopherLocator

Bu üye işlevi oluşturmak için çağrılan bir `CGopherLocator` nesne.

```
CGopherLocator(const CGopherLocator& ref);
```

### <a name="parameters"></a>Parametreler

*ref*<br/>
Bir sabit bir başvuru `CGopherLocator` nesne.

### <a name="remarks"></a>Açıklamalar

Asla oluşturma bir `CGopherLocator` doğrudan nesne. Bunun yerine çağrı [CGopherConnection::CreateLocator](../../mfc/reference/cgopherconnection-class.md#createlocator) oluşturmak ve bir işaretçi döndürmek için `CGopherLocator` nesne.

##  <a name="getlocatortype"></a>  CGopherLocator::GetLocatorType

Bulucu türünü almak için bu üye işlevini çağırın.

```
BOOL GetLocatorType(DWORD& dwRef) const;
```

### <a name="parameters"></a>Parametreler

*dwRef*<br/>
Bulucu türü alacak bir DWORD başvuru. Bkz: **açıklamalar** Bulucu türlerinin bir tablo için.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0. Çağrı başarısız olursa, Win32 işlevini [GetLastError](/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror) hatanın nedenini belirlemek için çağrılabilir.

### <a name="remarks"></a>Açıklamalar

Olası türleri aşağıdaki gibidir:

|Değer|Açıklama|
|-----------|-------------|
|GOPHER_TYPE_TEXT_FILE|Bir ASCII metin dosyası.|
|GOPHER_TYPE_DIRECTORY|Ek Gopher öğe dizini.|
|GOPHER_TYPE_CSO|CSO telefon rehberi sunucu.|
|GOPHER_TYPE_ERROR|Bir hata koşulu belirtir.|
|GOPHER_TYPE_MAC_BINHEX|BINHEX biçiminde bir Macintosh dosyası.|
|GOPHER_TYPE_DOS_ARCHIVE|Bir DOS arşiv dosyası.|
|GOPHER_TYPE_UNIX_UUENCODED|UUENCODED dosya.|
|GOPHER_TYPE_INDEX_SERVER|Bir dizin sunucusu.|
|GOPHER_TYPE_TELNET|Telnet sunucusu.|
|GOPHER_TYPE_BINARY|Bir ikili dosyadır.|
|GOPHER_TYPE_REDUNDANT|Yinelenen bir sunucu. İçinde yer alan bilgileri, birincil sunucunun yineleniyor. Birincil sunucu GOPHER_TYPE_REDUNDANT türü yoktu son dizin girdisi değil.|
|GOPHER_TYPE_TN3270|TN3270 sunucu.|
|GOPHER_TYPE_GIF|Bir GIF grafik dosyası.|
|GOPHER_TYPE_IMAGE|Bir resim dosyası.|
|GOPHER_TYPE_BITMAP|Bir bit eşlem dosyası.|
|GOPHER_TYPE_MOVIE|Bir film dosyası.|
|GOPHER_TYPE_SOUND|Ses dosyası.|
|GOPHER_TYPE_HTML|Bir HTML belgesi.|
|GOPHER_TYPE_PDF|Bir PDF dosyası.|
|GOPHER_TYPE_CALENDAR|Bir takvim dosyası.|
|GOPHER_TYPE_INLINE|Satır içi dosya.|
|GOPHER_TYPE_UNKNOWN|Öğe türü bilinmiyor.|
|GOPHER_TYPE_ASK|Ask + öğe.|
|GOPHER_TYPE_GOPHER_PLUS|Bir Gopher + öğesi.|

##  <a name="operator_lpctstr"></a>  CGopherLocator::operator LPCTSTR

Bu yararlı bir yayım işleciyle bulunan boş sonlandırılmış C dizesi erişmek için verimli bir yöntem sağlar. bir `CGopherLocator` nesne.

```
operator LPCTSTR () const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizenin veri karakter işaretçisi.

### <a name="remarks"></a>Açıklamalar

Hiçbir karakter kopyalanır; yalnızca bir işaretçi döndürülür.

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CGopherFileFind Sınıfı](../../mfc/reference/cgopherfilefind-class.md)
