---
description: 'Daha fazla bilgi edinin: CFont sınıfı'
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
ms.openlocfilehash: 4c3df138c80aeb572a4e449e7fe1065e70b5fe49
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184419"
---
# <a name="cfont-class"></a>CFont sınıfı

Windows grafik cihaz arabirimi (GDI) yazı tipini kapsüller ve yazı tipini işlemek için üye işlevleri sağlar.

## <a name="syntax"></a>Syntax

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
|[CFont:: CreateFont](#createfont)|`CFont`Belirtilen özelliklerle bir ile başlatır.|
|[CFont:: CreateFontIndirect](#createfontindirect)|Bir `CFont` yapıda verilen özelliklerle bir nesnesi başlatır `LOGFONT` .|
|[CFont:: CreatePointFont](#createpointfont)|`CFont`Belirtilen yüksekliğiyle, bir noktanın onda birinde ölçülen ve yazı biçiminin üzerine bir başlatır.|
|[CFont:: CreatePointFontIndirect](#createpointfontindirect)|`CreateFontIndirect`Yazı tipi yüksekliğinin, mantıksal birimler yerine bir noktanın onda ölçüldüğü ile aynıdır.|
|[CFont:: FromHandle](#fromhandle)|Bir `CFont` Windows HFONT verildiğinde bir nesneye bir işaretçi döndürür.|
|[CFont:: GetLogFont](#getlogfont)|`LOGFONT`Nesneye eklenen mantıksal yazı tipiyle ilgili bilgileri bir ile doldurur `CFont` .|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CFont:: operator HFONT](#operator_hfont)|Nesnesine eklenen Windows GDI yazı tipi tanıtıcısını döndürür `CFont` .|

## <a name="remarks"></a>Açıklamalar

Bir nesne kullanmak için `CFont` , bir `CFont` nesne oluşturun ve bunu [CreateFont](#createfont), [createfontınmıtfont](#createfontindirect)veya [CreatePointFontIndirect](#createpointfontindirect)ile bir Windows yazı tipi ile ekleyin ve sonra da nesnenin üye işlevlerini kullanarak yazı tipini değiştirin. [](#createpointfont)

`CreatePointFont`Ve `CreatePointFontIndirect` işlevlerinin kullanımı genellikle daha kolay olur ve `CreateFont` `CreateFontIndirect` bu yana yazı tipinin yüksekliğinin bir nokta boyutundan mantıksal birimlere otomatik olarak dönüştürülmesini sağlar.

Hakkında daha fazla bilgi için `CFont` bkz. [grafik nesneleri](../../mfc/graphic-objects.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CFont`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="cfontcfont"></a><a name="cfont"></a> CFont:: CFont

Bir `CFont` nesnesi oluşturur.

```
CFont();
```

### <a name="remarks"></a>Açıklamalar

Elde edilen nesne, kullanılmadan önce,, veya ile başlatılmalıdır `CreateFont` `CreateFontIndirect` `CreatePointFont` `CreatePointFontIndirect` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#70](../../mfc/codesnippet/cpp/cfont-class_1.cpp)]

## <a name="cfontcreatefont"></a><a name="createfont"></a> CFont:: CreateFont

`CFont`Belirtilen özelliklerle bir nesne başlatır.

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
Yazı tipinin istenen yüksekliğini (mantıksal birimler cinsinden) belirtir. `lfHeight`Bir açıklama için Windows SDK [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw)yapısının üyesine bakın. *NHeight* öğesinin mutlak değeri, dönüştürüldükten sonra 16.384 cihaz birimini aşmamalıdır. Tüm yükseklik karşılaştırmaları için, yazı tipi Eşleyici istenen boyutu aşmayan en büyük yazı tipini veya tüm fontlar istenen boyutu aşarsa en küçük yazı tipini arar.

*nWidth*<br/>
Yazı tipindeki karakterlerin ortalama genişliğini (mantıksal birimler cinsinden) belirtir. *NWidth* 0 ise, cihazın en boy oranı, fark değerinin mutlak değeri tarafından belirlenen en yakın eşleşmeyi bulmak için kullanılabilir yazı tiplerinin sayısal oranına göre eşleştirilir.

*Nessepement*<br/>
Yürüyen pement vektörü ile görüntü yüzeyinin x ekseni arasındaki açıyı (0,1 derece birimler cinsinden) belirtir. Yürüyen pement vektörü, satırdaki ilk ve son karakterlerin kaynakları arasındaki satırdır. Açı x ekseninden saatin tersi yönde ölçülür. `lfEscapement` `LOGFONT` Daha fazla bilgi için Windows SDK yapısındaki üyeye bakın.

*nOrientation*<br/>
Bir karakterin ve x ekseninin taban çizgisi arasındaki açıyı (0,1 derece birimler cinsinden) belirtir. Açı, y yönünün doğru olduğu koordinat sistemleri için x ekseninden ve y yönünün kullanıldığı koordinat sistemleri için x ekseninden saat yönünde ölçülür.

*nWeight*<br/>
Yazı tipi kalınlığını belirtir (1000 başına düşen piksellerde). Daha fazla bilgi için Windows SDK yapısındaki *lfWeight* üyesine bakın `LOGFONT` . Açıklanan değerler yaklaşık değerlerdir; Asıl görünüm, yazı tipine bağlıdır. Bazı yazı tiplerinde yalnızca FW_NORMAL, FW_REGULAR ve FW_BOLD ağırlıkları vardır. FW_DONTCARE belirtilirse, varsayılan bir ağırlık kullanılır.

*Bitic*<br/>
Yazı tipinin italik olup olmadığını belirtir.

*bUnderline*<br/>
Yazı tipinin altı çizili olup olmadığını belirtir.

*Cüstü çizili*<br/>
Yazı tipindeki karakterlerin aşağı çizili olup olmayacağını belirtir. Sıfır dışında bir değere ayarlandıysa, üstü çizili yazı tipini belirtir.

*nCharSet*<br/>
Yazı tipinin karakter seti `lfCharSet` `LOGFONT` değerini belirtir bir değer listesi için Windows SDK yapısındaki üyeyi görüntüleyin.

OEM karakter kümesi sisteme bağımlıdır.

Diğer karakter kümelerine sahip yazı tipleri sistemde bulunabilir. Bilinmeyen bir karakter kümesine sahip bir yazı tipi kullanan bir uygulama, bu yazı tipiyle işlenecek dizeleri çevirmeye veya yorumlamaya çalışmamalıdır. Bunun yerine, dizeler doğrudan çıkış cihazı sürücüsüne geçirilmelidir.

Yazı tipi Eşleyici DEFAULT_CHARSET değerini kullanmıyor. Bir uygulama bu değeri, bir yazı tipinin adının ve boyutunun mantıksal yazı tipi tam olarak tanımlanmasına olanak tanımak için kullanabilir. Belirtilen ada sahip bir yazı tipi yoksa, herhangi bir karakter kümesindeki bir yazı tipi belirtilen yazı tipi için değiştirilebilir. Beklenmedik sonuçlara engel olmak için, uygulamalar DEFAULT_CHARSET değerini gelişigüzel bir şekilde kullanmalıdır.

*nOutPrecision*<br/>
İstenen çıkış hassasiyetini belirtir. Çıkış hassasiyeti, çıktının istenen yazı tipinin yüksekliği, genişliği, karakter yönü, yürüyen soyı ve sıklık ile ne kadar yakın olduğunu tanımlar. `lfOutPrecision` `LOGFONT` Değer listesi ve daha fazla bilgi için Windows SDK yapısındaki üyeye bakın.

*nClipPrecision*<br/>
İstenen kırpma hassasiyetini belirtir. Kırpma hassasiyeti, kırpma bölgesinin kısmen dışında olan karakterlerin nasıl kırpılmasını tanımlar. `lfClipPrecision` `LOGFONT` Değerlerin listesi için Windows SDK yapısındaki üyeye bakın.

Katıştırılmış salt biçimli bir yazı tipi kullanmak için, bir uygulamanın CLIP_ENCAPSULATE belirtmesi gerekir.

Cihaz, TrueType ve vektör yazı tiplerinin tutarlı bir şekilde döndürülmesini sağlamak için, bir uygulama veya işlecini kullanarak CLIP_LH_ANGLES değerini diğer *nClipPrecision* değerlerinden herhangi biriyle birleştirebilir. CLIP_LH_ANGLES bit ayarlandıysa, tüm yazı tiplerinin dönüşü koordinat sisteminin yönünün sola veya sağ elli olmasına bağlıdır. (Koordinat sistemlerinin yönü hakkında daha fazla bilgi için, *nOrientation* parametresinin açıklamasına bakın.) CLIP_LH_ANGLES ayarlanmamışsa, cihaz yazı tipleri her zaman saatin tersi döndürülür, ancak diğer yazı tiplerinin dönüşü koordinat sisteminin yönüne bağlıdır.

*nQuality*<br/>
GDI 'nın mantıksal yazı tipi özniteliklerini gerçek fiziksel yazı tipine göre eşleştirmeye ne kadar dikkatli olduğunu tanımlayan yazı tipinin çıkış kalitesini belirtir. `lfQuality` `LOGFONT` Değerlerin listesi için Windows SDK yapısındaki üyeye bakın.

*Nstachandfamily*<br/>
Yazı tipinin perdesini ve ailesini belirtir. `lfPitchAndFamily` `LOGFONT` Değer listesi ve daha fazla bilgi için Windows SDK yapısındaki üyeye bakın.

*lpszFacename*<br/>
`CString`Yazı tipinin yazı tipi adını belirten null ile sonlandırılmış bir dize için veya işaretçisi. Bu dizenin uzunluğu en fazla 30 karakter uzunluğunda olmalıdır. Windows [Enumfontaileleri](/windows/win32/api/wingdi/nf-wingdi-enumfontfamiliesw) işlevi, şu anda kullanılabilir olan tüm yazı tiplerini listelemek için kullanılabilir. *LPSZFACENAME* null Ise, GDI cihazdan bağımsız bir yazı tipi kullanır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Yazı tipi daha sonra herhangi bir cihaz bağlamının yazı tipi olarak seçilebilir.

`CreateFont`İşlev yeni bir WINDOWS GDI yazı tipi oluşturmaz. Yalnızca GDI için kullanılabilir fiziksel yazı tiplerinin en yakın eşleşmesini seçer.

Uygulamalar, mantıksal bir yazı tipi oluştururken çoğu parametre için varsayılan ayarları kullanabilir. Her zaman belirli değerler verilmesi gereken parametreler *nHeight* ve *lpszFacename*. Eğer *nHeight* ve *lpszFacename* uygulama tarafından ayarlanmamışsa, oluşturulan mantıksal yazı tipi cihaza bağımlıdır.

`CFont`İşlev tarafından oluşturulan nesneyle bitirdiğinizde `CreateFont` , `CDC::SelectObject` cihaz bağlamında farklı bir yazı tipi seçmek için kullanın, ardından `CFont` artık gerekli olmayan nesneyi silin.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#71](../../mfc/codesnippet/cpp/cfont-class_2.cpp)]

## <a name="cfontcreatefontindirect"></a><a name="createfontindirect"></a> CFont:: CreateFontIndirect

`CFont` [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw)yapısında verilen özelliklerle bir nesnesi başlatır.

```
BOOL CreateFontIndirect(const LOGFONT* lpLogFont);
```

### <a name="parameters"></a>Parametreler

*lpLogFont*<br/>
`LOGFONT`Mantıksal yazı tipinin özelliklerini tanımlayan bir yapıya işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Yazı tipi daha sonra herhangi bir cihaz için geçerli yazı tipi olarak seçilebilir.

Bu yazı tipi, [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) yapısında belirtilen özelliklere sahiptir. Yazı tipi [CDC:: NesneSeç](../../mfc/reference/cdc-class.md#selectobject) üye işlevi kullanılarak SEÇILDIĞINDE, GDI yazı tipi Eşleyici, varolan bir fiziksel yazı tipiyle mantıksal yazı tipiyle eşleştirmeye çalışır. Yazı tipi Eşleyicisi mantıksal yazı tipi için tam bir eşleşme bulamazsa, özellikleri istenen özelliklerden çok sayıda olacak şekilde eşleşen alternatif bir yazı tipi sağlar.

`CFont`İşlev tarafından oluşturulan nesneye artık ihtiyacınız kalmadığında `CreateFontIndirect` , `CDC::SelectObject` cihaz bağlamında farklı bir yazı tipi seçmek için kullanın, ardından `CFont` artık gerekli olmayan nesneyi silin.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#72](../../mfc/codesnippet/cpp/cfont-class_3.cpp)]

## <a name="cfontcreatepointfont"></a><a name="createpointfont"></a> CFont:: CreatePointFont

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
`CString`Yazı tipinin yazı tipi adını belirten null ile sonlandırılmış bir dize için veya işaretçisi. Bu dizenin uzunluğu en fazla 30 karakter uzunluğunda olmalıdır. Windows ' Enumfontaileleri işlevi şu anda kullanılabilir olan tüm yazı tiplerini listelemek için kullanılabilir. *LPSZFACENAME* null Ise, GDI cihazdan bağımsız bir yazı tipi kullanır.

*Kökündeki*<br/>
*NPointSize* yüksekliğini mantıksal birimlere dönüştürmek Için kullanılacak [CDC](../../mfc/reference/cdc-class.md) nesnesine yönelik işaretçi. NULL ise, dönüştürme için bir ekran cihaz bağlamı kullanılır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

*PDC* tarafından Işaret edilen CDC nesnesini kullanarak *nPointSize* 'nın yüksekliğini mantıksal birimlere otomatik olarak dönüştürür.

`CFont`İşlev tarafından oluşturulan nesneyle bitirdiğinizde `CreatePointFont` , önce cihaz bağlamından yazı tipini seçin, sonra `CFont` nesneyi silin.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#73](../../mfc/codesnippet/cpp/cfont-class_4.cpp)]

## <a name="cfontcreatepointfontindirect"></a><a name="createpointfontindirect"></a> CFont:: CreatePointFontIndirect

Bu işlev, [](#createfontindirect) `lfHeight` öğesinin üyesi `LOGFONT` cihaz birimleri yerine bir noktanın onda yorumlanması dışında CreateFontIndirect ile aynıdır.

```
BOOL CreatePointFontIndirect(
    const LOGFONT* lpLogFont,
    CDC* pDC = NULL);
```

### <a name="parameters"></a>Parametreler

*lpLogFont*<br/>
Mantıksal yazı tipinin özelliklerini tanımlayan bir [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) yapısına işaret eder. `lfHeight` `LOGFONT` Yapının üyesi mantıksal birimler yerine bir noktanın onda ölçülür. (Örneğin, `lfHeight` 12 puntoluk bir yazı tipi istemek için 120 olarak ayarlayın.)

*Kökündeki*<br/>
Yüksekliği mantıksal birimlere dönüştürmek için kullanılacak [CDC](../../mfc/reference/cdc-class.md) nesnesine yönelik işaretçi `lfHeight` . NULL ise, dönüştürme için bir ekran cihaz bağlamı kullanılır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, `lfHeight` yapıyı Windows 'a geçirmeden önce *PDC* tarafından işaret edilen CDC nesnesini kullanarak mantıksal birimlere, yüksekliğini otomatik olarak dönüştürür `LOGFONT` .

`CFont`İşlev tarafından oluşturulan nesneyle bitirdiğinizde `CreatePointFontIndirect` , önce cihaz bağlamından yazı tipini seçin, sonra `CFont` nesneyi silin.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#74](../../mfc/codesnippet/cpp/cfont-class_5.cpp)]

## <a name="cfontfromhandle"></a><a name="fromhandle"></a> CFont:: FromHandle

Bir `CFont` HFONT tutamacı bir WINDOWS GDI yazı tipi nesnesine verildiğinde, nesnesine bir işaretçi döndürür.

```
static CFont* PASCAL FromHandle(HFONT hFont);
```

### <a name="parameters"></a>Parametreler

*hFont*<br/>
Windows yazı tipine yönelik bir HFONT tutamacı.

### <a name="return-value"></a>Dönüş Değeri

`CFont`Başarılı olursa nesne için bir işaretçi; aksi takdırde null.

### <a name="remarks"></a>Açıklamalar

Bir `CFont` nesne zaten tanıtıcıya iliştirilmişse, geçici bir `CFont` nesne oluşturulur ve eklenir. Bu geçici `CFont` nesne yalnızca uygulamanın olay döngüsünde bir sonraki kez boşta kalması durumunda geçerlidir. bu süre, tüm geçici grafik nesneleri silinir. Bunun başka bir yolu, geçici nesnenin yalnızca bir pencere iletisinin işlenmesi sırasında geçerli olduğu durumdur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#75](../../mfc/codesnippet/cpp/cfont-class_6.cpp)]

## <a name="cfontgetlogfont"></a><a name="getlogfont"></a> CFont:: GetLogFont

Yapısının bir kopyasını almak için bu işlevi çağırın `LOGFONT` `CFont` .

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

## <a name="cfontoperator-hfont"></a><a name="operator_hfont"></a> CFont:: operator HFONT

Nesneye eklenen yazı tipinin Windows GDI işleyicisini almak için bu işleci kullanın `CFont` .

```
operator HFONT() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa Windows GDI yazı tipi nesnesinin tanıtıcısı `CFont` ; aksi takdırde null.

### <a name="remarks"></a>Açıklamalar

Bu işleç `CFont` , ' den [yazı tiplerine ve metne](/windows/win32/gdi/fonts-and-text)dönüşümler için otomatik olarak kullanıldığından, `CFont` nesneleri hfonts bekleyen işlevlere geçirebilirsiniz.

Grafik nesnelerini kullanma hakkında daha fazla bilgi için, Windows SDK [grafik nesneleri](/windows/win32/gdi/graphic-objects) bölümüne bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#77](../../mfc/codesnippet/cpp/cfont-class_8.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[CGdiObject sınıfı](../../mfc/reference/cgdiobject-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)
