---
title: CPen sınıfı
ms.date: 11/04/2016
f1_keywords:
- CPen
- AFXWIN/CPen
- AFXWIN/CPen::CPen
- AFXWIN/CPen::CreatePen
- AFXWIN/CPen::CreatePenIndirect
- AFXWIN/CPen::FromHandle
- AFXWIN/CPen::GetExtLogPen
- AFXWIN/CPen::GetLogPen
helpviewer_keywords:
- CPen [MFC], CPen
- CPen [MFC], CreatePen
- CPen [MFC], CreatePenIndirect
- CPen [MFC], FromHandle
- CPen [MFC], GetExtLogPen
- CPen [MFC], GetLogPen
ms.assetid: 93175a3a-d46c-4768-be8d-863254f97a5f
ms.openlocfilehash: 8510c29571e6a370c7948ebe49e53b2c22dbfb9c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62372926"
---
# <a name="cpen-class"></a>CPen sınıfı

Bir Windows grafik cihaz arabirimi (GDI) kalemi kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CPen : public CGdiObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CPen::CPen](#cpen)|Oluşturur bir `CPen` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CPen::CreatePen](#createpen)|Mantıksal yüzeysel veya geometrik kalem belirtilen stili, genişliğini ve fırça öznitelikleri oluşturur ve ona ekler `CPen` nesne.|
|[CPen::CreatePenIndirect](#createpenindirect)|Kalem stili, genişliği ve belirtilen rengi oluşturur bir [LOGPEN](/windows/desktop/api/wingdi/ns-wingdi-taglogpen) yapısı ve ekler `CPen` nesne.|
|[CPen::FromHandle](#fromhandle)|Bir işaretçi döndüren bir `CPen` Windows HPEN verildiğinde nesne.|
|[CPen::GetExtLogPen](#getextlogpen)|Alır bir [EXTLOGPEN](/windows/desktop/api/wingdi/ns-wingdi-tagextlogpen) yapısı temel.|
|[CPen::GetLogPen](#getlogpen)|Alır bir [LOGPEN](/windows/desktop/api/wingdi/ns-wingdi-taglogpen) yapısı temel.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[HPEN CPen::operator](#operator_hpen)|Bağlı Windows tanıtıcısını döndürür `CPen` nesne.|

## <a name="remarks"></a>Açıklamalar

Kullanma hakkında daha fazla bilgi için `CPen`, bkz: [grafik nesneleri](../../mfc/graphic-objects.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CPen`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

##  <a name="cpen"></a>  CPen::CPen

Oluşturur bir `CPen` nesne.

```
CPen();

CPen(
    int nPenStyle,
    int nWidth,
    COLORREF crColor);

CPen(
    int nPenStyle,
    int nWidth,
    const LOGBRUSH* pLogBrush,
    int nStyleCount = 0,
    const DWORD* lpStyle = NULL);
```

### <a name="parameters"></a>Parametreler

*nPenStyle*<br/>
Kalem stilini belirtir. Oluşturucu'nün ilk sürümündeki Bu parametre aşağıdaki değerlerden biri olabilir:

- Düz kalem PS_SOLID oluşturur.

- PS_DASH kesikli kalem oluşturur. Kalem genişliği 1 veya daha az, cihaz birimleri olduğunda geçerlidir.

- PS_DOT noktalı kalem oluşturur. Kalem genişliği 1 veya daha az, cihaz birimleri olduğunda geçerlidir.

- Kalem değişen ile çizgi ve nokta PS_DASHDOT oluşturur. Kalem genişliği 1 veya daha az, cihaz birimleri olduğunda geçerlidir.

- PS_DASHDOTDOT kalem ile çizgi ve çift nokta değişen bir oluşturur. Kalem genişliği 1 veya daha az, cihaz birimleri olduğunda geçerlidir.

- PS_NULL null kalem oluşturur.

- PS_INSIDEFRAME Windows GDI oluşturduğu kapalı şekiller çerçevenin içine bir çizgi çizer bir kalem üretilen çıkış sınırlayıcı bir dikdörtgen belirtin işlevleri (örneğin, `Ellipse`, `Rectangle`, `RoundRect`, `Pie`ve `Chord`üye işlevleri). Bu stil sınırlayıcı bir dikdörtgen belirtmeyin Windows GDI çıkış işlevleri ile kullanıldığında (örneğin, `LineTo` üye işlevi), çerçeve tarafından kalemi çizim alanının sınırlı değildir.

Dosyanın ikinci sürümü, `CPen` Oluşturucu türü, stil, bitiş ucu ve birleştirme öznitelikleri belirtir. Her kategori değerleri bit düzeyinde OR işleci kullanılarak birleştirilmelidir (&#124;). Kalem türü aşağıdaki değerlerden biri olabilir:

- Geometrik kalem PS_GEOMETRIC oluşturur.

- Yüzeysel kalem PS_COSMETIC oluşturur.

   Dosyanın ikinci sürümü, `CPen` Oluşturucu ekler için aşağıdaki kalem stilleri *nPenStyle*:

- Her bir piksel ayarlayan kalem PS_ALTERNATE oluşturur. (Bu yalnızca yüzeysel kalemler için geçerlidir.)

- Bir stil dizisi kullanan bir kalem PS_USERSTYLE oluşturur Kullanıcı tarafından sağlandı.

   Bitiş ucu aşağıdaki değerlerden biri olabilir:

- PS_ENDCAP_ROUND uç başlıkları YUVARLA.

- Kare PS_ENDCAP_SQUARE uç başlıkları.

- Düz PS_ENDCAP_FLAT uç başlıkları.

   Birleştirme aşağıdaki değerlerden biri olabilir:

- PS_JOIN_BEVEL birleşimler Eğimli.

- PS_JOIN_MITER birleşimler gönye belirlenen geçerli sınırı içinde olduğunda [SetMiterLimit](/windows/desktop/api/wingdi/nf-wingdi-setmiterlimit) işlevi. Birleşim bu sınırı aşarsa Eğimli.

- Birleşimler PS_JOIN_ROUND yuvarlatılmış.

*nWidth*<br/>
Kalem genişliğini belirtir.

- Bu değer 0 ise ilk oluşturucusu için cihaz birimlerindeki genişliğini her zaman eşleme modunu bağımsız olarak 1 piksel artımlı sürümüdür.

- İkinci oluşturucu sürümü için ise *nPenStyle* PS_GEOMETRIC, olan mantıksal birimler cinsinden genişliğini verilir. Varsa *nPenStyle* PS_COSMETIC, olan genişliği 1 olarak ayarlanması gerekir.

*crColor*<br/>
Bir RGB rengi kalemin içerir.

*pLogBrush*<br/>
İşaret eden bir `LOGBRUSH` yapısı. Varsa *nPenStyle* PS_COSMETIC, olan *lbColor* üyesi `LOGBRUSH` yapısı kalemin rengini belirtir ve *lbStyle* üyesi `LOGBRUSH` Yapı için BS_SOLID ayarlamanız gerekir. Varsa *nPenStyle* PS_GEOMETRIC, olan tüm üyeleri kalem fırça özniteliklerini belirtmek için kullanılmalıdır.

*nStyleCount*<br/>
Doubleword birimindeki uzunluğu belirtir *lpStyle* dizisi. Bu değerin sıfır olması *nPenStyle* PS_USERSTYLE değil.

*lpStyle*<br/>
Bir dizi noktalarını doubleword değerleri. İlk değer, kullanıcı tanımlı bir stilde ilk dash uzunluğunu belirtir, ikinci değer ilk alanı vb. uzunluğunu belirtir. This işaretçisi, NULL olmalı *nPenStyle* PS_USERSTYLE değil.

### <a name="remarks"></a>Açıklamalar

Oluşturucu bağımsız değişken olmadan kullanırsanız, sonuç başlatmalıdır `CPen` nesnesi ile `CreatePen`, `CreatePenIndirect`, veya `CreateStockObject` üye işlevleri.

Bağımsız değişken alan oluşturucu kullanırsanız, başka hiçbir başlatma gereklidir. Oluşturucu bağımsız değişken olmadan her zaman başarılı olur ancak, bir hatayla karşılaşılmazsa oluşturucu bağımsız değişkenleri olan bir özel durum.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#99](../../mfc/codesnippet/cpp/cpen-class_1.cpp)]

##  <a name="createpen"></a>  CPen::CreatePen

Mantıksal yüzeysel veya geometrik kalem belirtilen stili, genişliğini ve fırça öznitelikleri oluşturur ve ona ekler `CPen` nesne.

```
BOOL CreatePen(
    int nPenStyle,
    int nWidth,
    COLORREF crColor);

BOOL CreatePen(
    int nPenStyle,
    int nWidth,
    const LOGBRUSH* pLogBrush,
    int nStyleCount = 0,
    const DWORD* lpStyle = NULL);
```

### <a name="parameters"></a>Parametreler

*nPenStyle*<br/>
Kalem stilini belirtir. Olası değerler listesi için bkz. *nPenStyle* parametresinde [CPen](#cpen) Oluşturucusu.

*nWidth*<br/>
Kalem genişliğini belirtir.

- İlk sürümü için `CreatePen`, bu değer 0 ise, cihaz birimlerindeki genişliğini her zaman eşleme modunu bağımsız olarak 1 piksel artımlı olur.

- İkinci sürümü için `CreatePen`, *nPenStyle* PS_GEOMETRIC, olan mantıksal birimler cinsinden genişliğini verilir. Varsa *nPenStyle* PS_COSMETIC, olan genişliği 1 olarak ayarlanması gerekir.

*crColor*<br/>
Bir RGB rengi kalemin içerir.

*pLogBrush*<br/>
İşaret eden bir [LOGBRUSH](/windows/desktop/api/wingdi/ns-wingdi-taglogbrush) yapısı. Varsa *nPenStyle* PS_COSMETIC, olan `lbColor` üyesi `LOGBRUSH` yapısı kalemin rengini belirtir ve *lbStyle* üyesi `LOGBRUSH` yapısı, BS_ için ayarlanmış olması gerekir DOLU. NPenStyle PS_GEOMETRIC ise, tüm üyeleri kalem fırça özniteliklerini belirtmek için kullanılmalıdır.

*nStyleCount*<br/>
Doubleword birimindeki uzunluğu belirtir *lpStyle* dizisi. Bu değerin sıfır olması *nPenStyle* PS_USERSTYLE değil.

*lpStyle*<br/>
Bir dizi noktalarını doubleword değerleri. İlk değer, kullanıcı tanımlı bir stilde ilk dash uzunluğunu belirtir, ikinci değer ilk alanı vb. uzunluğunu belirtir. This işaretçisi, NULL olmalı *nPenStyle* PS_USERSTYLE değil.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı veya yöntem başarısız olursa sıfır.

### <a name="remarks"></a>Açıklamalar

Ürününün ilk sürümünü `CreatePen` kalem belirtilen stili, genişliği ve rengi ile başlatır. Kalem, daha sonra herhangi bir cihaz bağlamı için geçerli kalem olarak seçilebilir.

1 piksel artımlı büyük bir genişliğe sahiptir kalemler, her zaman PS_NULL, PS_SOLID veya PS_INSIDEFRAME stil olması gerekir.

Kalem PS_INSIDEFRAME stili ve mantıksal bir renk tablosundaki bir renk eşleşmeyen bir renk varsa, kalem bir Titremeli renk ile çizilir. PS_SOLID kalem stili bir Titremeli renk ile bir kalem oluşturmak için kullanılamaz. Kalem genişliği 1'e eşit veya küçükse PS_INSIDEFRAME stili PS_SOLID için aynıdır.

Dosyanın ikinci sürümü, `CreatePen` stili, genişliğini ve öznitelikleri fırça belirtilen sahip mantıksal yüzeysel veya geometrik kalem başlatır. Yüzeysel kalem genişliği her zaman 1'dir; Geometrik kalem genişliği her zaman dünya birimleri cinsinden belirtilir. Bir uygulamanın mantıksal kalem oluşturduktan sonra kalem bir cihaz bağlamına çağırarak seçebilirsiniz [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) işlevi. Bir cihaz bağlamına kalem seçtikten sonra çizgiler ve eğrilerle çizmek için kullanılabilir.

- Varsa *nPenStyle* PS_COSMETIC ve PS_USERSTYLE, girişleri *lpStyle* dizi çizgi ve boşluk uzunlukları stili birimleri cinsinden belirtin. Bir stil birim bir çizgi çizmek için Kalem kullanıldığı cihaz tarafından tanımlanır.

- Varsa *nPenStyle* PS_GEOMETRIC ve PS_USERSTYLE, girişleri *lpStyle* dizisi uzunluklarının çizgi ve boşluk mantıksal birimler cinsinden belirtin.

- Varsa *nPenStyle* PS_ALTERNATE, stil birim göz ardı edilir ve her bir piksel ayarlanır.

Artık bir uygulama belirli bir kalem gerektirdiğinde çağırmalıdır [CGdiObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) üye işlev veya yok etme `CPen` kaynak artık kullanımda olduğundan nesne. Kalem cihaz bağlamında seçili olduğunda, bir uygulama bir kalem silmemelisiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#100](../../mfc/codesnippet/cpp/cpen-class_2.cpp)]

##  <a name="createpenindirect"></a>  CPen::CreatePenIndirect

Bir stil, genişliği ve rengine işaret ettiği yapısı verilen sahip bir kalem başlatır *lpLogPen*.

```
BOOL CreatePenIndirect(LPLOGPEN lpLogPen);
```

### <a name="parameters"></a>Parametreler

*lpLogPen*<br/>
Windows için işaret [LOGPEN](/windows/desktop/api/Wingdi/ns-wingdi-taglogpen) kalem hakkında bilgi içeren yapısı.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

1 piksel artımlı büyük bir genişliğe sahiptir kalemler, her zaman PS_NULL, PS_SOLID veya PS_INSIDEFRAME stil olması gerekir.

Kalem PS_INSIDEFRAME stili ve mantıksal bir renk tablosundaki bir renk eşleşmeyen bir renk varsa, kalem bir Titremeli renk ile çizilir. Kalem genişliği 1'e eşit veya küçükse PS_INSIDEFRAME stili PS_SOLID için aynıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#101](../../mfc/codesnippet/cpp/cpen-class_3.cpp)]

##  <a name="fromhandle"></a>  CPen::FromHandle

Bir işaretçi döndüren bir `CPen` bir Windows GDI pen nesnesi için bir tanıtıcı verilen nesne.

```
static CPen* PASCAL FromHandle(HPEN hPen);
```

### <a name="parameters"></a>Parametreler

*hPen*<br/>
`HPEN` Windows GDI kaleme işleyin.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir `CPen` nesne başarılı; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Varsa bir `CPen` nesne tanıtıcısını, geçici bir iliştirilmemiş `CPen` nesnesi oluşturulur ve bağlı. Bu geçici `CPen` tüm geçici grafik, zaman sonraki açışınızda uygulama boşta kalma süresi kendi olay döngüsü olana kadar nesneler silinir yalnızca nesne geçerlidir. Diğer bir deyişle, geçici nesne yalnızca bir pencere ileti işlenmesi sırasında geçerli değil.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#105](../../mfc/codesnippet/cpp/cpen-class_4.cpp)]

##  <a name="getextlogpen"></a>  CPen::GetExtLogPen

Alır bir `EXTLOGPEN` yapısı temel.

```
int GetExtLogPen(EXTLOGPEN* pLogPen);
```

### <a name="parameters"></a>Parametreler

*pLogPen*<br/>
İşaret eden bir [EXTLOGPEN](/windows/desktop/api/wingdi/ns-wingdi-tagextlogpen) kalem hakkında bilgi içeren yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

`EXTLOGPEN` Yapısı, stil, genişliğini ve Kalem fırça özniteliklerini tanımlar. Örneğin, çağrı `GetExtLogPen` kalem belirli stilini eşleştirilecek.

Windows SDK'sındaki kalem öznitelikleri hakkında daha fazla bilgi için aşağıdaki konulara bakın:

- [GetObject](/windows/desktop/api/wingdi/nf-wingdi-getobject)

- [EXTLOGPEN](/windows/desktop/api/wingdi/ns-wingdi-tagextlogpen)

- [LOGPEN](/windows/desktop/api/wingdi/ns-wingdi-taglogpen)

- [ExtCreatePen](/windows/desktop/api/wingdi/nf-wingdi-extcreatepen)

### <a name="example"></a>Örnek

Aşağıdaki kod örneği arama gösterir `GetExtLogPen` bir kalem öznitelikleri almak ve sonra yeni, yüzeysel bir kalem ile aynı renge oluşturun.

[!code-cpp[NVC_MFCDocView#102](../../mfc/codesnippet/cpp/cpen-class_5.cpp)]

##  <a name="getlogpen"></a>  CPen::GetLogPen

Alır bir `LOGPEN` yapısı temel.

```
int GetLogPen(LOGPEN* pLogPen);
```

### <a name="parameters"></a>Parametreler

*pLogPen*<br/>
İşaret eden bir [LOGPEN](/windows/desktop/api/wingdi/ns-wingdi-taglogpen) yapısı kalem hakkındaki bilgileri içerir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

`LOGPEN` Yapısı, stil, rengini ve Kalem desenini tanımlar.

Örneğin, çağrı `GetLogPen` kalem belirli stilini eşleştirilecek.

Windows SDK'sındaki kalem öznitelikleri hakkında daha fazla bilgi için aşağıdaki konulara bakın:

- [GetObject](/windows/desktop/api/wingdi/nf-wingdi-getobject)

- [LOGPEN](/windows/desktop/api/wingdi/ns-wingdi-taglogpen)

### <a name="example"></a>Örnek

Aşağıdaki kod örneği arama gösterir `GetLogPen` kalem karakter alıp sonra yeni, düz bir kalem ile aynı renge oluşturun.

[!code-cpp[NVC_MFCDocView#103](../../mfc/codesnippet/cpp/cpen-class_6.cpp)]

##  <a name="operator_hpen"></a>  HPEN CPen::operator

Ekli Windows GDI tanıtıcısını alır `CPen` nesne.

```
operator HPEN() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı, Windows GDI nesnesi için bir tanıtıcı tarafından temsil edilen varsa `CPen` nesne; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

HPEN nesne doğrudan kullanımını destekleyen bir yayım işleciyle işlecidir.

Grafik nesneler kullanma hakkında daha fazla bilgi için bkz [grafik nesneleri](/windows/desktop/gdi/graphic-objects) Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#104](../../mfc/codesnippet/cpp/cpen-class_7.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CGdiObject Sınıfı](../../mfc/reference/cgdiobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CBrush Sınıfı](../../mfc/reference/cbrush-class.md)
