---
title: CFont Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CFont
- AFXWIN/CFont
- AFXWIN/CFont::CFont
- AFXWIN/CFont::CreateFont
- AFXWIN/CFont::CreateFontIndirect
- AFXWIN/CFont::CreatePointFont
- AFXWIN/CFont::CreatePointFontIndirect
- AFXWIN/CFont::FromHandle
- AFXWIN/CFont::GetLogFont
helpviewer_keywords:
- CFont [MFC], CFont
- CFont [MFC], CreateFont
- CFont [MFC], CreateFontIndirect
- CFont [MFC], CreatePointFont
- CFont [MFC], CreatePointFontIndirect
- CFont [MFC], FromHandle
- CFont [MFC], GetLogFont
ms.assetid: 3fad6bfe-d6ce-4ab9-967a-5ce0aa102800
ms.openlocfilehash: 36fd469b182d5f3e0d3449112d04c1a8623d7526
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373837"
---
# <a name="cfont-class"></a>CFont Sınıfı

Bir Windows grafik aygıtı arabirimini (GDI) kapsüller ve yazı tipini işlemek için üye işlevler sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CFont : public CGdiObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CFont::CFont](#cfont)|Bir `CFont` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CFont::CreateFont](#createfont)|Belirtilen özelliklere `CFont` sahip bir baş harfe ayrılır.|
|[CFont::CreateFontIndirect](#createfontindirect)|Bir yapıda `CFont` verilen özelliklere sahip `LOGFONT` bir nesneyi başolarak karşılar.|
|[CFont::CreatePointFont](#createpointfont)|Belirtilen yüksekliğe `CFont` sahip bir noktayı, bir noktanın onda birinde ölçülen bir harfi ve yazı tipini başolarak karşılar.|
|[CFont::CreatePointFontIndirect](#createpointfontindirect)|Yazı `CreateFontIndirect` tipi yüksekliğinin mantıksal birimler yerine bir noktanın onda biri olarak ölçülmesi dışında aynıdır.|
|[CFont::FromHandle](#fromhandle)|Windows HFONT `CFont` verildiğinde bir nesneye işaretçi döndürür.|
|[CFont::GetlogFont](#getlogfont)|Nesneye `CFont` `LOGFONT` iliştirilen mantıksal yazı tipi hakkında bilgi ile a doldurur.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CFont::operatör HFONT](#operator_hfont)|Nesneye bağlı Windows GDI yazı `CFont` tipi tutamacını döndürür.|

## <a name="remarks"></a>Açıklamalar

`CFont` Bir nesne kullanmak için, `CFont` bir nesne oluşturmak ve CreateFont , [CreateFontIndirect](#createfontindirect), CreatePointFont , veya [CreateFont](#createfont) [CreatePointFontIndirect](#createpointfontindirect)ile bir Windows yazı tipi eklemek ve sonra yazı tipi işlemek için nesnenin üye işlevlerini kullanın. [CreatePointFont](#createpointfont)

`CreatePointFont` Ve `CreatePointFontIndirect` işlevlerin kullanımı genellikle, `CreateFont` yazı `CreateFontIndirect` tipinin yüksekliği için bir nokta boyutundan mantıksal birimlere otomatik olarak dönüştürme yaptıklarından daha kolaydır.

Daha fazla `CFont`bilgi için [Bkz. Grafik Nesneler.](../../mfc/graphic-objects.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Cgdiobject](../../mfc/reference/cgdiobject-class.md)

`CFont`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="cfontcfont"></a><a name="cfont"></a>CFont::CFont

Bir `CFont` nesne inşa eder.

```
CFont();
```

### <a name="remarks"></a>Açıklamalar

Ortaya çıkan `CreateFont`nesne , , `CreateFontIndirect` `CreatePointFont`, veya `CreatePointFontIndirect` kullanılabilir önce ile başharflealınmalıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#70](../../mfc/codesnippet/cpp/cfont-class_1.cpp)]

## <a name="cfontcreatefont"></a><a name="createfont"></a>CFont::CreateFont

Belirtilen özelliklere `CFont` sahip bir nesneyi başolarak karşılar.

```
BOOL CreateFont(
    int nHeight,
    int nWidth,
    int nEscapement,
    int nOrientation,
    int nWeight,
    BYTE bItalic,
    BYTE bUnderline,
    BYTE cStrikeOut,
    BYTE nCharSet,
    BYTE nOutPrecision,
    BYTE nClipPrecision,
    BYTE nQuality,
    BYTE nPitchAndFamily,
    LPCTSTR lpszFacename);
```

### <a name="parameters"></a>Parametreler

*Nheight*<br/>
Yazı tipinin istenen yüksekliğini (mantıksal birimler halinde) belirtir. Açıklama `lfHeight` için Windows SDK'daki [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw)yapısının üyesine bakın. *nHeight'ın* mutlak değeri dönüştürüldükten sonra 16.384 aygıt birimini geçmemelidir. Tüm yükseklik karşılaştırmaları için, yazı tipi eşlemesi, tüm yazı tipleri istenen boyutu aşıyorsa, istenen boyutu veya en küçük yazı tipini aşmayan en büyük yazı tipini arar.

*Nwidth*<br/>
Yazı tipindeki karakterlerin ortalama genişliğini (mantıksal birimler halinde) belirtir. *nWidth* 0 ise, aygıtın en boy oranı, farkın mutlak değerine göre belirlenen en yakın eşleşmeyi bulmak için kullanılabilir yazı tiplerinin sayısallaştırma en boy oranıyla eşleşir.

*nEscapement*<br/>
Kaçış vektörü ile görüntü yüzeyinin x ekseni arasındaki açıyı (0,1 derecelik birimler halinde) belirtir. Kaçış vektörü, bir çizgiüzerindeki ilk ve son karakterlerin kökenleri arasındaki çizgidir. Açı x ekseninden saat yönünün tersine ölçülür. Daha `lfEscapement` fazla bilgi `LOGFONT` için Windows SDK'daki yapıdaki üyeye bakın.

*nOrororasyon*<br/>
Bir karakterin taban çizgisi ile x ekseni arasındaki açıyı (0,1 derecelik birimler halinde) belirtir. Açı, y-yönünün aşağı ve saat yönünde olduğu koordinat sistemleri için x ekseninden saat yönünün karşıölçülür.

*nAğırlık*<br/>
Yazı tipi ağırlığını belirtir (1000'de mürekkepli piksellerde). Daha fazla bilgi için `LOGFONT` Windows SDK'daki yapıdaki *lfWeight* üyesine bakın. Açıklanan değerler yaklaşık; gerçek görünüm yazı tipine bağlıdır. Bazı yazı tiplerinde yalnızca FW_NORMAL, FW_REGULAR ve FW_BOLD ağırlıkları vardır. FW_DONTCARE belirtilirse, varsayılan bir ağırlık kullanılır.

*bItalik*<br/>
Yazı tipinin italik olup olmadığını belirtir.

*bUnderline*<br/>
Yazı tipinin altı çizili olup olmadığını belirtir.

*cStrikeOut*<br/>
Yazı tipindeki karakterlerin çıkarılıp çıkarılmayacağını belirtir. Sıfır olmayan bir değere ayarlanmışsa, bir strikeout yazı tipi belirtir.

*nCharSet*<br/>
Yazı tipinin karakter kümesini belirtir `lfCharSet` Değerler `LOGFONT` listesi için Windows SDK'daki yapıdaki üyeyi görün.

OEM karakter kümesi sisteme bağlıdır.

Sistemde başka karakter kümelerine sahip yazı tipleri bulunabilir. Bilinmeyen karakter kümesine sahip bir yazı tipi kullanan bir uygulama, bu yazı tipiyle oluşturulacak dizeleri çevirmeye veya yorumlamaya çalışmamalıdır. Bunun yerine, dizeleri doğrudan çıkış aygıtı sürücüsüne geçirilmelidir.

Yazı tipi eşleği DEFAULT_CHARSET değerini kullanmaz. Bir uygulama, bir yazı tipinin adını ve boyutunun mantıksal yazı tipini tam olarak tanımlamasına izin vermek için bu değeri kullanabilir. Belirtilen ada sahip bir yazı tipi yoksa, herhangi bir karakter kümesinden bir yazı tipi belirtilen yazı tipi nin yerine geçilebilir. Beklenmeyen sonuçları önlemek için, uygulamalar DEFAULT_CHARSET değerini dikkatli kullanmalıdır.

*nOutPrecision*<br/>
İstenilen çıkış hassasiyetini belirtir. Çıktı kesinlemi, çıktının istenen yazı tipinin yüksekliği, genişliği, karakter yönü, kaçış ve perdeyle ne kadar yakından eşleşmesi gerektiğini tanımlar. Değerler `lfOutPrecision` listesi ve `LOGFONT` daha fazla bilgi için Windows SDK'daki yapıdaki üyeye bakın.

*nClipPrecision*<br/>
İstenilen kırpma hassasiyetini belirtir. Kırpma hassasiyeti, kırpma bölgesinin kısmen dışında kalan karakterlerin nasıl kesişeceklerini tanımlar. Değerler `lfClipPrecision` listesi için `LOGFONT` Windows SDK'daki yapıdaki üyeye bakın.

Katıştılmış salt okunur yazı tipini kullanmak için uygulamanın CLIP_ENCAPSULATE belirtmesi gerekir.

Aygıt, TrueType ve vektör yazı tiplerinin tutarlı bir şekilde döndürülmesini sağlamak için, bir uygulama CLIP_LH_ANGLES değerini diğer *nClipPrecision* değerlerinden herhangi biriyle birleştirmek için OR işleci'ni kullanabilir. CLIP_LH_ANGLES biti ayarlanırsa, tüm yazı tiplerinin döndürmesi koordinat sisteminin yönünün solak mı yoksa sağ elle mi olduğuna bağlıdır. (Koordinat sistemlerinin yönü hakkında daha fazla bilgi için *nOrientation* parametresinin açıklamasına bakın.) CLIP_LH_ANGLES ayarlı değilse, aygıt yazı tipleri her zaman saat yönünün tersine döner, ancak diğer yazı tiplerinin döndürmesi koordinat sisteminin yönlendirmeye bağlıdır.

*nKalite*<br/>
GDI'nin mantıksal yazı tipi özniteliklerini gerçek bir fiziksel yazı tipininkilerle eşleştirmeye ne kadar dikkatli çalışması gerektiğini tanımlayan yazı tipinin çıktı kalitesini belirtir. Değerler `lfQuality` listesi için `LOGFONT` Windows SDK'daki yapıdaki üyeye bakın.

*nPitchAndFamily*<br/>
Yazı tipinin perdesini ve ailesini belirtir. Değerler `lfPitchAndFamily` listesi ve `LOGFONT` daha fazla bilgi için Windows SDK'daki yapıdaki üyeye bakın.

*lpszFacename*<br/>
Yazı `CString` tipinin yazı tipi adını belirten null-sonlandırılan dize için bir veya işaretçi. Bu dize uzunluğu 30 karakter geçmemelidir. Windows [EnumFontFamilies](/windows/win32/api/wingdi/nf-wingdi-enumfontfamiliesw) işlevi, şu anda kullanılabilen tüm yazı tiplerini sayısallandırmak için kullanılabilir. *lpszFacename* NULL ise, GDI aygıta bağımsız bir yazı tipi kullanır.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Yazı tipi daha sonra herhangi bir aygıt bağlamı için yazı tipi olarak seçilebilir.

İşlev `CreateFont` yeni bir Windows GDI yazı tipi oluşturmaz. Yalnızca GDI için kullanılabilir fiziksel yazı tiplerinden en yakın eşleşmeyi seçer.

Uygulamalar, mantıksal bir yazı tipi oluştururken çoğu parametre için varsayılan ayarları kullanabilir. Her zaman belirli değerler verilmelidir *parametreleri nHeight* ve *lpszFacename*vardır. *nHeight* ve *lpszFacename* uygulama tarafından ayarlanmazsa, oluşturulan mantıksal yazı tipi aygıta bağlıdır.

İşlev tarafından `CFont` oluşturulan nesneyle bitirdiğinizde, aygıt bağlamına farklı bir yazı `CFont` tipi seçmek için kullanın `CDC::SelectObject` ve artık gerekli olmayan nesneyi silin. `CreateFont`

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#71](../../mfc/codesnippet/cpp/cfont-class_2.cpp)]

## <a name="cfontcreatefontindirect"></a><a name="createfontindirect"></a>CFont::CreateFontIndirect

`CFont` [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw)yapısında verilen özelliklere sahip bir nesneyi başharfe ait hale getirmeyi sağlar.

```
BOOL CreateFontIndirect(const LOGFONT* lpLogFont);
```

### <a name="parameters"></a>Parametreler

*lpLogFont*<br/>
Mantıksal yazı `LOGFONT` tipinin özelliklerini tanımlayan bir yapıyı işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Yazı tipi daha sonra herhangi bir aygıt için geçerli yazı tipi olarak seçilebilir.

Bu yazı tipi [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) yapısında belirtilen özelliklere sahiptir. Yazı tipi [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) üye işlevi kullanılarak seçildiğinde, GDI yazı tipi mapper varolan bir fiziksel yazı tipi ile mantıksal yazı tipi eşleştirmeye çalışır. Yazı tipi eşlemesi mantıksal yazı tipi için tam bir eşleşme bulamazsa, özellikleri istenen özelliklerin mümkün olduğunca çok olduğu kadar eşleşen alternatif bir yazı tipi sağlar.

İşlev tarafından oluşturulan `CFont` nesneye artık ihtiyacınız `CDC::SelectObject` olmadığında, aygıt bağlamına farklı bir `CFont` yazı tipi seçmek için kullanın ve artık gerekli olmayan nesneyi silin. `CreateFontIndirect`

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#72](../../mfc/codesnippet/cpp/cfont-class_3.cpp)]

## <a name="cfontcreatepointfont"></a><a name="createpointfont"></a>CFont::CreatePointFont

Bu işlev, belirli bir yazı tipi ve nokta boyutu bir yazı tipi oluşturmak için basit bir yol sağlar.

```
BOOL CreatePointFont(
    int nPointSize,
    LPCTSTR lpszFaceName,
    CDC* pDC = NULL);
```

### <a name="parameters"></a>Parametreler

*nPointSize*<br/>
Bir noktanın onda birinde istenen yazı tipi yüksekliği. (Örneğin, 12 noktalı bir yazı tipi istemek için 120'yi geç.)

*lpszFaceName*<br/>
Yazı `CString` tipinin yazı tipi adını belirten null-sonlandırılan dize için bir veya işaretçi. Bu dize uzunluğu 30 karakter geçmemelidir. Windows 'EnumFontFamilies işlevi, şu anda kullanılabilen tüm yazı tiplerini sayısallandırmak için kullanılabilir. *lpszFaceName* NULL ise, GDI aygıta bağımsız bir yazı tipi kullanır.

*Pdc*<br/>
*NPointSize'daki* yüksekliği mantıksal birimlere dönüştürmek için kullanılacak [CDC](../../mfc/reference/cdc-class.md) nesnesine işaretçi. NULL ise, dönüştürme için bir ekran aygıtı bağlamı kullanılır.

### <a name="return-value"></a>Dönüş Değeri

Sıfır sız, başarılı ysa, aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

*NPointSize'daki* yüksekliği *pDC*tarafından işaret edilen CDC nesnesini kullanarak mantıksal birimlere otomatik olarak dönüştürür.

İşlev tarafından `CFont` oluşturulan nesneyle bitirdiğinizde, önce yazı tipini aygıt bağlamının dışına seçin, ardından nesneyi `CFont` silin. `CreatePointFont`

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#73](../../mfc/codesnippet/cpp/cfont-class_4.cpp)]

## <a name="cfontcreatepointfontindirect"></a><a name="createpointfontindirect"></a>CFont::CreatePointFontIndirect

Bu işlev [CreateFontIndirect](#createfontindirect) ile aynıdır, `lfHeight` ancak `LOGFONT` üye aygıt birimleri yerine bir noktanın onda biri olarak yorumlanır.

```
BOOL CreatePointFontIndirect(
    const LOGFONT* lpLogFont,
    CDC* pDC = NULL);
```

### <a name="parameters"></a>Parametreler

*lpLogFont*<br/>
Mantıksal yazı tipinin özelliklerini tanımlayan bir [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) yapısına işaret eder. Yapının `lfHeight` `LOGFONT` üyesi mantıksal birimler yerine bir noktanın onda biri olarak ölçülür. (Örneğin, 12 noktalı yazı tipi istemek için 120 olarak ayarlayın.) `lfHeight`

*Pdc*<br/>
Yüksekliği `lfHeight` mantıksal birimlere dönüştürmek için kullanılacak [CDC](../../mfc/reference/cdc-class.md) nesnesine işaretçi. NULL ise, dönüştürme için bir ekran aygıtı bağlamı kullanılır.

### <a name="return-value"></a>Dönüş Değeri

Sıfır sız, başarılı ysa, aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, `lfHeight` `LOGFONT` yapıyı Windows'a geçirmeden önce *pDC* tarafından işaret edilen CDC nesnesini kullanarak yüksekliği otomatik olarak mantıksal birimlere dönüştürür.

İşlev tarafından `CFont` oluşturulan nesneyle bitirdiğinizde, önce yazı tipini aygıt bağlamının dışına seçin, ardından nesneyi `CFont` silin. `CreatePointFontIndirect`

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#74](../../mfc/codesnippet/cpp/cfont-class_5.cpp)]

## <a name="cfontfromhandle"></a><a name="fromhandle"></a>CFont::FromHandle

Bir HFONT `CFont` tanıtıcısı Windows GDI yazı tipi nesnesine verildiğinde bir işaretçiyi nesneye döndürür.

```
static CFont* PASCAL FromHandle(HFONT hFont);
```

### <a name="parameters"></a>Parametreler

*hFont*<br/>
Windows yazı tipine bir HFONT tutamacı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa `CFont` nesneye işaretçi; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Bir `CFont` nesne tutamacına zaten eklenmiş değilse, geçici `CFont` bir nesne oluşturulur ve eklenir. Bu `CFont` geçici nesne yalnızca, uygulamanın olay döngüsünde boşta kalma süresine sahip olduğu ve tüm geçici grafik nesnelerinin silindiği bir sonraki zamana kadar geçerlidir. Bunu söylemenin başka bir yolu, geçici nesnenin yalnızca bir pencere iletisinin işlenmesi sırasında geçerli olmasıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#75](../../mfc/codesnippet/cpp/cfont-class_6.cpp)]

## <a name="cfontgetlogfont"></a><a name="getlogfont"></a>CFont::GetlogFont

Yapının `LOGFONT` bir kopyasını almak için `CFont`bu işlevi arayın.

```
int GetLogFont(LOGFONT* pLogFont);
```

### <a name="parameters"></a>Parametreler

*pLogFont*<br/>
Yazı tipi bilgilerini almak için [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) yapısını işaretle.

### <a name="return-value"></a>Dönüş Değeri

Nonzero işlevi başarılı olursa, aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#76](../../mfc/codesnippet/cpp/cfont-class_7.cpp)]

## <a name="cfontoperator-hfont"></a><a name="operator_hfont"></a>CFont::operatör HFONT

`CFont` Nesneye bağlı yazı tipinin Windows GDI tutamacını almak için bu işleci kullanın.

```
operator HFONT() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı `CFont` olursa eklenen Windows GDI yazı tipi nesnesinin tutamacı; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Bu işleç, Yazı Tipleri ve `CFont` [Metin'e](/windows/win32/gdi/fonts-and-text)dönüşümler için `CFont` otomatik olarak kullanıldığından, nesneleri HFONT'lar bekleyen işlevlere geçirebilirsiniz.

Grafik nesneleri kullanma hakkında daha fazla bilgi için Windows SDK'daki [Grafik Nesneler'e](/windows/win32/gdi/graphic-objects) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#77](../../mfc/codesnippet/cpp/cfont-class_8.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[CGdiObject Sınıfı](../../mfc/reference/cgdiobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
