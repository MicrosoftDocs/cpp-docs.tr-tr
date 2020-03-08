---
title: CBrush sınıfı
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
ms.openlocfilehash: a99d8c8022d23f627320b66c3f376be803c9c839
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78876054"
---
# <a name="cbrush-class"></a>CBrush sınıfı

Bir Windows grafik cihaz arabirimi (GDI) fırçası kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CBrush : public CGdiObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CBrush:: CBrush](#cbrush)|`CBrush` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CBrush:: Createbrühdolaylı](#createbrushindirect)|[LOGBRUSH](/windows/win32/api/wingdi/ns-wingdi-logbrush) yapısında belirtilen stili, rengi ve kalıbı içeren bir fırça başlatır.|
|[CBrush:: CreateDIBPatternBrush](#createdibpatternbrush)|Cihazdan bağımsız bir bit eşlem (DIB) tarafından belirtilen bir desenli fırçayı başlatır.|
|[CBrush:: CreateHatchBrush](#createhatchbrush)|Belirtilen taranmış düzene ve renge sahip bir fırça başlatır.|
|[CBrush:: CreatePatternBrush](#createpatternbrush)|Bit eşlemle belirtilen bir fırça ile bir fırça başlatır.|
|[CBrush:: Createkesintisdbrush](#createsolidbrush)|Belirtilen düz renge sahip bir fırça başlatır.|
|[CBrush:: CreateSysColorBrush](#createsyscolorbrush)|Varsayılan sistem rengi olan bir fırça oluşturur.|
|[CBrush:: FromHandle](#fromhandle)|Bir Windows `HBRUSH` nesnesine bir tanıtıcı verildiğinde `CBrush` nesnesine yönelik bir işaretçi döndürür.|
|[CBrush:: GetLogBrush](#getlogbrush)|[LOGBRUSH](/windows/win32/api/wingdi/ns-wingdi-logbrush) yapısını alır.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CBrush:: operator HBRUSH](#operator_hbrush)|`CBrush` nesnesine eklenen Windows işleyicisini döndürür.|

## <a name="remarks"></a>Açıklamalar

`CBrush` nesnesini kullanmak için, bir `CBrush` nesnesi oluşturun ve bunu fırça gerektiren `CDC` üye işlevine geçirin.

Fırçalar düz, taranmış veya desenli olabilir.

`CBrush`hakkında daha fazla bilgi için bkz. [grafik nesneleri](../../mfc/graphic-objects.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CBrush`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

##  <a name="cbrush"></a>CBrush:: CBrush

`CBrush` nesnesi oluşturur.

```
CBrush();
CBrush(COLORREF crColor);
CBrush(int nIndex, COLORREF crColor);
explicit CBrush(CBitmap* pBitmap);
```

### <a name="parameters"></a>Parametreler

*crColor*<br/>
Fırçanın bir RGB rengi olarak ön plan rengini belirtir. Fırça, bu parametre, tarama rengini belirtir.

*nDizin*<br/>
Fırçanın tarama stilini belirtir. Aşağıdaki değerlerden herhangi biri olabilir:

- 45 derece HS_BDIAGONAL aşağı doğru tarama (soldan sağa)

- HS_CROSS yatay ve dikey çapraz tarama

- 45 derece HS_DIAGCROSS çapraz tarama

- 45 derece HS_FDIAGONAL yukarı doğru tarama (soldan sağa)

- Yatay tarama HS_HORIZONTAL

- Dikey tarama HS_VERTICAL

*Pbımap*<br/>
Fırçanın boyayan bir bit eşlem belirten `CBitmap` nesnesine işaret eder.

### <a name="remarks"></a>Açıklamalar

`CBrush` dört aşırı yüklenmiş Oluşturucu içerir. Bağımsız değişken içermeyen Oluşturucu, kullanılmadan önce başlatılması gereken başlatılmamış bir `CBrush` nesnesi oluşturur.

Oluşturucuyu bağımsız değişken olmadan kullanırsanız, elde edilen `CBrush` nesnesini [CreateSolidBrush](#createsolidbrush), [CreateHatchBrush](#createhatchbrush), [createbrühdolaylı](#createbrushindirect), [CreatePatternBrush](#createpatternbrush)veya [createdibpatternbrush](#createdibpatternbrush)ile başlatmalısınız. Bağımsız değişken alan oluşturuculardan birini kullanırsanız, başka bir başlatma gerekmez. Bağımsız değişken içermeyen Oluşturucu her zaman başarılı olursa, bağımsız değişkenlere sahip oluşturucular bir özel durum oluşturabilir.

Tek bir [colorref](/windows/win32/gdi/colorref) parametresine sahip Oluşturucu belirtilen renge sahip düz bir fırça oluşturur. Renk bir RGB değeri belirtir ve WINDOWS 'da RGB makrosu ile oluşturulabilir. Olsun.

İki parametreli Oluşturucu bir tarama fırçası oluşturur. *NIndex* parametresi, bir hadallanmış düzenin dizinini belirtir. *CrColor* parametresi rengi belirtir.

`CBitmap` parametresine sahip Oluşturucu bir desenli fırça oluşturur. Parametresi bir bit eşlemi tanımlar. Bit eşlemin [CBitmap:: CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap), [CBitmap:: createbitmapdolaylı](../../mfc/reference/cbitmap-class.md#createbitmapindirect), [CBitmap:: LoadBitmap](../../mfc/reference/cbitmap-class.md#loadbitmap)veya [CBitmap:: CreateCompatibleBitmap](../../mfc/reference/cbitmap-class.md#createcompatiblebitmap)kullanılarak oluşturulmuş olduğu varsayılır. Bir bir bit eşlemin, bir Fill düzeninde kullanılacak en küçük boyutu 8 piksel 8 pikseldir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#21](../../mfc/codesnippet/cpp/cbrush-class_1.cpp)]

##  <a name="createbrushindirect"></a>CBrush:: Createbrühdolaylı

[LOGBRUSH](/windows/win32/api/wingdi/ns-wingdi-logbrush) yapısında belirtilen stili, rengi ve kalıbı içeren bir fırça başlatır.

```
BOOL CreateBrushIndirect(const LOGBRUSH* lpLogBrush);
```

### <a name="parameters"></a>Parametreler

*lpLogBrush*<br/>
Fırça hakkında bilgi içeren bir [LOGBRUSH](/windows/win32/api/wingdi/ns-wingdi-logbrush) yapısına işaret eder.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Fırça daha sonra herhangi bir cihaz bağlamı için geçerli fırça olarak seçilebilir.

Geçerli metin ve arka plan renkleri kullanılarak tek renkli (1 düzlem, piksel başına 1 bit) bit eşlem kullanılarak oluşturulan bir fırça çizilir. Bit olarak 0 olarak ayarlanan piksel, geçerli metin rengiyle çizilir. 1 olarak ayarlanan bit olarak temsil edilen pikseller geçerli arka plan rengiyle çizilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#22](../../mfc/codesnippet/cpp/cbrush-class_2.cpp)]

##  <a name="createdibpatternbrush"></a>CBrush:: CreateDIBPatternBrush

Cihazdan bağımsız bir bit eşlem (DIB) tarafından belirtilen desenli bir fırça başlatır.

```
BOOL CreateDIBPatternBrush(
    HGLOBAL hPackedDIB,
    UINT nUsage);

BOOL CreateDIBPatternBrush(
    const void* lpPackedDIB,
    UINT nUsage);
```

### <a name="parameters"></a>Parametreler

*Hpackeddıb*<br/>
Paketlenmiş cihazdan bağımsız bit eşlem (DIB) içeren bir genel bellek nesnesini tanımlar.

*nKullanım*<br/>
[Bitmapınfo](/windows/win32/api/wingdi/ns-wingdi-bitmapinfo) veri yapısının ("Paketlenmiş DIB" bir parçası) `bmiColors[]` alanlarının, gerçekleştirilmiş olan mantıksal palete açık RGB değerleri veya dizinleri içerip içermediğini belirtir. Parametre aşağıdaki değerlerden biri olmalıdır:

- DIB_PAL_COLORS renk tablosu, 16 bit dizinlerden oluşan bir diziden oluşur.

- DIB_RGB_COLORS renk tablosu sabit RGB değerleri içerir.

*Lppackeddıb*<br/>
Bir `BITMAPINFO` yapısından oluşan paketlenmiş bir DIB 'ye işaret eder ve hemen ardından bit eşlemin piksellerini tanımlayan bir bayt dizisi gelir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Fırça daha sonra Raster işlemlerini destekleyen herhangi bir cihaz bağlamı için seçilebilir.

İki sürüm, DIB 'yi nasıl işleytiğinize göre farklılık gösterir:

- İlk sürümde, DIB 'ye bir tanıtıcı almak için, bir genel bellek bloğu ayırmak ve sonra Paketlenmiş DIB ile belleği doldurmanız için Windows `GlobalAlloc` işlevini çağırın.

- İkinci sürümde, Paketlenmiş DIB için bellek ayırmak üzere `GlobalAlloc` çağırmak gerekli değildir.

Paketlenmiş bir DIB, hemen ardından bir `BITMAPINFO` veri yapısından oluşur ve ardından, bit eşlemin piksellerini tanımlayan bayt dizisini izler. Fill desenleri olarak kullanılan bit eşlemler 8 piksel olmalıdır. Bit eşlem daha büyükse, Windows yalnızca ilk 8 satıra karşılık gelen bitleri ve bit eşlemin sol üst köşesindeki 8 sütun pikseli kullanarak bir Fill stili oluşturur.

Bir uygulama iki renkli bir DIB örüntüsünün tek renkli bir cihaz bağlamına seçtiği zaman, Windows, DIB 'de belirtilen renkleri yoksayar ve bunun yerine, cihaz bağlamının geçerli metin ve arka plan renklerini kullanarak kalıp fırçayı görüntüler. DIB 'nin ilk rengine eşlenen pikseller (DIB Color tablosundaki 0. uzaklığında) metin rengi kullanılarak görüntülenir. İkinci renkle eşlenen pikseller (renk tablosundaki 1. uzaklığında) arka plan rengi kullanılarak görüntülenir.

Aşağıdaki Windows işlevlerini kullanma hakkında daha fazla bilgi için Windows SDK bakın:

- [Createdibpatternbrush](/windows/win32/api/wingdi/nf-wingdi-createdibpatternbrush) (Bu işlev yalnızca 3,0 'Den önceki Windows sürümleri için yazılmış uygulamalarla uyumluluk için sağlanır; `CreateDIBPatternBrushPt` işlevini kullanın.)

- [Createdibpatternbrühpt](/windows/win32/api/wingdi/nf-wingdi-createdibpatternbrushpt) (Bu işlev Win32 tabanlı uygulamalar için kullanılmalıdır.)

- [GlobalAlloc](/windows/win32/api/winbase/nf-winbase-globalalloc)

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#23](../../mfc/codesnippet/cpp/cbrush-class_3.cpp)]

##  <a name="createhatchbrush"></a>CBrush:: CreateHatchBrush

Belirtilen taranmış düzene ve renge sahip bir fırça başlatır.

```
BOOL CreateHatchBrush(
    int nIndex,
    COLORREF crColor);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Fırçanın tarama stilini belirtir. Aşağıdaki değerlerden herhangi biri olabilir:

- 45 derece HS_BDIAGONAL aşağı doğru tarama (soldan sağa)

- HS_CROSS yatay ve dikey çapraz tarama

- 45 derece HS_DIAGCROSS çapraz tarama

- 45 derece HS_FDIAGONAL yukarı doğru tarama (soldan sağa)

- Yatay tarama HS_HORIZONTAL

- Dikey tarama HS_VERTICAL

*crColor*<br/>
Fırçanın bir RGB rengi (tarama rengi) olarak ön plan rengini belirtir. Daha fazla bilgi için Windows SDK [colorref](/windows/win32/gdi/colorref) bölümüne bakın.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Fırça daha sonra herhangi bir cihaz bağlamı için geçerli fırça olarak seçilebilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#24](../../mfc/codesnippet/cpp/cbrush-class_4.cpp)]

##  <a name="createpatternbrush"></a>CBrush:: CreatePatternBrush

Bit eşlemle belirtilen bir fırça ile bir fırça başlatır.

```
BOOL CreatePatternBrush(CBitmap* pBitmap);
```

### <a name="parameters"></a>Parametreler

*Pbımap*<br/>
Bit eşlemi tanımlar.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Fırça daha sonra Raster işlemlerini destekleyen herhangi bir cihaz bağlamı için seçilebilir. *Pbıx* tarafından tanımlanan bit eşlem genellikle [cbit eşlem:: CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap), [CBitmap:: createbitmapdolaylı](../../mfc/reference/cbitmap-class.md#createbitmapindirect), [CBitmap:: LoadBitmap](../../mfc/reference/cbitmap-class.md#loadbitmap)veya [CBitmap:: CreateCompatibleBitmap](../../mfc/reference/cbitmap-class.md#createcompatiblebitmap) işlevi kullanılarak başlatılır.

Fill desenleri olarak kullanılan bit eşlemler 8 piksel olmalıdır. Bit eşlem daha büyükse, Windows yalnızca bit eşlemin sol üst köşesindeki ilk 8 satır ve piksel sütunları ile eşleşen bitleri kullanacaktır.

Bir model fırçası, ilişkili bit eşlem etkilenmeden silinebilir. Bu, bit eşlemin herhangi bir sayıda desenler fırçaları oluşturmak için kullanılabileceği anlamına gelir.

Tek renkli bit eşlem (1 renk düzlemi, piksel başına 1 bit) kullanılarak oluşturulan bir fırça, geçerli metin ve arka plan renkleri kullanılarak çizilir. Bit olarak ayarlanan bit olarak temsil edilen pikseller geçerli metin rengiyle çizilir. Bit kümesi 1 olarak temsil edilen pikseller geçerli arka plan rengiyle çizilir.

Bir Windows işlevi olan [CreatePatternBrush](/windows/win32/api/wingdi/nf-wingdi-createpatternbrush)kullanma hakkında daha fazla bilgi için Windows SDK bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#25](../../mfc/codesnippet/cpp/cbrush-class_5.cpp)]

##  <a name="createsolidbrush"></a>CBrush:: Createkesintisdbrush

Belirtilen düz renge sahip bir fırça başlatır.

```
BOOL CreateSolidBrush(COLORREF crColor);
```

### <a name="parameters"></a>Parametreler

*crColor*<br/>
Fırçanın rengini belirten [colorref](/windows/win32/gdi/colorref) yapısı. Renk bir RGB değeri belirtir ve WINDOWS 'da RGB makrosu ile oluşturulabilir. Olsun.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Fırça daha sonra herhangi bir cihaz bağlamı için geçerli fırça olarak seçilebilir.

Bir uygulama `CreateSolidBrush`tarafından oluşturulan fırçayı kullanmayı bitirdiğinde, cihaz bağlamından fırçayı seçer.

### <a name="example"></a>Örnek

  [CBrush:: CBrush](#cbrush)örneğine bakın.

##  <a name="createsyscolorbrush"></a>CBrush:: CreateSysColorBrush

Bir fırça rengi başlatır.

```
BOOL CreateSysColorBrush(int nIndex);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Renk dizinini belirtir. Bu değer 21 pencere öğelerinden birini boyamak için kullanılan renge karşılık gelir. Değerlerin listesi için Windows SDK bkz. [Getsyscrengi](/windows/win32/api/winuser/nf-winuser-getsyscolor) .

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Fırça daha sonra herhangi bir cihaz bağlamı için geçerli fırça olarak seçilebilir.

Bir uygulama `CreateSysColorBrush`tarafından oluşturulan fırçayı kullanmayı bitirdiğinde, cihaz bağlamından fırçayı seçer.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#26](../../mfc/codesnippet/cpp/cbrush-class_6.cpp)]

##  <a name="fromhandle"></a>CBrush:: FromHandle

Bir Windows [HBRUSH](#operator_hbrush) nesnesine bir tanıtıcı verildiğinde `CBrush` nesnesine yönelik bir işaretçi döndürür.

```
static CBrush* PASCAL FromHandle(HBRUSH hBrush);
```

### <a name="parameters"></a>Parametreler

*hBrush*<br/>
Windows GDI fırçasının tanıtıcısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa `CBrush` nesnesine yönelik bir işaretçi; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Bir `CBrush` nesnesi tanıtıcıya zaten iliştirilmişse, geçici bir `CBrush` nesnesi oluşturulur ve eklenir. Bu geçici `CBrush` nesne yalnızca, olay döngüsünde uygulamanın bir sonraki boşta kalma süresine kadar geçerlidir. Şu anda tüm geçici grafik nesneleri silinir. Diğer bir deyişle, geçici nesne yalnızca bir pencere iletisi işlenirken geçerlidir.

Grafik nesnelerini kullanma hakkında daha fazla bilgi için, Windows SDK [grafik nesneleri](/windows/win32/gdi/graphic-objects) bölümüne bakın.

### <a name="example"></a>Örnek

  [CBrush:: CBrush](#cbrush)örneğine bakın.

##  <a name="getlogbrush"></a>CBrush:: GetLogBrush

`LOGBRUSH` yapısını almak için bu üye işlevi çağırın.

```
int GetLogBrush(LOGBRUSH* pLogBrush);
```

### <a name="parameters"></a>Parametreler

*pLogBrush*<br/>
Fırça hakkında bilgi içeren bir [LOGBRUSH](/windows/win32/api/wingdi/ns-wingdi-logbrush) yapısına işaret eder.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa ve *pLogBrush* geçerli bir işaretçisiyse, dönüş değeri arabellekte depolanan baytların sayısıdır.

İşlev başarılı olursa ve *pLogBrush* null ise, dönüş değeri işlevin arabellekte depolayacağı bilgileri tutmak için gereken bayt sayısıdır.

İşlev başarısız olursa, dönüş değeri 0 ' dır.

### <a name="remarks"></a>Açıklamalar

`LOGBRUSH` yapısı, bir fırçanın stilini, rengini ve modelini tanımlar.

Örneğin, bir bit eşlemin belirli rengi veya düzeniyle eşleştirmek için `GetLogBrush` çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#27](../../mfc/codesnippet/cpp/cbrush-class_7.cpp)]

##  <a name="operator_hbrush"></a>CBrush:: operator HBRUSH

`CBrush` nesnesinin ekli Windows GDI işleyicisini almak için bu işleci kullanın.

```
operator HBRUSH() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, `CBrush` nesnesi tarafından temsil edilen Windows GDI nesnesine yönelik bir tanıtıcı; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Bu işleç, bir HBRUSH nesnesinin doğrudan kullanımını destekleyen bir atama işleçtir.

Grafik nesnelerini kullanma hakkında daha fazla bilgi için, Windows SDK [grafik nesneleri](/windows/win32/gdi/graphic-objects) bölümüne bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#28](../../mfc/codesnippet/cpp/cbrush-class_8.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek PROPDLG](../../overview/visual-cpp-samples.md)<br/>
[CGdiObject Sınıfı](../../mfc/reference/cgdiobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CBitmap Sınıfı](../../mfc/reference/cbitmap-class.md)<br/>
[CDC Sınıfı](../../mfc/reference/cdc-class.md)
