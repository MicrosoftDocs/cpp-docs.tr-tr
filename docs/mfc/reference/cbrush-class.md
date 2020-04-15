---
title: CBrush Sınıfı
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
ms.openlocfilehash: 15132bb5497886638edfe431ae769dd446785df8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81352488"
---
# <a name="cbrush-class"></a>CBrush Sınıfı

Bir Windows grafik aygıtı arabirimi (GDI) fırçası kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CBrush : public CGdiObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CBrush::CBrush](#cbrush)|Bir `CBrush` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CBrush::CreateBrushIndirect](#createbrushindirect)|Bir [LOGBRUSH](/windows/win32/api/wingdi/ns-wingdi-logbrush) yapısında belirtilen stil, renk ve desenle bir fırçayı başharfe ait hale sağlar.|
|[CBrush::CreateDIBPatternBrush](#createdibpatternbrush)|Aygıttan bağımsız bitmap (DIB) tarafından belirtilen desenle fırçayı başolarak adlandırır.|
|[CBrush::CreateHatchBrush](#createhatchbrush)|Belirtilen yumurtadan çıkmış desen ve renk ile bir fırça başharfleri.|
|[CBrush::CreatePatternBrush](#createpatternbrush)|Bir fırçayı bitmap tarafından belirtilen desenle başolarak karşılar.|
|[CBrush::CreateSolidBrush](#createsolidbrush)|Belirtilen düz renkle bir fırçayı başharfe ait hale.|
|[CBrush::CreateSysColorBrush](#createsyscolorbrush)|Varsayılan sistem rengi olan bir fırça oluşturur.|
|[CBrush::FromHandle](#fromhandle)|Bir Windows `CBrush` `HBRUSH` nesnesine tanıtıcı verildiğinde bir işaretçiyi nesneye döndürür.|
|[CBrush::GetLogBrush](#getlogbrush)|[LOGBRUSH](/windows/win32/api/wingdi/ns-wingdi-logbrush) yapısı alır.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CBrush::operatör HBRUSH](#operator_hbrush)|Nesneye bağlı Windows tutamacını `CBrush` döndürür.|

## <a name="remarks"></a>Açıklamalar

Bir `CBrush` nesneyi kullanmak `CBrush` için, bir nesne `CDC` oluşturmak ve fırça gerektiren herhangi bir üye işlev için geçirin.

Fırçalar katı, yumurtadan veya desenli olabilir.

Daha fazla `CBrush`bilgi için [Bkz. Grafik Nesneler.](../../mfc/graphic-objects.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Cgdiobject](../../mfc/reference/cgdiobject-class.md)

`CBrush`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="cbrushcbrush"></a><a name="cbrush"></a>CBrush::CBrush

Bir `CBrush` nesne inşa eder.

```
CBrush();
CBrush(COLORREF crColor);
CBrush(int nIndex, COLORREF crColor);
explicit CBrush(CBitmap* pBitmap);
```

### <a name="parameters"></a>Parametreler

*crColor*<br/>
Fırçanın ön plan rengini RGB rengi olarak belirtir. Fırça yumurtadan çıkarsa, bu parametre kapağın rengini belirtir.

*Nındex*<br/>
Fırçanın kapak stilini belirtir. Aşağıdaki değerlerden herhangi biri olabilir:

- 45 derece aşağı kapak (soldan sağa) HS_BDIAGONAL

- HS_CROSS Yatay ve dikey çapraz kapak

- 45 derece de Crosshatch HS_DIAGCROSS

- HS_FDIAGONAL Yukarı kapak (soldan sağa) 45 derece

- HS_HORIZONTAL Yatay kapak

- HS_VERTICAL Dikey kapak

*pBitmap*<br/>
Fırçanın `CBitmap` boyadığı bir bit eşlemi belirten bir nesneyi işaret eder.

### <a name="remarks"></a>Açıklamalar

`CBrush`dört aşırı yüklü yapıcıları vardır. Bağımsız değişkeni olmayan oluşturucu, kullanılmadan önce başharflere geçilmesi gereken baş harflere getirilmemiş `CBrush` bir nesne inşa eder.

Hiçbir bağımsız değişken `CBrush` ile oluşturucu kullanıyorsanız, [CreateSolidBrush](#createsolidbrush)ile ortaya çıkan nesne başlatmanız gerekir , [CreateHatchBrush](#createhatchbrush), [CreateBrushIndirect](#createbrushindirect), [CreatePatternBrush](#createpatternbrush), veya [CreateDIBPatternBrush](#createdibpatternbrush). Bağımsız değişkenleri alan oluşturuculardan birini kullanıyorsanız, başka bir başlatma gerekmez. Bağımsız değişkenleri olan yapıcılar hatalarla karşılaşılırsa bir özel durum atabilir, bağımsız değişkeni olmayan yapıcı ise her zaman başarılı olur.

Tek bir [COLORREF](/windows/win32/gdi/colorref) parametresi olan yapıcı, belirtilen renge sahip katı bir fırça yıkıyor. Renk bir RGB değeri belirtir ve WINDOWS'da RGB makrosu ile oluşturulabilir. H.

İki parametreli yapıcı bir kapak fırçası inşa eder. *nIndex* parametresi, yumurtadan çıkan bir desenin dizinini belirtir. *crColor* parametresi rengi belirtir.

`CBitmap` Parametreli yapıcı desenli bir fırça inşa eder. Parametre bir bit eşlemi tanımlar. Bitmap'in [CBitmap::CreateBitmap,](../../mfc/reference/cbitmap-class.md#createbitmap) [CBitmap::CreateBitmap,](../../mfc/reference/cbitmap-class.md#createbitmapindirect) [CBitmap::LoadBitmap](../../mfc/reference/cbitmap-class.md#loadbitmap)veya [CBitmap::CreateCompatibleBitmap](../../mfc/reference/cbitmap-class.md#createcompatiblebitmap)kullanılarak oluşturulduğu varsayılır. Dolgu deseninde kullanılacak bit eşlemi için minimum boyut 8 piksele 8 pikseldir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#21](../../mfc/codesnippet/cpp/cbrush-class_1.cpp)]

## <a name="cbrushcreatebrushindirect"></a><a name="createbrushindirect"></a>CBrush::CreateBrushIndirect

Bir [LOGBRUSH](/windows/win32/api/wingdi/ns-wingdi-logbrush) yapısında belirtilen stil, renk ve desenle fırçayı başolarak açar.

```
BOOL CreateBrushIndirect(const LOGBRUSH* lpLogBrush);
```

### <a name="parameters"></a>Parametreler

*lpLogBrush*<br/>
Fırça hakkında bilgi içeren bir [LOGBRUSH](/windows/win32/api/wingdi/ns-wingdi-logbrush) yapısına işaret edin.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Fırça daha sonra herhangi bir aygıt bağlamı için geçerli fırça olarak seçilebilir.

Tek renkli (1 düzlem, piksel başına 1 bit) bit eşlemi kullanılarak oluşturulan bir fırça, geçerli metin ve arka plan renkleri kullanılarak çizilir. Bir bit ile 0 olarak ayarlanmış pikseller geçerli metin rengiyle çizilir. 1'e ayarlanmış bir bitle temsil edilen pikseller, geçerli arka plan rengiyle birlikte çizilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#22](../../mfc/codesnippet/cpp/cbrush-class_2.cpp)]

## <a name="cbrushcreatedibpatternbrush"></a><a name="createdibpatternbrush"></a>CBrush::CreateDIBPatternBrush

Aygıttan bağımsız bitmap (DIB) tarafından belirtilen desenle bir fırçayı başolarak adlandırır.

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
Paketlenmiş aygıtbağımsız bit eşlemi (DIB) içeren genel bellek nesnesi tanımlar.

*nKullanım*<br/>
[BITMAPINFO](/windows/win32/api/wingdi/ns-wingdi-bitmapinfo) veri `bmiColors[]` yapısıalanlarının ("paketlenmiş DIB"nin bir parçası) açık RGB değerleri veya indeksleri şu anda gerçekleştirilen mantıksal palete dahil edip etmediğini belirtir. Parametre aşağıdaki değerlerden biri olmalıdır:

- DIB_PAL_COLORS Renk tablosu 16 bit dizinler dizisinden oluşur.

- DIB_RGB_COLORS Renk tablosu gerçek RGB değerleri içerir.

*lpPackedDIB*<br/>
Bit haritasının piksellerini tanımlayan bir `BITMAPINFO` dizi baytın hemen ardından bir yapıdan oluşan paketlenmiş bir DIB'ye işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Fırça daha sonra raster işlemlerini destekleyen herhangi bir aygıt bağlamı için seçilebilir.

İki sürüm, DIB'yi işleme şeklinize göre farklılık gösterir:

- İlk sürümde, DIB'ye bir tanıtıcı elde `GlobalAlloc` etmek için, windows işlevini arayarak bir genel bellek bloğunu ayırın ve ardından belleği paketlenmiş DIB ile doldurun.

- İkinci sürümde, paketlenmiş DIB `GlobalAlloc` için bellek ayırmak için aramak gerekli değildir.

Paketlenmiş DIB, bit `BITMAPINFO` eşizin piksellerini tanımlayan bayt dizisini hemen izleyen bir veri yapısından oluşur. Dolgu deseni olarak kullanılan bit eşlemler 8 piksele 8 piksel olmalıdır. Bit eşlemi daha büyükse, Windows bit eşleninin sol üst köşesindeki ilk 8 satır ve 8 piksel sütununa karşılık gelen bitleri kullanarak bir dolgu deseni oluşturur.

Bir uygulama tek renkli aygıt bağlamına iki renkli DIB desen fırçası seçtiğinde, Windows DIB'de belirtilen renkleri yoksa ve bunun yerine aygıt bağlamının geçerli metnini ve arka plan renklerini kullanarak desen fırçasını görüntüler. DIB'nin ilk color'una eşlenen pikseller (DIB renk tablosunda ofset 0'da) metin rengi kullanılarak görüntülenir. İkinci renge eşlenen pikseller (renk tablosundaki ofset 1'de) arka plan rengi kullanılarak görüntülenir.

Aşağıdaki Windows işlevlerini kullanma hakkında daha fazla bilgi için Windows SDK'ya bakın:

- [CreateDIBPatternBrush](/windows/win32/api/wingdi/nf-wingdi-createdibpatternbrush) (Bu işlev yalnızca Windows'un 3.0'dan önceki sürümleri için yazılmış `CreateDIBPatternBrushPt` uygulamalarla uyumluluk için sağlanır;

- [CreateDIBPatternBrushPt](/windows/win32/api/wingdi/nf-wingdi-createdibpatternbrushpt) (Bu işlev Win32 tabanlı uygulamalar için kullanılmalıdır.)

- [Globalalloc](/windows/win32/api/winbase/nf-winbase-globalalloc)

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#23](../../mfc/codesnippet/cpp/cbrush-class_3.cpp)]

## <a name="cbrushcreatehatchbrush"></a><a name="createhatchbrush"></a>CBrush::CreateHatchBrush

Belirtilen yumurtadan çıkmış desen ve renk ile bir fırça başharfleri.

```
BOOL CreateHatchBrush(
    int nIndex,
    COLORREF crColor);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Fırçanın kapak stilini belirtir. Aşağıdaki değerlerden herhangi biri olabilir:

- 45 derece aşağı kapak (soldan sağa) HS_BDIAGONAL

- HS_CROSS Yatay ve dikey çapraz kapak

- 45 derece de Crosshatch HS_DIAGCROSS

- HS_FDIAGONAL Yukarı kapak (soldan sağa) 45 derece

- HS_HORIZONTAL Yatay kapak

- HS_VERTICAL Dikey kapak

*crColor*<br/>
Fırçanın ön plan rengini RGB rengi (kapakların rengi) olarak belirtir. Daha fazla bilgi için Windows SDK'daki [COLORREF'a](/windows/win32/gdi/colorref) bakın.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Fırça daha sonra herhangi bir aygıt bağlamı için geçerli fırça olarak seçilebilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#24](../../mfc/codesnippet/cpp/cbrush-class_4.cpp)]

## <a name="cbrushcreatepatternbrush"></a><a name="createpatternbrush"></a>CBrush::CreatePatternBrush

Bir fırçayı bitmap tarafından belirtilen desenle başolarak karşılar.

```
BOOL CreatePatternBrush(CBitmap* pBitmap);
```

### <a name="parameters"></a>Parametreler

*pBitmap*<br/>
Bir bit eşlemi tanımlar.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Fırça daha sonra raster işlemlerini destekleyen herhangi bir aygıt bağlamı için seçilebilir. *pBitmap* tarafından tanımlanan bitmap genellikle [CBitmap kullanılarak başharflenir::CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap), [CBitmap::CreateBitmapIndirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect), [CBitmap::LoadBitmap](../../mfc/reference/cbitmap-class.md#loadbitmap), veya [CBitmap::CreateCompatibleBitmap](../../mfc/reference/cbitmap-class.md#createcompatiblebitmap) işlevi.

Dolgu deseni olarak kullanılan bit eşlemler 8 piksele 8 piksel olmalıdır. Bit eşlemi daha büyükse, Windows yalnızca bit eşleninin sol üst köşesindeki ilk 8 satır ve piksel sütununa karşılık gelen bitleri kullanır.

Bir desen fırçası ilişkili bit eşlemi etkilemeden silinebilir. Bu, bit eşleninin herhangi bir sayıda desen fırçası oluşturmak için kullanAbileceği anlamına gelir.

Tek renkli bit eşlemi (1 renkli düzlem, piksel başına 1 bit) kullanılarak oluşturulan bir fırça, geçerli metin ve arka plan renkleri kullanılarak çizilir. Bir bit ile 0 olarak ayarlanmış pikseller geçerli metin rengiyle çizilir. 1'e ayarlanmış bir bitle temsil edilen pikseller geçerli arka plan rengiyle çizilir.

Windows işlevi [olan CreatePatternBrush'ı](/windows/win32/api/wingdi/nf-wingdi-createpatternbrush)kullanma hakkında daha fazla bilgi için Windows SDK'ya bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#25](../../mfc/codesnippet/cpp/cbrush-class_5.cpp)]

## <a name="cbrushcreatesolidbrush"></a><a name="createsolidbrush"></a>CBrush::CreateSolidBrush

Belirli bir düz renkle bir fırçayı başharfe ait hale.

```
BOOL CreateSolidBrush(COLORREF crColor);
```

### <a name="parameters"></a>Parametreler

*crColor*<br/>
Fırçanın rengini belirten bir [COLORREF](/windows/win32/gdi/colorref) yapısı. Renk bir RGB değeri belirtir ve WINDOWS'da RGB makrosu ile oluşturulabilir. H.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Fırça daha sonra herhangi bir aygıt bağlamı için geçerli fırça olarak seçilebilir.

Bir uygulama tarafından `CreateSolidBrush`oluşturulan fırçayı kullanarak tamamlandığında, fırçayı aygıt bağlamının dışına seçmelidir.

### <a name="example"></a>Örnek

  CBrush örneğine [bakın:CBrush.](#cbrush)

## <a name="cbrushcreatesyscolorbrush"></a><a name="createsyscolorbrush"></a>CBrush::CreateSysColorBrush

Fırça rengini başharfe ait hale.

```
BOOL CreateSysColorBrush(int nIndex);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Renk dizini belirtir. Bu değer, 21 pencere öğesinden birini boyamak için kullanılan renge karşılık gelir. Değerler listesi için Windows SDK'daki [GetSysColor'a](/windows/win32/api/winuser/nf-winuser-getsyscolor) bakın.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Fırça daha sonra herhangi bir aygıt bağlamı için geçerli fırça olarak seçilebilir.

Bir uygulama tarafından `CreateSysColorBrush`oluşturulan fırçayı kullanarak tamamlandığında, fırçayı aygıt bağlamının dışına seçmelidir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#26](../../mfc/codesnippet/cpp/cbrush-class_6.cpp)]

## <a name="cbrushfromhandle"></a><a name="fromhandle"></a>CBrush::FromHandle

Bir Windows `CBrush` [HBRUSH](#operator_hbrush) nesnesine tutamacı verildiğinde bir işaretçiyi nesneye döndürür.

```
static CBrush* PASCAL FromHandle(HBRUSH hBrush);
```

### <a name="parameters"></a>Parametreler

*hFırça*<br/>
Windows GDI fırçasına HANDLE.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa `CBrush` nesneye işaretçi; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Bir `CBrush` nesne tutamacına zaten eklenmiş değilse, geçici `CBrush` bir nesne oluşturulur ve eklenir. Bu `CBrush` geçici nesne yalnızca uygulamanın olay döngüsünde boşta kalma süresi olana kadar geçerlidir. Şu anda, tüm geçici grafik nesneleri silinir. Başka bir deyişle, geçici nesne yalnızca bir pencere iletisinin işlenmesi sırasında geçerlidir.

Grafik nesneleri kullanma hakkında daha fazla bilgi için Windows SDK'daki [Grafik Nesneler'e](/windows/win32/gdi/graphic-objects) bakın.

### <a name="example"></a>Örnek

  CBrush örneğine [bakın:CBrush.](#cbrush)

## <a name="cbrushgetlogbrush"></a><a name="getlogbrush"></a>CBrush::GetLogBrush

Yapıyı `LOGBRUSH` almak için bu üye işlevi arayın.

```
int GetLogBrush(LOGBRUSH* pLogBrush);
```

### <a name="parameters"></a>Parametreler

*pLogBrush*<br/>
Fırça hakkında bilgi içeren bir [LOGBRUSH](/windows/win32/api/wingdi/ns-wingdi-logbrush) yapısına işaret edin.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa ve *pLogBrush* geçerli bir işaretçiyse, iade değeri arabellekte depolanan bayt sayısıdır.

İşlev başarılı olursa ve *pLogBrush* NULL ise, döndürme değeri, işlevin arabellekte depolayacağınız bilgileri tutmak için gereken bayt sayısıdır.

İşlev başarısız olursa, iade değeri 0'dır.

### <a name="remarks"></a>Açıklamalar

Yapı, `LOGBRUSH` fırçanın stilini, rengini ve deseni tanımlar.

Örneğin, bir `GetLogBrush` bit eşleminin belirli renk veya deseniyle eşleşmek için arayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#27](../../mfc/codesnippet/cpp/cbrush-class_7.cpp)]

## <a name="cbrushoperator-hbrush"></a><a name="operator_hbrush"></a>CBrush::operatör HBRUSH

`CBrush` Nesnenin ekli Windows GDI tutamacını almak için bu işleci kullanın.

```
operator HBRUSH() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, nesne tarafından temsil edilen Windows `CBrush` GDI nesnesine bir tanıtıcı; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Bu işleç, bir HBRUSH nesnesinin doğrudan kullanımını destekleyen bir döküm operatörüdür.

Grafik nesneleri kullanma hakkında daha fazla bilgi için Windows SDK'daki [Grafik Nesneler'e](/windows/win32/gdi/graphic-objects) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#28](../../mfc/codesnippet/cpp/cbrush-class_8.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek PROPDLG](../../overview/visual-cpp-samples.md)<br/>
[CGdiObject Sınıfı](../../mfc/reference/cgdiobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CBitmap Sınıfı](../../mfc/reference/cbitmap-class.md)<br/>
[CDC Sınıfı](../../mfc/reference/cdc-class.md)
