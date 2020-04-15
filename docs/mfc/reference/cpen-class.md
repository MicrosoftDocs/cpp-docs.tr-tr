---
title: CPen Sınıfı
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
ms.openlocfilehash: e15dc53fafa0d80f1b52b3fe77f3635c592a4346
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364076"
---
# <a name="cpen-class"></a>CPen Sınıfı

Bir Windows grafik aygıtı arabirimini (GDI) kalemini kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CPen : public CGdiObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CPen::CPen](#cpen)|Bir `CPen` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CPen::CreatePen](#createpen)|Belirtilen stil, genişlik ve fırça özniteliklerine sahip mantıksal bir kozmetik veya `CPen` geometrik kalem oluşturur ve nesneye bağlar.|
|[CPen::CreatePenIndirect](#createpenindirect)|[LOGPEN](/windows/win32/api/wingdi/ns-wingdi-logpen) yapısında verilen stil, genişlik ve renk içeren bir kalem oluşturur `CPen` ve nesneye bağlar.|
|[CPen::FromHandle](#fromhandle)|Windows HPEN `CPen` verildiğinde bir nesneye işaretçiyi döndürür.|
|[CPen::GetExtLogPen](#getextlogpen)|[EXTLOGPEN](/windows/win32/api/wingdi/ns-wingdi-extlogpen) altta yatan bir yapı alır.|
|[CPen::GetLogPen](#getlogpen)|[LOGPEN](/windows/win32/api/wingdi/ns-wingdi-logpen) altta yatan bir yapı alır.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CPen::operatör HPEN](#operator_hpen)|Nesneye bağlı Windows tutamacını `CPen` döndürür.|

## <a name="remarks"></a>Açıklamalar

Kullanma `CPen`hakkında daha fazla bilgi için [Bkz. Grafik Nesneler.](../../mfc/graphic-objects.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Cgdiobject](../../mfc/reference/cgdiobject-class.md)

`CPen`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="cpencpen"></a><a name="cpen"></a>CPen::CPen

Bir `CPen` nesne inşa eder.

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
Kalem stilini belirtir. Oluşturucunun ilk sürümündeki bu parametre aşağıdaki değerlerden biri olabilir:

- PS_SOLID katı bir kalem oluşturur.

- PS_DASH kesikli bir kalem oluşturur. Yalnızca kalem genişliği 1 veya daha az olduğunda, aygıt birimlerinde geçerlidir.

- PS_DOT Noktalı kalem oluşturur. Yalnızca kalem genişliği 1 veya daha az olduğunda, aygıt birimlerinde geçerlidir.

- PS_DASHDOT Alternatif tire ve nokta ile bir kalem oluşturur. Yalnızca kalem genişliği 1 veya daha az olduğunda, aygıt birimlerinde geçerlidir.

- PS_DASHDOTDOT Alternatif tire ve çift noktalı bir kalem oluşturur. Yalnızca kalem genişliği 1 veya daha az olduğunda, aygıt birimlerinde geçerlidir.

- PS_NULL Null kalem oluşturur.

- PS_INSIDEFRAME, sınırlayıcı bir dikdörtgen (örneğin, `Ellipse`, `Rectangle`, `RoundRect`, `Pie`ve `Chord` üye işlevler) belirten Windows GDI çıkış işlevleri tarafından üretilen kapalı şekillerin çerçevesi içinde bir çizgi çizen bir kalem oluşturur. Bu stil, sınırlayıcı bir dikdörtgen `LineTo` (örneğin, üye işlev) belirtmeyen Windows GDI çıkış işlevleriyle kullanıldığında, kalemin çizim alanı bir çerçeveyle sınırlı değildir.

`CPen` Oluşturucunun ikinci sürümü, tür, stil, bitiş kapağı ve birleştirme özniteliklerinin bir birleşimini belirtir. Her kategorideki değerler bitwise OR işleci (&#124;) kullanılarak birleştirilmelidir. Kalem türü aşağıdaki değerlerden biri olabilir:

- PS_GEOMETRIC geometrik bir kalem oluşturur.

- PS_COSMETIC kozmetik kalem oluşturur.

   Oluşturucunun `CPen` ikinci sürümü *nPenStyle*için aşağıdaki kalem stillerini ekler:

- PS_ALTERNATE Diğer tüm pikselleri ayarlayan bir kalem oluşturur. (Bu stil sadece kozmetik kalemler için geçerlidir.)

- PS_USERSTYLE Kullanıcı tarafından sağlanan bir stil dizisini kullanan bir kalem oluşturur.

   Bitiş kapağı aşağıdaki değerlerden biri olabilir:

- PS_ENDCAP_ROUND Son kapaklar yuvarlak.

- PS_ENDCAP_SQUARE Uç kapakları karedir.

- PS_ENDCAP_FLAT Uç kapakları düz.

   Birleştirme aşağıdaki değerlerden biri olabilir:

- PS_JOIN_BEVEL Joins beveled vardır.

- PS_JOIN_MITER [Joins, SetMiterLimit](/windows/win32/api/wingdi/nf-wingdi-setmiterlimit) işlevi tarafından belirlenen geçerli sınır dahilinde olduklarında gönyelenir. Birleştirme bu sınırı aşarsa, yaslanır.

- PS_JOIN_ROUND Joins yuvarlak.

*Nwidth*<br/>
Kalemin genişliğini belirtir.

- Oluşturucunun ilk sürümü için, bu değer 0 ise, eşleme modune bakılmaksızın aygıt birimlerindeki genişlik her zaman 1 pikseldir.

- Oluşturucunun ikinci sürümü için, *nPenStyle* PS_GEOMETRIC ise, genişlik mantıksal birimler halinde verilir. *nPenStyle* PS_COSMETIC ise, genişlik 1 olarak ayarlanmalıdır.

*crColor*<br/>
Kalem için rgb rengi içerir.

*pLogBrush*<br/>
Bir `LOGBRUSH` yapıyı işaret edin. *nPenStyle* PS_COSMETIC ise, `LOGBRUSH` yapının *lbColor* üyesi kalemin rengini belirtir ve `LOGBRUSH` yapının *lbStyle* üyesi BS_SOLID olarak ayarlanmalıdır. *nPenStyle* PS_GEOMETRIC ise, kalemin fırça özniteliklerini belirtmek için tüm üyeler kullanılmalıdır.

*nStyleCount*<br/>
*LpStyle* dizisinin çift kelime birimlerinde uzunluğunu belirtir. *nPenStyle* PS_USERSTYLE değilse bu değer sıfır olmalıdır.

*lpStyle*<br/>
Bir dizi çift sözcük değerine işaret edin. İlk değer, kullanıcı tanımlı bir stilde ilk tirenin uzunluğunu, ikinci değer ise ilk boşluğun uzunluğunu ve benzeri özellikleri belirtir. *nPenStyle* PS_USERSTYLE değilse, bu işaretçi NULL olmalıdır.

### <a name="remarks"></a>Açıklamalar

Kurucuyu bağımsız değişkenolmadan kullanıyorsanız, `CPen` ortaya çıkan nesneyi `CreatePen`, `CreatePenIndirect`veya `CreateStockObject` üye işlevlerle başlatmanız gerekir.

Bağımsız değişkenleri alan oluşturucuyu kullanırsanız, başka bir başlatma gerekmez. Bağımsız değişkenleri olan oluşturucu, hatalarla karşılaşılırsa bir özel durum atabilirken, bağımsız değişkeni olmayan oluşturucu her zaman başarılı olur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#99](../../mfc/codesnippet/cpp/cpen-class_1.cpp)]

## <a name="cpencreatepen"></a><a name="createpen"></a>CPen::CreatePen

Belirtilen stil, genişlik ve fırça özniteliklerine sahip mantıksal bir kozmetik veya `CPen` geometrik kalem oluşturur ve nesneye bağlar.

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
Kalemin stilini belirtir. Olası değerlerin listesi için [CPen](#cpen) oluşturucudaki *nPenStyle* parametreye bakın.

*Nwidth*<br/>
Kalemin genişliğini belirtir.

- Bu değer 0 `CreatePen`ise, eşleme modune bakılmaksızın aygıt birimlerindeki genişlik her zaman 1 pikseldir.

- NPenStyle'ın `CreatePen`ikinci *nPenStyle* sürümü için PS_GEOMETRIC, genişlik mantıksal birimler halinde verilir. *nPenStyle* PS_COSMETIC ise, genişlik 1 olarak ayarlanmalıdır.

*crColor*<br/>
Kalem için rgb rengi içerir.

*pLogBrush*<br/>
[LOGBRUSH](/windows/win32/api/wingdi/ns-wingdi-logbrush) yapısına işaret edin. *nPenStyle* PS_COSMETIC ise, `lbColor` `LOGBRUSH` yapının üyesi kalemin rengini belirtir ve `LOGBRUSH` yapının *lbStyle* üyesi BS_SOLID olarak ayarlanmalıdır. nPenStyle PS_GEOMETRIC ise, kalemin fırça özniteliklerini belirtmek için tüm üyeler kullanılmalıdır.

*nStyleCount*<br/>
*LpStyle* dizisinin çift kelime birimlerinde uzunluğunu belirtir. *nPenStyle* PS_USERSTYLE değilse bu değer sıfır olmalıdır.

*lpStyle*<br/>
Bir dizi çift sözcük değerine işaret edin. İlk değer, kullanıcı tanımlı bir stilde ilk tirenin uzunluğunu, ikinci değer ise ilk boşluğun uzunluğunu ve benzeri özellikleri belirtir. *nPenStyle* PS_USERSTYLE değilse, bu işaretçi NULL olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Başarısız olursa sıfır veya yöntem başarısız olursa sıfır.

### <a name="remarks"></a>Açıklamalar

İlk sürümü, `CreatePen` belirtilen stil, genişlik ve renge sahip bir kalemi başharfe ait hale sağlar. Kalem daha sonra herhangi bir aygıt bağlamı için geçerli kalem olarak seçilebilir.

Genişliği 1 pikselden büyük olan kalemlerde her zaman PS_NULL, PS_SOLID veya PS_INSIDEFRAME tarzı olmalıdır.

Kalemin PS_INSIDEFRAME stili ve mantıksal renk tablosundaki bir renge uymayan bir renk varsa, kalem dithered renkle çizilir. PS_SOLID kalem stili, renk tespisi olan bir kalem oluşturmak için kullanılamaz. Kalem genişliği 1'den küçük veya eşitse, PS_INSIDEFRAME stili PS_SOLID ile aynıdır.

İkinci sürümü, `CreatePen` belirtilen stil, genişlik ve fırça özniteliklerine sahip mantıksal bir kozmetik veya geometrik kalemi başharfe bağlar. Bir kozmetik kalem genişliği her zaman 1; geometrik kalemin genişliği her zaman dünya birimlerinde belirtilir. Bir uygulama mantıksal bir kalem oluşturduktan sonra, [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) işlevini arayarak bu kalemi aygıt bağlamına seçebilir. Bir kalem aygıt bağlamına seçildikten sonra, çizgiler ve eğriler çizmek için kullanılabilir.

- *nPenStyle* PS_COSMETIC ve PS_USERSTYLE ise, *lpStyle* dizisindeki girişler stil birimlerindeki tire ve boşlukların uzunluklarını belirtir. Bir stil birimi, kalemin bir çizgi çizmek için kullanıldığı aygıt tarafından tanımlanır.

- *nPenStyle* PS_GEOMETRIC ve PS_USERSTYLE ise, *lpStyle* dizisindeki girişler mantıksal birimlerdeki tire ve boşlukların uzunluklarını belirtir.

- *nPenStyle* PS_ALTERNATE ise, stil birimi yoksayılır ve diğer tüm pikseller ayarlanır.

Bir uygulama artık belirli bir kalem gerektirmediğinde, [CGdiObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) üye `CPen` işlevini aramalı veya kaynağın artık kullanılmaması için nesneyi yok etmelidir. Kalem aygıt bağlamında seçildiğinde bir uygulama kalemi silmemelidir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#100](../../mfc/codesnippet/cpp/cpen-class_2.cpp)]

## <a name="cpencreatepenindirect"></a><a name="createpenindirect"></a>CPen::CreatePenIndirect

*lpLogPen*tarafından işaret edilen yapıda verilen stil, genişlik ve renk içeren bir kalemi başharfe döndürer.

```
BOOL CreatePenIndirect(LPLOGPEN lpLogPen);
```

### <a name="parameters"></a>Parametreler

*lpLogPen*<br/>
Kalem hakkında bilgi içeren Windows [LOGPEN](/windows/win32/api/Wingdi/ns-wingdi-logpen) yapısına işaret edin.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Genişliği 1 pikselden büyük olan kalemlerde her zaman PS_NULL, PS_SOLID veya PS_INSIDEFRAME tarzı olmalıdır.

Kalemin PS_INSIDEFRAME stili ve mantıksal renk tablosundaki bir renge uymayan bir renk varsa, kalem dithered renkle çizilir. Kalem genişliği 1'den küçük veya eşitse PS_INSIDEFRAME stili PS_SOLID ile aynıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#101](../../mfc/codesnippet/cpp/cpen-class_3.cpp)]

## <a name="cpenfromhandle"></a><a name="fromhandle"></a>CPen::FromHandle

Bir işaretçiyi `CPen` windows GDI kalem nesnesine tutamacı verilen bir nesneye döndürür.

```
static CPen* PASCAL FromHandle(HPEN hPen);
```

### <a name="parameters"></a>Parametreler

*hPen*<br/>
`HPEN`Windows GDI kalemi için kolu.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa `CPen` nesneye işaretçi; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Bir `CPen` nesne tutamacına bağlı değilse, `CPen` geçici bir nesne oluşturulur ve eklenir. Bu `CPen` geçici nesne yalnızca, uygulamanın olay döngüsünde boşta kalma süresine sahip olduğu ve tüm geçici grafik nesnelerinin silindiği bir sonraki zamana kadar geçerlidir. Başka bir deyişle, geçici nesne yalnızca bir pencere iletisinin işlenmesi sırasında geçerlidir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#105](../../mfc/codesnippet/cpp/cpen-class_4.cpp)]

## <a name="cpengetextlogpen"></a><a name="getextlogpen"></a>CPen::GetExtLogPen

Altta `EXTLOGPEN` yatan bir yapı alır.

```
int GetExtLogPen(EXTLOGPEN* pLogPen);
```

### <a name="parameters"></a>Parametreler

*pLogPen*<br/>
Kalem hakkında bilgi içeren bir [EXTLOGPEN](/windows/win32/api/wingdi/ns-wingdi-extlogpen) yapısına işaret edin.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Yapı, `EXTLOGPEN` kalemin stilini, genişliğini ve fırça özniteliklerini tanımlar. Örneğin, bir `GetExtLogPen` kalemin belirli stiliyle eşleşmek için arayın.

Kalem öznitelikleri hakkında bilgi için Windows SDK'daki aşağıdaki konulara bakın:

- [GetObject](/windows/win32/api/wingdi/nf-wingdi-getobject)

- [EXTLOGPEN](/windows/win32/api/wingdi/ns-wingdi-extlogpen)

- [LOGPEN](/windows/win32/api/wingdi/ns-wingdi-logpen)

- [ExtCreatePen](/windows/win32/api/wingdi/nf-wingdi-extcreatepen)

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `GetExtLogPen` kalemin özniteliklerini almak ve ardından aynı renge sahip yeni, kozmetik kalem oluşturmak için çağrı yı gösterir.

[!code-cpp[NVC_MFCDocView#102](../../mfc/codesnippet/cpp/cpen-class_5.cpp)]

## <a name="cpengetlogpen"></a><a name="getlogpen"></a>CPen::GetLogPen

Altta `LOGPEN` yatan bir yapı alır.

```
int GetLogPen(LOGPEN* pLogPen);
```

### <a name="parameters"></a>Parametreler

*pLogPen*<br/>
Kalem hakkında bilgi içeren bir [LOGPEN](/windows/win32/api/wingdi/ns-wingdi-logpen) yapısına işaret edin.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Yapı, `LOGPEN` kalemin stilini, rengini ve deseni tanımlar.

Örneğin, kalemin belirli stiliyle eşleşmek için arayın. `GetLogPen`

Kalem öznitelikleri hakkında bilgi için Windows SDK'daki aşağıdaki konulara bakın:

- [GetObject](/windows/win32/api/wingdi/nf-wingdi-getobject)

- [LOGPEN](/windows/win32/api/wingdi/ns-wingdi-logpen)

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `GetLogPen` bir kalem karakterini almak ve sonra aynı renge sahip yeni, düz bir kalem oluşturmak için çağrıyı gösterir.

[!code-cpp[NVC_MFCDocView#103](../../mfc/codesnippet/cpp/cpen-class_6.cpp)]

## <a name="cpenoperator-hpen"></a><a name="operator_hpen"></a>CPen::operatör HPEN

Nesnenin ekli Windows GDI `CPen` tutamacını alır.

```
operator HPEN() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, nesne tarafından temsil edilen Windows `CPen` GDI nesnesine bir tanıtıcı; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Bu işleç, bir HPEN nesnesinin doğrudan kullanımını destekleyen bir döküm operatörüdür.

Grafik nesneleri kullanma hakkında daha fazla bilgi için Windows SDK'daki [Grafik Nesneler](/windows/win32/gdi/graphic-objects) makalesine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#104](../../mfc/codesnippet/cpp/cpen-class_7.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CGdiObject Sınıfı](../../mfc/reference/cgdiobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CBrush Sınıfı](../../mfc/reference/cbrush-class.md)
