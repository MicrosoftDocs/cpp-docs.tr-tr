---
title: CBrush Class
ms.date: 11/04/2016
f1_keywords:
- CBrush
- AFXWIN/CBrush
- AFXWIN/CBrush::CBrush
- AFXWIN/CBrush::CreateBrushIndirect
- AFXWIN/CBrush::CreateDIBPatternBrush
- AFXWIN/CBrush::CreateHatchBrush
- AFXWIN/CBrush::CreatePatternBrush
- AFXWIN/CBrush::CreateSolidBrush
- AFXWIN/CBrush::CreateSysColorBrush
- AFXWIN/CBrush::FromHandle
- AFXWIN/CBrush::GetLogBrush
helpviewer_keywords:
- CBrush [MFC], CBrush
- CBrush [MFC], CreateBrushIndirect
- CBrush [MFC], CreateDIBPatternBrush
- CBrush [MFC], CreateHatchBrush
- CBrush [MFC], CreatePatternBrush
- CBrush [MFC], CreateSolidBrush
- CBrush [MFC], CreateSysColorBrush
- CBrush [MFC], FromHandle
- CBrush [MFC], GetLogBrush
ms.assetid: e5ef2c62-dd95-4973-9090-f52f605900e1
ms.openlocfilehash: f2a2e385a9f210b3644d7fade00b72c4befa47ef
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58778877"
---
# <a name="cbrush-class"></a>CBrush Class

Bir Windows grafik cihaz arabirimi (GDI) Fırçası kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CBrush : public CGdiObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CBrush::CBrush](#cbrush)|Oluşturur bir `CBrush` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CBrush::CreateBrushIndirect](#createbrushindirect)|Fırça stili, renk ve belirtilen desen ile başlatan bir [LOGBRUSH](/windows/desktop/api/wingdi/ns-wingdi-taglogbrush) yapısı.|
|[CBrush::CreateDIBPatternBrush](#createdibpatternbrush)|Bir CİHAZDAN bağımsız bit eşlem (DIB) tarafından belirtilen desenle fırça başlatır.|
|[CBrush::CreateHatchBrush](#createhatchbrush)|Fırça rengi ve belirtilen taranmış deseni ile başlatır.|
|[CBrush::CreatePatternBrush](#createpatternbrush)|Bir bit eşlem tarafından belirtilen desenle fırça başlatır.|
|[CBrush::CreateSolidBrush](#createsolidbrush)|Fırça belirtilen düz renk ile başlatır.|
|[CBrush::CreateSysColorBrush](#createsyscolorbrush)|Varsayılan sistem renkli fırça oluşturur.|
|[CBrush::FromHandle](#fromhandle)|Bir işaretçi döndüren bir `CBrush` nesnesi bir işleyici için bir Windows verildiğinde `HBRUSH` nesne.|
|[CBrush::GetLogBrush](#getlogbrush)|Alır bir [LOGBRUSH](/windows/desktop/api/wingdi/ns-wingdi-taglogbrush) yapısı.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[HBRUSH CBrush::operator](#operator_hbrush)|Bağlı Windows tanıtıcısını döndürür `CBrush` nesne.|

## <a name="remarks"></a>Açıklamalar

Kullanılacak bir `CBrush` nesne, oluşturun bir `CBrush` nesne ve birine geçme `CDC` fırça gerektiren üye işlevi.

Fırçalar çizgili veya desenli düz, olabilir.

Daha fazla bilgi için `CBrush`, bkz: [grafik nesneleri](../../mfc/graphic-objects.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CBrush`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

##  <a name="cbrush"></a>  CBrush::CBrush

Oluşturur bir `CBrush` nesne.

```
CBrush();
CBrush(COLORREF crColor);
CBrush(int nIndex, COLORREF crColor);
explicit CBrush(CBitmap* pBitmap);
```

### <a name="parameters"></a>Parametreler

*crColor*<br/>
Bir RGB rengi fırça ön plan rengini belirtir. Fırça çizgili, bu parametre tarama rengini belirtir.

*nIndex*<br/>
Fırça tarama stilini belirtir. Bu, aşağıdaki değerlerden biri olabilir:

- 45 derecede HS_BDIAGONAL aşağı tarama (soldan sağa)

- HS_CROSS yatay ve dikey çapraz tarama

- HS_DIAGCROSS çapraz tarama 45 derecede

- Yukarı HS_FDIAGONAL tarama (soldan sağa) 45 derecede

- HS_HORIZONTAL yatay tarama

- HS_VERTICAL dikey tarama

*pBitmap*<br/>
İşaret eden bir `CBitmap` nesnesini bir bit eşlem ile fırça boyar belirtir.

### <a name="remarks"></a>Açıklamalar

`CBrush` Dördüncü oluşturucu aşırı yüklü. Oluşturucu bağımsız değişken içermeyen bir başlatılmamış yapıları `CBrush` nesnesi, kullanılmadan önce başlatılmalıdır.

Oluşturucu bağımsız değişken olmadan kullanırsanız, sonuç başlatmalıdır `CBrush` nesnesi ile [CreateSolidBrush](#createsolidbrush), [CreateHatchBrush](#createhatchbrush), [CreateBrushIndirect](#createbrushindirect), [CreatePatternBrush](#createpatternbrush), veya [CreateDIBPatternBrush](#createdibpatternbrush). Bağımsız değişken alan oluşturucular birini kullanırsanız, daha sonra başka başlatma gereklidir. Oluşturucu bağımsız değişken olmadan her zaman başarılı olur ancak, bir hatayla karşılaşılmazsa oluşturucular bağımsız değişken bir özel durum.

Tek bir oluşturucuyla [COLORREF](/windows/desktop/gdi/colorref) parametresi düz fırça belirtilen rengi oluşturur. Renk RGB değeri belirtir ve WINDOWS RGB makroda ile oluşturulabilir. H

İki parametre oluşturucuyla tarama fırça oluşturur. *NIndex* parametresi taranmış bir desen dizinini belirtir. *CrColor* parametresi rengini belirtir.

Oluşturucu bir `CBitmap` parametre desenli fırça oluşturur. Parametresi bir bit eşlem tanımlar. Bit eşlem kullanarak oluşturmuş olduğunuz varsayılır [CBitmap::CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap), [CBitmap::CreateBitmapIndirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect), [CBitmap::LoadBitmap](../../mfc/reference/cbitmap-class.md#loadbitmap), veya [ CBitmap::CreateCompatibleBitmap](../../mfc/reference/cbitmap-class.md#createcompatiblebitmap). En az bir dolgu deseni kullanılacak bir bit eşlem 8 x 8 piksel büyüklüğünde.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#21](../../mfc/codesnippet/cpp/cbrush-class_1.cpp)]

##  <a name="createbrushindirect"></a>  CBrush::CreateBrushIndirect

Fırça stili, renk ve belirtilen desen ile başlatır bir [LOGBRUSH](/windows/desktop/api/wingdi/ns-wingdi-taglogbrush) yapısı.

```
BOOL CreateBrushIndirect(const LOGBRUSH* lpLogBrush);
```

### <a name="parameters"></a>Parametreler

*lpLogBrush*<br/>
İşaret eden bir [LOGBRUSH](/windows/desktop/api/wingdi/ns-wingdi-taglogbrush) fırça hakkında bilgi içeren yapısı.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Fırça sonradan herhangi bir cihaz bağlamı için geçerli fırça olarak seçilebilir.

Geçerli metin ve arkaplan renklerini kullanarak tek renkli (1 düzlemi, 1 bit / piksel) bit eşlemi kullanılarak oluşturulan bir fırça çizilir. Geçerli metin rengi ile 0 olarak ayarlamak biraz tarafından temsil edilen piksel çizilir. 1 olarak ayarlanmış bir bit tarafından temsil edilen piksel arka plan rengiyle çizilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#22](../../mfc/codesnippet/cpp/cbrush-class_2.cpp)]

##  <a name="createdibpatternbrush"></a>  CBrush::CreateDIBPatternBrush

Bir CİHAZDAN bağımsız bit eşlem (DIB) tarafından belirtilen düzene sahip bir fırça başlatır.

```
BOOL CreateDIBPatternBrush(
    HGLOBAL hPackedDIB,
    UINT nUsage);

BOOL CreateDIBPatternBrush(
    const void* lpPackedDIB,
    UINT nUsage);
```

### <a name="parameters"></a>Parametreler

*hPackedDIB*<br/>
Paketlenmiş CİHAZDAN bağımsız bit eşlem (DIB) içeren bir genel bellek nesnesi tanımlar.

*Nkullanım*<br/>
Belirtir olup olmadığını `bmiColors[]` alanlarının [BITMAPINFO](/windows/desktop/api/wingdi/ns-wingdi-tagbitmapinfo) veri yapısı ("DIB paketleneceğini" bir parçası) açık RGB değerleri veya dizinler şu anda gerçekleşen mantıksal paletini içerir. Parametre aşağıdaki değerlerden biri olmalıdır:

- 16-bit dizinleri dizisi DIB_PAL_COLORS renk tablosu oluşur.

- Renk tablosunu DIB_RGB_COLORS değişmez değer RGB değerleri içerir.

*lpPackedDIB*<br/>
İşaret oluşan bir paket DIB bir `BITMAPINFO` bit eşlemin piksel tanımlayan bir bayt dizisi hemen ardından yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Fırça sonradan tarama işlemleri destekleyen herhangi bir cihaz bağlamı için seçilebilir.

İki sürüm DIB işleyecek şekilde farklıdır:

- İlk sürümde DIB için bir tanıtıcı elde etmek için Windows Arama `GlobalAlloc` işlevi genel bellek bloğu ayrılamadı ve sonra bellek paketlenmiş DIB ile doldurun.

- Dosyanın ikinci sürümü çağırmak ise gerekli değildir `GlobalAlloc` paketlenmiş DIB için bellek ayrılamadı.

Paketlenmiş DIB oluşan bir `BITMAPINFO` bit eşlemin piksel tanımlayan bayt dizisi hemen ardından veri yapısı. Dolgu deseni olarak kullanılan bit eşlemleri 8 x 8 piksel olmalıdır. Bit eşlem daha büyük ise, yalnızca ilk 8 satır ve sol üst köşedeki bit eşlemin piksel 8 sütunlarına karşılık gelen BITS kullanarak dolgu deseni Windows oluşturur.

Bir uygulamanın iki renkli DIB Desen fırçası tek renkli cihaz bağlamına seçtiğinde Windows DIB içinde belirtilen renkleri yok sayar ve bunun yerine cihaz bağlamı geçerli metin ve arkaplan renklerini kullanarak Desen fırçası görüntüler. Metin rengi kullanarak DIB (uzaklığındaki 0 DIB renk tablosundaki) ilk renk için eşlenmiş piksel görüntülenir. İkinci rengi (1 uzaklığından renk tablosundaki) eşlenmiş piksel kullanarak arka plan rengi görüntülenir.

Aşağıdaki Windows işlevlerini kullanma hakkında daha fazla bilgi için Windows SDK'sı bakın:

- [CreateDIBPatternBrush](/windows/desktop/api/wingdi/nf-wingdi-createdibpatternbrush) (Bu işlevi yalnızca 3.0'den önceki Windows sürümleri için yazılmış uygulamalarla uyumluluk için sağlanır; kullanın `CreateDIBPatternBrushPt` işlevi.)

- [CreateDIBPatternBrushPt](/windows/desktop/api/wingdi/nf-wingdi-createdibpatternbrushpt) (Win32 tabanlı uygulamalar için bu işlevi kullanılmalıdır.)

- [GlobalAlloc](/windows/desktop/api/winbase/nf-winbase-globalalloc)

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#23](../../mfc/codesnippet/cpp/cbrush-class_3.cpp)]

##  <a name="createhatchbrush"></a>  CBrush::CreateHatchBrush

Fırça rengi ve belirtilen taranmış deseni ile başlatır.

```
BOOL CreateHatchBrush(
    int nIndex,
    COLORREF crColor);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Fırça tarama stilini belirtir. Bu, aşağıdaki değerlerden biri olabilir:

- 45 derecede HS_BDIAGONAL aşağı tarama (soldan sağa)

- HS_CROSS yatay ve dikey çapraz tarama

- HS_DIAGCROSS çapraz tarama 45 derecede

- Yukarı HS_FDIAGONAL tarama (soldan sağa) 45 derecede

- HS_HORIZONTAL yatay tarama

- HS_VERTICAL dikey tarama

*crColor*<br/>
Bir RGB rengi (tarama rengi) fırça ön plan rengini belirtir. Bkz: [COLORREF](/windows/desktop/gdi/colorref) daha fazla bilgi için Windows SDK.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Fırça sonradan herhangi bir cihaz bağlamı için geçerli fırça olarak seçilebilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#24](../../mfc/codesnippet/cpp/cbrush-class_4.cpp)]

##  <a name="createpatternbrush"></a>  CBrush::CreatePatternBrush

Bir bit eşlem tarafından belirtilen desenle fırça başlatır.

```
BOOL CreatePatternBrush(CBitmap* pBitmap);
```

### <a name="parameters"></a>Parametreler

*pBitmap*<br/>
Bir bit eşlem tanımlar.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Fırça sonradan tarama işlemleri destekleyen herhangi bir cihaz bağlamı için seçilebilir. Tarafından belirtilen bit eşlem *pBitmap* genellikle kullanılarak başlatılan [CBitmap::CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap), [CBitmap::CreateBitmapIndirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect), [CBitmap:: LoadBitmap](../../mfc/reference/cbitmap-class.md#loadbitmap), veya [CBitmap::CreateCompatibleBitmap](../../mfc/reference/cbitmap-class.md#createcompatiblebitmap) işlevi.

Dolgu deseni olarak kullanılan bit eşlemleri 8 x 8 piksel olmalıdır. Bit eşlem büyükse, Windows, yalnızca ilk 8 satırları ve sütunları sol üst köşedeki bit eşlemin piksel karşılık gelen bit kullanır.

Bir desen Fırçası ilişkili bir eşlem etkilemeden silinebilir. Başka bir deyişle, bit eşlemi Desen fırçaları herhangi bir sayıda oluşturmak için kullanılabilir.

Geçerli metin ve arkaplan renklerini kullanarak tek renkli bir bit eşlem (1 Renk düzlemi, 1 bit / piksel) kullanılarak oluşturulan bir fırça çizilir. Piksel 0 olarak ayarlamak biraz tarafından temsil edilen geçerli metin rengi ile çizilir. 1 olarak ayarlanmış bir bit tarafından temsil edilen piksel arka plan rengiyle çizilir.

Kullanma hakkında bilgi için [CreatePatternBrush](/windows/desktop/api/wingdi/nf-wingdi-createpatternbrush), bir Windows işlevi, Windows SDK'sı bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#25](../../mfc/codesnippet/cpp/cbrush-class_5.cpp)]

##  <a name="createsolidbrush"></a>  CBrush::CreateSolidBrush

Belirtilen düz renk ile bir fırça başlatır.

```
BOOL CreateSolidBrush(COLORREF crColor);
```

### <a name="parameters"></a>Parametreler

*crColor*<br/>
A [COLORREF](/windows/desktop/gdi/colorref) yapısı fırça rengini belirtir. Renk RGB değeri belirtir ve WINDOWS RGB makroda ile oluşturulabilir. H

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Fırça sonradan herhangi bir cihaz bağlamı için geçerli fırça olarak seçilebilir.

Bir uygulama bittiğinde tarafından oluşturulan fırça kullanarak `CreateSolidBrush`, cihaz bağlam dışında fırça seçmeniz gerekir.

### <a name="example"></a>Örnek

  Örneğin bakın [CBrush::CBrush](#cbrush).

##  <a name="createsyscolorbrush"></a>  CBrush::CreateSysColorBrush

Fırça Rengi başlatır.

```
BOOL CreateSysColorBrush(int nIndex);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Renk dizini belirtir. Bu değer bir 21 pencere öğeleri boyamak için kullanılan renge karşılık gelir. Bkz: [GetSysColor](/windows/desktop/api/winuser/nf-winuser-getsyscolor) değerlerin listesi için Windows SDK.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Fırça sonradan herhangi bir cihaz bağlamı için geçerli fırça olarak seçilebilir.

Bir uygulama bittiğinde tarafından oluşturulan fırça kullanarak `CreateSysColorBrush`, cihaz bağlam dışında fırça seçmeniz gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#26](../../mfc/codesnippet/cpp/cbrush-class_6.cpp)]

##  <a name="fromhandle"></a>  CBrush::FromHandle

Bir işaretçi döndüren bir `CBrush` nesnesi bir işleyici için bir Windows verildiğinde [HBRUSH](#operator_hbrush) nesne.

```
static CBrush* PASCAL FromHandle(HBRUSH hBrush);
```

### <a name="parameters"></a>Parametreler

*hBrush*<br/>
Windows GDI fırça İŞLEYİN.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir `CBrush` nesne başarılı; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Varsa bir `CBrush` nesne zaten iliştirilmemiş tanıtıcı, geçici bir `CBrush` nesnesi oluşturulur ve bağlı. Bu geçici `CBrush` nesne geçerli uygulamanın kendi olay döngüsü içinde boşta kalma süresi varsa yalnızca zamana kadar. Şu anda tüm geçici grafik nesneler silinir. Diğer bir deyişle, yalnızca bir pencere ileti işleme sırasında geçici nesne geçerli değil.

Grafik nesneler kullanma hakkında daha fazla bilgi için bkz. [grafik nesneleri](/windows/desktop/gdi/graphic-objects) Windows SDK.

### <a name="example"></a>Örnek

  Örneğin bakın [CBrush::CBrush](#cbrush).

##  <a name="getlogbrush"></a>  CBrush::GetLogBrush

Almak için bu üye işlevi çağrısı `LOGBRUSH` yapısı.

```
int GetLogBrush(LOGBRUSH* pLogBrush);
```

### <a name="parameters"></a>Parametreler

*pLogBrush*<br/>
İşaret eden bir [LOGBRUSH](/windows/desktop/api/wingdi/ns-wingdi-taglogbrush) fırça hakkında bilgi içeren yapısı.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa ve *pLogBrush* geçerli bir işaretçi dönüş değeri arabelleğe depolanan bayt sayısıdır.

İşlev başarılı olursa ve *pLogBrush* NULL ise işlev bilgileri tutmak için gereken bayt sayısını arabelleğe depolamak değer döndürülür.

İşlev başarısız olursa, dönüş değeri 0'dır.

### <a name="remarks"></a>Açıklamalar

`LOGBRUSH` Yapısı, stil, rengini ve fırça deseni tanımlar.

Örneğin, çağrı `GetLogBrush` belirli renk ya da bir bit eşlem desenini eşleştirmek için.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#27](../../mfc/codesnippet/cpp/cbrush-class_7.cpp)]

##  <a name="operator_hbrush"></a>  HBRUSH CBrush::operator

Ekli Windows GDI tanıtıcısını almak için bu işleci kullanın `CBrush` nesne.

```
operator HBRUSH() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı, Windows GDI nesnesi için bir tanıtıcı tarafından temsil edilen varsa `CBrush` nesne; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

HBRUSH nesne doğrudan kullanımını destekleyen bir yayım işleciyle işlecidir.

Grafik nesneler kullanma hakkında daha fazla bilgi için bkz. [grafik nesneleri](/windows/desktop/gdi/graphic-objects) Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#28](../../mfc/codesnippet/cpp/cbrush-class_8.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek PROPDLG](../../overview/visual-cpp-samples.md)<br/>
[CGdiObject Sınıfı](../../mfc/reference/cgdiobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CBitmap Sınıfı](../../mfc/reference/cbitmap-class.md)<br/>
[CDC Sınıfı](../../mfc/reference/cdc-class.md)
