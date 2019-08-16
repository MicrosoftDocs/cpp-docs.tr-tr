---
title: CFont sınıfı
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
ms.openlocfilehash: c37b2f657105e0065e0cddb2c508424bd6c89b0a
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69506497"
---
# <a name="cfont-class"></a>CFont sınıfı

Windows grafik cihaz arabirimi (GDI) yazı tipini kapsüller ve yazı tipini işlemek için üye işlevleri sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CFont : public CGdiObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CFont:: CFont](#cfont)|Bir `CFont` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CFont:: CreateFont](#createfont)|Belirtilen özelliklerle `CFont` bir ile başlatır.|
|[CFont:: CreateFontIndirect](#createfontindirect)|Bir `LOGFONT` yapıda `CFont` verilen özelliklerle bir nesnesi başlatır.|
|[CFont:: CreatePointFont](#createpointfont)|Belirtilen yüksekliğiyle, bir noktanın onda birinde ölçülen ve yazı biçiminin üzerine bir `CFont` başlatır.|
|[CFont:: CreatePointFontIndirect](#createpointfontindirect)|Yazı tipi `CreateFontIndirect` yüksekliğinin, mantıksal birimler yerine bir noktanın onda ölçüldüğü ile aynıdır.|
|[CFont:: FromHandle](#fromhandle)|Bir Windows hfont verildiğinde `CFont` bir nesneye bir işaretçi döndürür.|
|[CFont:: GetLogFont](#getlogfont)|Nesneye`CFont` eklenen `LOGFONT` mantıksal yazı tipiyle ilgili bilgileri bir ile doldurur.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CFont:: operator HFONT](#operator_hfont)|`CFont` Nesnesine eklenen Windows GDI yazı tipi tanıtıcısını döndürür.|

## <a name="remarks"></a>Açıklamalar

Bir `CFont` nesne kullanmak için, bir `CFont` nesne oluşturun ve [CreateFont](#createfont), createfontınmıtfont veya [createpointfontdolaylı](#createpointfontindirect)ile bir Windows yazı tipi ekleyin ve ardından nesnenin üyesini kullanın [](#createfontindirect) [](#createpointfont) yazı tipini işlemek için işlevler.

Ve işlevlerinin `CreatePointFontIndirect` kullanımı genellikle`CreateFont` dahakolayolurvebuyanayazıtipininyüksekliğininbirnoktaboyutundanmantıksalbirimlereotomatik`CreateFontIndirect` olarak dönüştürülmesini sağlar. `CreatePointFont`

Hakkında `CFont`daha fazla bilgi için bkz. [grafik nesneleri](../../mfc/graphic-objects.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CFont`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

##  <a name="cfont"></a>CFont:: CFont

Bir `CFont` nesnesi oluşturur.

```
CFont();
```

### <a name="remarks"></a>Açıklamalar

Elde `CreateFont`edilen nesne `CreateFontIndirect` `CreatePointFontIndirect` , kullanılmadan önce,, veya ile başlatılmalıdır. `CreatePointFont`

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#70](../../mfc/codesnippet/cpp/cfont-class_1.cpp)]

##  <a name="createfont"></a>CFont:: CreateFont

Belirtilen özelliklerle `CFont` bir nesne başlatır.

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

*nHeight*<br/>
Yazı tipinin istenen yüksekliğini (mantıksal birimler cinsinden) belirtir. Bir açıklama için Windows SDK [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw)yapısının üyesinebakın.`lfHeight` *NHeight* öğesinin mutlak değeri, dönüştürüldükten sonra 16.384 cihaz birimini aşmamalıdır. Tüm yükseklik karşılaştırmaları için, yazı tipi Eşleyici istenen boyutu aşmayan en büyük yazı tipini veya tüm fontlar istenen boyutu aşarsa en küçük yazı tipini arar.

*nWidth*<br/>
Yazı tipindeki karakterlerin ortalama genişliğini (mantıksal birimler cinsinden) belirtir. *NWidth* 0 ise, cihazın en boy oranı, fark değerinin mutlak değeri tarafından belirlenen en yakın eşleşmeyi bulmak için kullanılabilir yazı tiplerinin sayısal oranına göre eşleştirilir.

*Nessepement*<br/>
Yürüyen pement vektörü ile görüntü yüzeyinin x ekseni arasındaki açıyı (0,1 derece birimler cinsinden) belirtir. Yürüyen pement vektörü, satırdaki ilk ve son karakterlerin kaynakları arasındaki satırdır. Açı x ekseninden saatin tersi yönde ölçülür. Daha fazla bilgi için Windows SDK `LOGFONT` yapısındaki üyeyebakın.`lfEscapement`

*nOrientation*<br/>
Bir karakterin ve x ekseninin taban çizgisi arasındaki açıyı (0,1 derece birimler cinsinden) belirtir. Açı, y yönünün doğru olduğu koordinat sistemleri için x ekseninden ve y yönünün kullanıldığı koordinat sistemleri için x ekseninden saat yönünde ölçülür.

*nWeight*<br/>
Yazı tipi kalınlığını belirtir (1000 başına düşen piksellerde). Daha fazla bilgi için Windows SDK `LOGFONT` yapısındaki *lfWeight* üyesine bakın. Açıklanan değerler yaklaşık değerlerdir; Asıl görünüm, yazı tipine bağlıdır. Bazı yazı tiplerinde yalnızca FW_NORMAL, FW_REGULAR ve FW_BOLD ağırlıkları vardır. FW_DONTCARE belirtilmişse, varsayılan bir ağırlık kullanılır.

*Bitic*<br/>
Yazı tipinin italik olup olmadığını belirtir.

*bUnderline*<br/>
Yazı tipinin altı çizili olup olmadığını belirtir.

*Cüstü çizili*<br/>
Yazı tipindeki karakterlerin aşağı çizili olup olmayacağını belirtir. Sıfır dışında bir değere ayarlandıysa, üstü çizili yazı tipini belirtir.

*nCharSet*<br/>
Yazı tipinin karakter seti değerini belirtir bir `lfCharSet` değer listesi için `LOGFONT` Windows SDK yapısındaki üyeyi görüntüleyin.

OEM karakter kümesi sisteme bağımlıdır.

Diğer karakter kümelerine sahip yazı tipleri sistemde bulunabilir. Bilinmeyen bir karakter kümesine sahip bir yazı tipi kullanan bir uygulama, bu yazı tipiyle işlenecek dizeleri çevirmeye veya yorumlamaya çalışmamalıdır. Bunun yerine, dizeler doğrudan çıkış cihazı sürücüsüne geçirilmelidir.

Yazı tipi Eşleyici, DEFAULT_CHARSET değerini kullanmaz. Bir uygulama bu değeri, bir yazı tipinin adının ve boyutunun mantıksal yazı tipi tam olarak tanımlanmasına olanak tanımak için kullanabilir. Belirtilen ada sahip bir yazı tipi yoksa, herhangi bir karakter kümesindeki bir yazı tipi belirtilen yazı tipi için değiştirilebilir. Beklenmedik sonuçlara engel olmak için, uygulamalar DEFAULT_CHARSET değerini gelişigüzel bir şekilde kullanmalıdır.

*nOutPrecision*<br/>
İstenen çıkış hassasiyetini belirtir. Çıkış hassasiyeti, çıktının istenen yazı tipinin yüksekliği, genişliği, karakter yönü, yürüyen soyı ve sıklık ile ne kadar yakın olduğunu tanımlar. Değer listesi ve daha fazla `LOGFONT` bilgi için Windows SDK yapısındaki üyeyebakın.`lfOutPrecision`

*nClipPrecision*<br/>
İstenen kırpma hassasiyetini belirtir. Kırpma hassasiyeti, kırpma bölgesinin kısmen dışında olan karakterlerin nasıl kırpılmasını tanımlar. Değerlerin listesi için Windows SDK `LOGFONT` yapısındaki üyeyebakın.`lfClipPrecision`

Katıştırılmış salt biçimli bir yazı tipi kullanmak için, bir uygulamanın CLIP_ENCAPSULATE belirtmesi gerekir.

Cihaz, TrueType ve vektör yazı tiplerinin tutarlı bir şekilde döndürülmesini sağlamak için, bir uygulama OR işlecini kullanarak CLIP_LH_ANGLES değerini diğer *nClipPrecision* değerlerinden herhangi biriyle birleştirebilir. CLIP_LH_ANGLES biti ayarlandıysa, tüm yazı tiplerinin dönüşü koordinat sisteminin yönünün sola veya sağ elli olmasına bağlıdır. (Koordinat sistemlerinin yönü hakkında daha fazla bilgi için, *nOrientation* parametresinin açıklamasına bakın.) CLIP_LH_ANGLES ayarlanmamışsa, cihaz yazı tipleri her zaman saatin tersi döndürülür, ancak diğer yazı tiplerinin dönüşü koordinat sisteminin yönüne bağlıdır.

*nQuality*<br/>
GDI 'nın mantıksal yazı tipi özniteliklerini gerçek fiziksel yazı tipine göre eşleştirmeye ne kadar dikkatli olduğunu tanımlayan yazı tipinin çıkış kalitesini belirtir. Değerlerin listesi için Windows SDK `LOGFONT` yapısındaki üyeyebakın.`lfQuality`

*Nstachandfamily*<br/>
Yazı tipinin perdesini ve ailesini belirtir. Değer listesi ve daha fazla `LOGFONT` bilgi için Windows SDK yapısındaki üyeyebakın.`lfPitchAndFamily`

*lpszFacename*<br/>
Yazı tipinin yazı tipi adını belirten null ile sonlandırılmış bir dize için veyaişaretçisi.`CString` Bu dizenin uzunluğu en fazla 30 karakter uzunluğunda olmalıdır. Windows [Enumfontaileleri](/windows/win32/api/wingdi/nf-wingdi-enumfontfamiliesw) işlevi, şu anda kullanılabilir olan tüm yazı tiplerini listelemek için kullanılabilir. *LPSZFACENAME* null Ise, GDI cihazdan bağımsız bir yazı tipi kullanır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Yazı tipi daha sonra herhangi bir cihaz bağlamının yazı tipi olarak seçilebilir.

`CreateFont` İşlev yeni bir Windows GDI yazı tipi oluşturmaz. Yalnızca GDI için kullanılabilir fiziksel yazı tiplerinin en yakın eşleşmesini seçer.

Uygulamalar, mantıksal bir yazı tipi oluştururken çoğu parametre için varsayılan ayarları kullanabilir. Her zaman belirli değerler verilmesi gereken parametreler *nHeight* ve *lpszFacename*. Eğer *nHeight* ve *lpszFacename* uygulama tarafından ayarlanmamışsa, oluşturulan mantıksal yazı tipi cihaza bağımlıdır.

İşlev tarafından oluşturulan `CFont` nesneyle bitirdiğinizde, cihaz bağlamında farklı bir yazı tipi `CDC::SelectObject` seçmek için kullanın, ardından artık gerekli olmayan `CFont` nesneyi silin. `CreateFont`

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#71](../../mfc/codesnippet/cpp/cfont-class_2.cpp)]

##  <a name="createfontindirect"></a>CFont:: CreateFontIndirect

`CFont` [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw)yapısında verilen özelliklerle bir nesnesi başlatır.

```
BOOL CreateFontIndirect(const LOGFONT* lpLogFont);
```

### <a name="parameters"></a>Parametreler

*lpLogFont*<br/>
Mantıksal yazı tipinin `LOGFONT` özelliklerini tanımlayan bir yapıya işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Yazı tipi daha sonra herhangi bir cihaz için geçerli yazı tipi olarak seçilebilir.

Bu yazı tipi, [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) yapısında belirtilen özelliklere sahiptir. Yazı tipi [CDC:: NesneSeç](../../mfc/reference/cdc-class.md#selectobject) üye işlevi kullanılarak SEÇILDIĞINDE, GDI yazı tipi Eşleyici, varolan bir fiziksel yazı tipiyle mantıksal yazı tipiyle eşleştirmeye çalışır. Yazı tipi Eşleyicisi mantıksal yazı tipi için tam bir eşleşme bulamazsa, özellikleri istenen özelliklerden çok sayıda olacak şekilde eşleşen alternatif bir yazı tipi sağlar.

İşlev tarafından oluşturulan `CFont` nesneye artık ihtiyacınız kalmadığında, cihaz bağlamında farklı bir yazı `CDC::SelectObject` tipi seçmek için kullanın, ardından artık gerekli olmayan `CFont` nesneyi silin. `CreateFontIndirect`

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#72](../../mfc/codesnippet/cpp/cfont-class_3.cpp)]

##  <a name="createpointfont"></a>CFont:: CreatePointFont

Bu işlev, belirtilen yazı biçiminin ve nokta boyutunun yazı tipinin oluşturulması için basit bir yol sağlar.

```
BOOL CreatePointFont(
    int nPointSize,
    LPCTSTR lpszFaceName,
    CDC* pDC = NULL);
```

### <a name="parameters"></a>Parametreler

*nPointSize*<br/>
Bir noktanın onda istenen yazı tipi yüksekliği. (Örneğin, 12 puntoluk bir yazı tipi istemek için 120 geçirin.)

*lpszFaceName*<br/>
Yazı tipinin yazı tipi adını belirten null ile sonlandırılmış bir dize için veyaişaretçisi.`CString` Bu dizenin uzunluğu en fazla 30 karakter uzunluğunda olmalıdır. Windows ' Enumfontaileleri işlevi şu anda kullanılabilir olan tüm yazı tiplerini listelemek için kullanılabilir. *LPSZFACENAME* null Ise, GDI cihazdan bağımsız bir yazı tipi kullanır.

*Kökündeki*<br/>
*NPointSize* yüksekliğini mantıksal birimlere dönüştürmek Için kullanılacak [CDC](../../mfc/reference/cdc-class.md) nesnesine yönelik işaretçi. NULL ise, dönüştürme için bir ekran cihaz bağlamı kullanılır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

*PDC*tarafından Işaret edilen CDC nesnesini kullanarak *nPointSize* 'nın yüksekliğini mantıksal birimlere otomatik olarak dönüştürür.

İşlev tarafından oluşturulan `CFont` nesneyle bitirdiğinizde, önce cihaz `CFont` bağlamından yazı tipini seçin, sonra nesneyi silin. `CreatePointFont`

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#73](../../mfc/codesnippet/cpp/cfont-class_4.cpp)]

##  <a name="createpointfontindirect"></a>CFont:: CreatePointFontIndirect

Bu işlev, öğesinin `lfHeight` `LOGFONT` üyesi cihaz birimleri yerine bir noktanın onda yorumlanması dışında [CreateFontIndirect](#createfontindirect) ile aynıdır.

```
BOOL CreatePointFontIndirect(
    const LOGFONT* lpLogFont,
    CDC* pDC = NULL);
```

### <a name="parameters"></a>Parametreler

*lpLogFont*<br/>
Mantıksal yazı tipinin özelliklerini tanımlayan bir [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) yapısına işaret eder. `LOGFONT` Yapının üyesi mantıksal birimler yerine bir noktanın `lfHeight` onda ölçülür. (Örneğin, 12 puntoluk `lfHeight` bir yazı tipi istemek için 120 olarak ayarlayın.)

*Kökündeki*<br/>
Yüksekliği`lfHeight` mantıksal birimlere dönüştürmek için kullanılacak [CDC](../../mfc/reference/cdc-class.md) nesnesine yönelik işaretçi. NULL ise, dönüştürme için bir ekran cihaz bağlamı kullanılır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, `LOGFONT` yapıyı Windows 'a geçirmeden `lfHeight` önce *PDC* tarafından işaret edilen CDC nesnesini kullanarak mantıksal birimlere, yüksekliğini otomatik olarak dönüştürür.

İşlev tarafından oluşturulan `CFont` nesneyle bitirdiğinizde, önce cihaz `CFont` bağlamından yazı tipini seçin, sonra nesneyi silin. `CreatePointFontIndirect`

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#74](../../mfc/codesnippet/cpp/cfont-class_5.cpp)]

##  <a name="fromhandle"></a>CFont:: FromHandle

Bir hfont tutamacı bir `CFont` Windows GDI yazı tipi nesnesine verildiğinde, nesnesine bir işaretçi döndürür.

```
static CFont* PASCAL FromHandle(HFONT hFont);
```

### <a name="parameters"></a>Parametreler

*hFont*<br/>
Windows yazı tipine yönelik bir HFONT tutamacı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa `CFont` nesne için bir işaretçi; Aksi takdirde null.

### <a name="remarks"></a>Açıklamalar

Bir `CFont` nesne zaten tanıtıcıya iliştirilmişse, geçici `CFont` bir nesne oluşturulur ve eklenir. Bu geçici `CFont` nesne yalnızca uygulamanın olay döngüsünde bir sonraki kez boşta kalması durumunda geçerlidir. bu süre, tüm geçici grafik nesneleri silinir. Bunun başka bir yolu, geçici nesnenin yalnızca bir pencere iletisinin işlenmesi sırasında geçerli olduğu durumdur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#75](../../mfc/codesnippet/cpp/cfont-class_6.cpp)]

##  <a name="getlogfont"></a>CFont:: GetLogFont

`LOGFONT` Yapısının bir kopyasını almak için bu işlevi çağırın. `CFont`

```
int GetLogFont(LOGFONT* pLogFont);
```

### <a name="parameters"></a>Parametreler

*pLogFont*<br/>
Yazı tipi bilgilerini almak için [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) yapısına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı, aksi durumda 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#76](../../mfc/codesnippet/cpp/cfont-class_7.cpp)]

##  <a name="operator_hfont"></a>CFont:: operator HFONT

`CFont` Nesneye eklenen yazı tipinin Windows GDI işleyicisini almak için bu işleci kullanın.

```
operator HFONT() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı `CFont` olursa Windows GDI yazı tipi nesnesinin tanıtıcısı; aksi takdirde null.

### <a name="remarks"></a>Açıklamalar

Bu işleç, ' den `CFont` [yazı tiplerine ve metne](/windows/win32/gdi/fonts-and-text)dönüşümler için otomatik olarak kullanıldığından, nesneleri hfonts bekleyen işlevlere geçirebilirsiniz `CFont` .

Grafik nesnelerini kullanma hakkında daha fazla bilgi için, Windows SDK [grafik nesneleri](/windows/win32/gdi/graphic-objects) bölümüne bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#77](../../mfc/codesnippet/cpp/cfont-class_8.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[CGdiObject Sınıfı](../../mfc/reference/cgdiobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
