---
description: 'Daha fazla bilgi edinin: CPen sınıfı'
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
ms.openlocfilehash: b85e0de8a5ce9048851b3f0a8ee5a701e749f0af
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345153"
---
# <a name="cpen-class"></a>CPen sınıfı

Windows grafik cihaz arabirimi (GDI) kalemini kapsüller.

## <a name="syntax"></a>Syntax

```
class CPen : public CGdiObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CPen:: CPen](#cpen)|Bir `CPen` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CPen:: CreatePen](#createpen)|Belirtilen stili, genişliği ve fırça özniteliklerini içeren bir mantıksal yüzeysel veya geometrik kalem oluşturur ve `CPen` nesneye ekler.|
|[CPen:: Creatependolaylı](#createpenindirect)|Bir [logpen](/windows/win32/api/wingdi/ns-wingdi-logpen) yapısında verilen stili, genişliği ve rengi içeren bir kalem oluşturur ve `CPen` nesneye ekler.|
|[CPen:: FromHandle](#fromhandle)|Bir `CPen` Windows HPEN verildiğinde bir nesneye bir işaretçi döndürür.|
|[CPen:: GetExtLogPen](#getextlogpen)|Bir [extlogpen](/windows/win32/api/wingdi/ns-wingdi-extlogpen) temel yapısını alır.|
|[CPen:: GetLogPen](#getlogpen)|Bir [logpen](/windows/win32/api/wingdi/ns-wingdi-logpen) temel yapısını alır.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CPen:: operator HPEN](#operator_hpen)|Nesnesine eklenen Windows işleyicisini döndürür `CPen` .|

## <a name="remarks"></a>Açıklamalar

Kullanma hakkında daha fazla bilgi için `CPen` bkz. [grafik nesneleri](../../mfc/graphic-objects.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CPen`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="cpencpen"></a><a name="cpen"></a> CPen:: CPen

Bir `CPen` nesnesi oluşturur.

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
Kalem stilini belirtir. Oluşturucunun ilk sürümündeki Bu parametre aşağıdaki değerlerden biri olabilir:

- PS_SOLID, düz bir kalem oluşturur.

- PS_DASH kesikli kalem oluşturur. Yalnızca kalem genişliği, cihaz birimlerinde 1 veya daha az olduğunda geçerlidir.

- PS_DOT noktalı bir kalem oluşturur. Yalnızca kalem genişliği, cihaz birimlerinde 1 veya daha az olduğunda geçerlidir.

- PS_DASHDOT, değişen tireler ve noktalar içeren bir kalem oluşturur. Yalnızca kalem genişliği, cihaz birimlerinde 1 veya daha az olduğunda geçerlidir.

- PS_DASHDOTDOT, değişen tireler ve çift noktalarla bir kalem oluşturur. Yalnızca kalem genişliği, cihaz birimlerinde 1 veya daha az olduğunda geçerlidir.

- PS_NULL, null bir kalem oluşturur.

- PS_INSIDEFRAME, bir sınırlayıcı dikdörtgen (örneğin,,,, `Ellipse` `Rectangle` `RoundRect` `Pie` ve `Chord` üye işlevleri) belirten Windows GDI çıkış işlevleri tarafından üretilen kapalı şekillerin çerçevesinin içine çizgi çizen bir kalem oluşturur. Bu stil, bir sınırlayıcı dikdörtgen belirtmeyen Windows GDI çıkış işlevleriyle kullanıldığında (örneğin, `LineTo` üye işlevi), kalemin çizim alanı bir kareyle sınırlı değildir.

Oluşturucunun ikinci sürümü `CPen` türü, stili, bitiş ucu ve birleşim özniteliklerinin bir birleşimini belirtir. Her kategorinin değerlerinin bit düzeyinde OR işleci kullanılarak birleştirilmesi gerekir (&#124;). Kalem türü aşağıdaki değerlerden biri olabilir:

- PS_GEOMETRIC geometrik kalem oluşturur.

- PS_COSMETIC bir yüzeysel kalem oluşturur.

   Oluşturucunun ikinci sürümü `CPen` *nPenStyle* için aşağıdaki kalem stillerini ekler:

- PS_ALTERNATE, diğer her pikseli ayarlayan bir kalem oluşturur. (Bu stil yalnızca yüzeysel kalemleri için geçerlidir.)

- PS_USERSTYLE, Kullanıcı tarafından sağlanan bir stil dizisi kullanan bir kalem oluşturur.

   Son sınır aşağıdaki değerlerden biri olabilir:

- PS_ENDCAP_ROUND End Caps değeri Round.

- PS_ENDCAP_SQUARE End Caps kare.

- PS_ENDCAP_FLAT End Caps bemol.

   JOIN aşağıdaki değerlerden biri olabilir:

- PS_JOIN_BEVEL birleşimler eğimli.

- PS_JOIN_MITER birleşimler, [Setmıterlimit](/windows/win32/api/wingdi/nf-wingdi-setmiterlimit) işlevi tarafından belirlenen geçerli sınırın içindeyse, JOIN bu sınırı aşarsa, eğimli olarak gelir.

- PS_JOIN_ROUND birleşimler Round.

*nWidth*<br/>
Kalemin genişliğini belirtir.

- Oluşturucunun ilk sürümü için, bu değer 0 ise, eşleme modundan bağımsız olarak cihaz birimlerindeki genişlik her zaman 1 pikseldir.

- Oluşturucunun ikinci sürümünde, *nPenStyle* PS_GEOMETRIC, Genişlik mantıksal birimlerde verilir. *NPenStyle* PS_COSMETIC ise, Width 'in 1 olarak ayarlanması gerekir.

*crColor*<br/>
Kalem için bir RGB rengi içerir.

*pLogBrush*<br/>
Bir yapıya işaret eder `LOGBRUSH` . *NPenStyle* PS_COSMETIC ise, yapının *lbColor* üyesi `LOGBRUSH` kalemin rengini belirtir ve yapının *lbStyle* üyesi `LOGBRUSH` BS_SOLID olarak ayarlanmalıdır. *NPenStyle* PS_GEOMETRIC ise, kalemin fırça özniteliklerini belirtmek için tüm üyelerin kullanılması gerekir.

*nStyleCount*<br/>
*LpStyle* dizisinin, doubleword birimi cinsinden uzunluğunu belirtir. *NPenStyle* PS_USERSTYLE değilse bu değer sıfır olmalıdır.

*lpStyle*<br/>
Doubleword değerleri dizisine işaret eder. İlk değer Kullanıcı tanımlı bir stilin ilk Dash uzunluğunu belirtir, ikinci değer ilk alanın uzunluğunu belirtir ve bu şekilde devam eder. *NPenStyle* PS_USERSTYLE değilse, bu işaretçi null olmalıdır.

### <a name="remarks"></a>Açıklamalar

Oluşturucuyu bağımsız değişken olmadan kullanırsanız, sonuçta elde edilen `CPen` nesneyi `CreatePen` ,, `CreatePenIndirect` veya `CreateStockObject` üye işlevleri ile başlatmalısınız.

Bağımsız değişken alan oluşturucuyu kullanırsanız, başka bir başlatma gerekmez. Bağımsız değişken içermeyen Oluşturucu her zaman başarılı olursa, bağımsız değişkenlerle Oluşturucu bir özel durum oluşturabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#99](../../mfc/codesnippet/cpp/cpen-class_1.cpp)]

## <a name="cpencreatepen"></a><a name="createpen"></a> CPen:: CreatePen

Belirtilen stili, genişliği ve fırça özniteliklerini içeren bir mantıksal yüzeysel veya geometrik kalem oluşturur ve `CPen` nesneye ekler.

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
Kalemin stilini belirtir. Olası değerler listesi için, [CPen](#cpen) Oluşturucu Içindeki *nPenStyle* parametresine bakın.

*nWidth*<br/>
Kalemin genişliğini belirtir.

- Öğesinin ilk sürümü için `CreatePen` , bu değer 0 ise, eşleme modundan bağımsız olarak cihaz birimlerindeki genişlik her zaman 1 pikseldir.

- İkinci sürümünde `CreatePen` , *nPenStyle* PS_GEOMETRIC, Genişlik mantıksal birimlerde verilir. *NPenStyle* PS_COSMETIC ise, Width 'in 1 olarak ayarlanması gerekir.

*crColor*<br/>
Kalem için bir RGB rengi içerir.

*pLogBrush*<br/>
[LOGBRUSH](/windows/win32/api/wingdi/ns-wingdi-logbrush) yapısına işaret eder. *NPenStyle* PS_COSMETIC, `lbColor` `LOGBRUSH` yapının üyesi kalemin rengini belirtir ve yapının *lbStyle* üyesi `LOGBRUSH` BS_SOLID olarak ayarlanmalıdır. NPenStyle PS_GEOMETRIC ise, kalemin fırça özniteliklerini belirtmek için tüm üyelerin kullanılması gerekir.

*nStyleCount*<br/>
*LpStyle* dizisinin, doubleword birimi cinsinden uzunluğunu belirtir. *NPenStyle* PS_USERSTYLE değilse bu değer sıfır olmalıdır.

*lpStyle*<br/>
Doubleword değerleri dizisine işaret eder. İlk değer Kullanıcı tanımlı bir stilin ilk Dash uzunluğunu belirtir, ikinci değer ilk alanın uzunluğunu belirtir ve bu şekilde devam eder. *NPenStyle* PS_USERSTYLE değilse, bu işaretçi null olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır olmayan veya yöntem başarısız olursa sıfır.

### <a name="remarks"></a>Açıklamalar

İlk sürümü `CreatePen` belirtilen stille, genişliğe ve renge sahip bir kalem başlatır. Kalem, daha sonra herhangi bir cihaz bağlamı için geçerli kalem olarak seçilebilir.

Genişliği 1 pikselden büyük olan kalemlerin her zaman PS_NULL, PS_SOLID veya PS_INSIDEFRAME stili olmalıdır.

Bir kalemin PS_INSIDEFRAME stili ve mantıksal renk tablosundaki renklerle eşleşmeyen bir renk varsa, kalem bir titremeli rengiyle çizilir. PS_SOLID kalem stili, titremeli rengi olan bir kalem oluşturmak için kullanılamaz. PS_INSIDEFRAME stil, kalem genişliği 1 ' den küçük veya buna eşitse PS_SOLID ile aynıdır.

İkinci sürümü `CreatePen` belirtilen stili, genişliği ve fırça özniteliklerini içeren bir mantıksal yüzeysel veya geometrik kalem başlatır. Bir yüzeysel kalemin genişliği her zaman 1 ' dir; bir geometrik kalemin genişliği her zaman dünya birimlerinde belirtilir. Bir uygulama bir mantıksal kalem oluşturduktan sonra, [CDC:: NesneSeç](../../mfc/reference/cdc-class.md#selectobject) işlevini çağırarak bu kalemi bir cihaz bağlamına seçebilir. Bir kalem bir cihaz bağlamına seçildikten sonra çizgiler ve eğriler çizmek için kullanılabilir.

- *NPenStyle* PS_COSMETIC ve PS_USERSTYLE, *lpStyle* dizisindeki girişler stil birimlerindeki çizgi ve boşluk uzunluklarının sayısını belirtir. Stil birimi, kalemin bir çizgiyi çizmek için kullanıldığı cihaz tarafından tanımlanır.

- *NPenStyle* PS_GEOMETRIC ve PS_USERSTYLE, *lpStyle* dizisindeki girişler mantıksal birimlerde çizgi ve boşluk uzunluklarının sayısını belirtir.

- *NPenStyle* PS_ALTERNATE ise, stil birimi yok sayılır ve diğer her piksel ayarlanır.

Bir uygulamaya artık belirli bir kalem gerekmiyorsa, kaynak artık kullanımda olmaması için [:D eleteobject](../../mfc/reference/cgdiobject-class.md#deleteobject) üye işlevini çağırmalıdır veya `CPen` nesneyi yok eder. Bir uygulama, bir cihaz bağlamında kalem seçildiğinde bir kalemi silmemelidir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#100](../../mfc/codesnippet/cpp/cpen-class_2.cpp)]

## <a name="cpencreatepenindirect"></a><a name="createpenindirect"></a> CPen:: Creatependolaylı

*Lplogpen* tarafından işaret edilen yapıda verilen stil, genişlik ve renge sahip bir kalem başlatır.

```
BOOL CreatePenIndirect(LPLOGPEN lpLogPen);
```

### <a name="parameters"></a>Parametreler

*lpLogPen*<br/>
Kalemle ilgili bilgileri içeren Windows [logpen](/windows/win32/api/Wingdi/ns-wingdi-logpen) yapısına işaret eder.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Genişliği 1 pikselden büyük olan kalemlerin her zaman PS_NULL, PS_SOLID veya PS_INSIDEFRAME stili olmalıdır.

Bir kalemin PS_INSIDEFRAME stili ve mantıksal renk tablosundaki renklerle eşleşmeyen bir renk varsa, kalem bir titremeli rengiyle çizilir. PS_INSIDEFRAME stili, kalem genişliği 1 ' e eşit veya bundan küçükse PS_SOLID ile aynıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#101](../../mfc/codesnippet/cpp/cpen-class_3.cpp)]

## <a name="cpenfromhandle"></a><a name="fromhandle"></a> CPen:: FromHandle

Bir `CPen` WINDOWS GDI kalem nesnesine bir tanıtıcı verilen nesneye bir işaretçi döndürür.

```
static CPen* PASCAL FromHandle(HPEN hPen);
```

### <a name="parameters"></a>Parametreler

*hPen*<br/>
`HPEN` Windows GDI kalemini işleme.

### <a name="return-value"></a>Dönüş Değeri

`CPen`Başarılı olursa nesne için bir işaretçi; aksi takdırde null.

### <a name="remarks"></a>Açıklamalar

Bir `CPen` nesne tutamaya iliştirilmişse, geçici bir `CPen` nesne oluşturulur ve eklenir. Bu geçici `CPen` nesne yalnızca uygulamanın olay döngüsünde bir sonraki kez boşta kalması durumunda geçerlidir. bu süre, tüm geçici grafik nesneleri silinir. Diğer bir deyişle, geçici nesne yalnızca bir pencere iletisinin işlenmesi sırasında geçerlidir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#105](../../mfc/codesnippet/cpp/cpen-class_4.cpp)]

## <a name="cpengetextlogpen"></a><a name="getextlogpen"></a> CPen:: GetExtLogPen

`EXTLOGPEN`Temel yapıyı alır.

```
int GetExtLogPen(EXTLOGPEN* pLogPen);
```

### <a name="parameters"></a>Parametreler

*pLogPen*<br/>
Kalem hakkında bilgi içeren bir [extlogpen](/windows/win32/api/wingdi/ns-wingdi-extlogpen) yapısına işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`EXTLOGPEN`Yapı, bir kalemin stil, genişlik ve fırça özniteliklerini tanımlar. Örneğin, `GetExtLogPen` bir kalemin belirli stiliyle eşleştirmek için çağrısı yapın.

Kalem öznitelikleri hakkında bilgi için Windows SDK aşağıdaki konulara bakın:

- [GetObject](/windows/win32/api/wingdi/nf-wingdi-getobject)

- [EXTLOGPEN](/windows/win32/api/wingdi/ns-wingdi-extlogpen)

- [LOGPEN](/windows/win32/api/wingdi/ns-wingdi-logpen)

- [ExtCreatePen](/windows/win32/api/wingdi/nf-wingdi-extcreatepen)

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `GetExtLogPen` bir kalemin özniteliklerini almak için çağrıyı gösterir ve ardından aynı renge sahip yeni bir yüzeysel kalem oluşturur.

[!code-cpp[NVC_MFCDocView#102](../../mfc/codesnippet/cpp/cpen-class_5.cpp)]

## <a name="cpengetlogpen"></a><a name="getlogpen"></a> CPen:: GetLogPen

`LOGPEN`Temel yapıyı alır.

```
int GetLogPen(LOGPEN* pLogPen);
```

### <a name="parameters"></a>Parametreler

*pLogPen*<br/>
Kalem hakkında bilgi içeren bir [logpen](/windows/win32/api/wingdi/ns-wingdi-logpen) yapısına işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`LOGPEN`Yapı, bir kalemin stilini, rengini ve modelini tanımlar.

Örneğin, `GetLogPen` kalemin belirli bir stilini eşleştirmek için çağırın.

Kalem öznitelikleri hakkında bilgi için Windows SDK aşağıdaki konulara bakın:

- [GetObject](/windows/win32/api/wingdi/nf-wingdi-getobject)

- [LOGPEN](/windows/win32/api/wingdi/ns-wingdi-logpen)

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `GetLogPen` bir kalem karakteri almak için çağrıyı gösterir ve ardından aynı renge sahip yeni ve düz bir kalem oluşturur.

[!code-cpp[NVC_MFCDocView#103](../../mfc/codesnippet/cpp/cpen-class_6.cpp)]

## <a name="cpenoperator-hpen"></a><a name="operator_hpen"></a> CPen:: operator HPEN

Nesnenin ekli Windows GDI işleyicisini alır `CPen` .

```
operator HPEN() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, nesne tarafından temsil edilen Windows GDI nesnesine yönelik bir tanıtıcı `CPen` ; aksi takdırde null.

### <a name="remarks"></a>Açıklamalar

Bu işleç, HPEN nesnesinin doğrudan kullanımını destekleyen bir atama işleçtir.

Grafik nesnelerini kullanma hakkında daha fazla bilgi için Windows SDK [grafik nesneleri](/windows/win32/gdi/graphic-objects) makalesine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#104](../../mfc/codesnippet/cpp/cpen-class_7.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CGdiObject sınıfı](../../mfc/reference/cgdiobject-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CBrush sınıfı](../../mfc/reference/cbrush-class.md)
