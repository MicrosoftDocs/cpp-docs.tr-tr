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
ms.openlocfilehash: 04136b3550675f0e50f905047fee551e27da7069
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58768114"
---
# <a name="cfont-class"></a>CFont sınıfı

Bir Windows grafik cihaz arabirimi (GDI) yazı tipi kapsüller ve yazı tipini yönlendirmek için işlevleri sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CFont : public CGdiObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CFont::CFont](#cfont)|Oluşturur bir `CFont` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CFont::CreateFont](#createfont)|Başlatan bir `CFont` belirtilen özelliklere sahip.|
|[CFont::CreateFontIndirect](#createfontindirect)|Başlatan bir `CFont` nesne verilen özelliklere sahip bir `LOGFONT` yapısı.|
|[CFont::CreatePointFont](#createpointfont)|Başlatan bir `CFont` belirtilen yüksekliği ile bir nokta ve yazı tipi onda içinde ölçülür.|
|[CFont::CreatePointFontIndirect](#createpointfontindirect)|Aynı `CreateFontIndirect` dışında yazı tipi onda mantıksal birimler yerine bir noktası ölçülür.|
|[CFont::FromHandle](#fromhandle)|Bir işaretçi döndüren bir `CFont` Windows HFONT verildiğinde nesne.|
|[CFont::GetLogFont](#getlogfont)|Dolduran bir `LOGFONT` bağlı mantıksal yazı tipi ilgili bilgilerle `CFont` nesne.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[HFONT CFont::operator](#operator_hfont)|Windows GDI yazı tipi tanıtıcı iliştirilmiş döndürür `CFont` nesne.|

## <a name="remarks"></a>Açıklamalar

Kullanılacak bir `CFont` nesne, oluşturun bir `CFont` nesne ve birlikte bir Windows yazı tipi ekleme [CreateFont](#createfont), [CreateFontIndirect](#createfontindirect), [CreatePointFont](#createpointfont), veya [CreatePointFontIndirect](#createpointfontindirect)ve sonra da yazı tipini değiştirmek için nesnenin üye işlevleri kullanın.

`CreatePointFont` Ve `CreatePointFontIndirect` işlevleri daha kolay genellikle `CreateFont` veya `CreateFontIndirect` dönüştürme yüksekliği için yazı tipinin noktası boyutundan mantıksal birimler otomatik olarak bunu olduğundan.

Daha fazla bilgi için `CFont`, bkz: [grafik nesneleri](../../mfc/graphic-objects.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CFont`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

##  <a name="cfont"></a>  CFont::CFont

Oluşturur bir `CFont` nesne.

```
CFont();
```

### <a name="remarks"></a>Açıklamalar

Elde edilen nesnenin ile başlatılmalıdır `CreateFont`, `CreateFontIndirect`, `CreatePointFont`, veya `CreatePointFontIndirect` kullanılmadan önce.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#70](../../mfc/codesnippet/cpp/cfont-class_1.cpp)]

##  <a name="createfont"></a>  CFont::CreateFont

Başlatan bir `CFont` belirtilen özelliklere sahip nesne.

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
İstenen yüksekliğini (mantıksal birimler cinsinden) yazı tipini belirtir. Bkz: `lfHeight` üyesi [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta)yapısı içinde bir açıklaması için Windows SDK'sı. Mutlak değerini *nHeight* dönüştürmeden sonra 16.384 cihaz birimleri aşmamalıdır. Tüm yazı tiplerini istenen boyuta aşarsanız tüm yükseklik karşılaştırmalar için istenen boyut aşmayan en büyük yazı tipi veya en küçük yazı tipi için yazı tipi Eşleyici arar.

*nWidth*<br/>
Ortalama genişliğini (mantıksal birimler cinsinden) karakter yazı tipini belirtir. Varsa *nWidth* 0 ise, cihazın en boy oranını fark mutlak değeri tarafından belirlenir en yakın eşleşme bulmak için yazı tiplerini digitization en boy oranını karşı eşleştirilir.

*nEscapement*<br/>
X ekseninin uzaklaştırabilir escapement vektör arasındaki açıyı (0,1 derece cinsinden) belirtir. Bir çizgi üzerinden ilk ve son karakter bir satırda kaynakları escapement vektördür. Açı saat yönünün tersine x ekseninden ölçülür. Bkz: `lfEscapement` üye `LOGFONT` daha fazla bilgi için Windows SDK'sındaki yapısı.

*nOrientation*<br/>
X ekseni ile temel bir karakterin arasındaki açıyı (0,1 derece cinsinden) belirtir. Açı, saat yönünün tersine x ekseni için y yönünde aşağı ve y yönünde çalışır durumda koordinat sistemi için x ekseni saat yönünde Döndürülmüş koordinat sistemi arasında ölçülür.

*nWeight*<br/>
Yazı tipi genişliği (kaynağa piksel cinsinden başına 1000) belirtir. Bkz: *lfWeight* üye `LOGFONT` daha fazla bilgi için Windows SDK'sındaki yapısı. Açıklanan yaklaşık değerlerdir; Gerçek görünümü üzerinde yazı bağlıdır. Bazı yazı tipleri yalnızca FW_NORMAL FW_REGULAR ve FW_BOLD ağırlıklara sahip. FW_DONTCARE belirtilmezse, varsayılan ağırlık kullanılır.

*bItalic*<br/>
İtalik yazı tipi olup olmadığını belirtir.

*bUnderline*<br/>
Yazı tipi altı çizili olup olmadığını belirtir.

*cStrikeOut*<br/>
Yazıtipindeki karakterlerin kaldırılmış olup olmadığını belirtir. Üstü çizili yazı tipini belirtir sıfır olmayan bir değere ayarlayın.

*nCharSet*<br/>
Yazı tipinin karakter setSee belirtir `lfCharSet` üye `LOGFONT` değerlerin listesi için Windows SDK'sındaki yapısı.

Sistem bağımlı OEM karakter kümesidir.

Yazı tipleri diğer karakter kümesi ile sistemde mevcut. Bir yazı tipi ile bir bilinmeyen karakter kümesi kullanan bir uygulama veya bu yazı tipiyle işlenecek dizelerini yorumlar çevirme kullanmamanız gerekir. Bunun yerine, doğrudan çıkış aygıt sürücüsü dizeleri geçirilmelidir.

Yazı tipi Eşleyici DEFAULT_CHARSET değeri kullanmaz. Bir uygulama adı ve tam olarak mantıksal yazı tipini açıklayan bir yazı tipi boyutunu izin vermek için bu değeri kullanabilirsiniz. Belirtilen ada sahip bir yazıtipi yoksa, herhangi bir karakter kümesi listesinden bir yazı tipi için belirtilen yazı tipi yerine kullanılabileceği. Beklenmeyen sonuçlardan kaçınmak için uygulamaları DEFAULT_CHARSET değeri tutumlu kullanmanız gerekir.

*nOutPrecision*<br/>
İstenen çıkış duyarlık belirtir. Çıkış duyarlılık çıktısını istenen yazı tipinin yükseklik, genişlik, karakter yönü, escapement ve aralık ne kadar yakın eşleşmelidir tanımlar. Bkz: `lfOutPrecision` üye `LOGFONT` yapısı içinde bir liste değerleri ve daha fazla bilgi için Windows SDK'sı.

*nClipPrecision*<br/>
İstenen kırpma duyarlık belirtir. Kırpma duyarlık kısmen kırpma bölgesinin dışındaki karakterler küçük nasıl yapılacağını tanımlar. Bkz: `lfClipPrecision` üye `LOGFONT` değerlerin listesi için Windows SDK'sındaki yapısı.

Gömülü bir salt okunur font kullanmak için bir uygulama CLIP_ENCAPSULATE belirtmeniz gerekir.

Cihaz, TrueType ve vektör yazı tipleri tutarlı döndürme elde etmek için bir uygulama veya işlecini CLIP_LH_ANGLES değeri herhangi diğer birleştirmek için kullanabilirsiniz *nClipPrecision* değerleri. Tüm yazı tipleri için döndürme CLIP_LH_ANGLES biti ayarlanmışsa, koordinat sistemi yönlendirmesini sol olmasına göre değişir ya da sağ. (Açıklama koordinat sistemi yönlendirmesini hakkında daha fazla bilgi için bkz *nOrientation* parametre.) CLIP_LH_ANGLES ayarlı değil, her zaman cihaz yazı tipleri saat yönünün tersine döndür, ancak diğer yazı tipleri döndürmesini koordinat sistemini yönünü üzerinde bağlıdır.

*nQuality*<br/>
GDI gerçek bir fiziksel yazı tipini, yazı tipi mantıksal öznitelikleri eşleşecek şekilde nasıl dikkatli bir şekilde denemelidir tanımlar yazıtipinin çıkış kalitesi belirtir. Bkz: `lfQuality` üye `LOGFONT` değerlerin listesi için Windows SDK'sındaki yapısı.

*nPitchAndFamily*<br/>
Yazı tipi ailesi ve sıklıktaki değişimi belirtir. Bkz: `lfPitchAndFamily` üye `LOGFONT` yapısı içinde bir liste değerleri ve daha fazla bilgi için Windows SDK'sı.

*lpszFacename*<br/>
A `CString` ya da yazı tipini, yazı tipi adını belirten bir null ile sonlandırılmış dizeye yönelik işaretçi. Bu dizenin uzunluğu 30 karakterden uzun olmamalıdır. Windows [EnumFontFamilies](/windows/desktop/api/wingdi/nf-wingdi-enumfontfamiliesa) işlevi, şu anda kullanılabilen tüm yazı tiplerini numaralandırma için kullanılabilir. Varsa *lpszFacename* NULL ise bir CİHAZDAN bağımsız yazı tipi GDI kullanır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Yazı tipini, yazı tipi için herhangi bir cihaz bağlamı olarak sonradan seçilebilir.

`CreateFont` İşlevi yeni bir Windows GDI yazı tipi oluşturmaz. Yalnızca en yakın eşleşme için GDI fiziksel yazı tiplerinin seçilir.

Uygulamaları mantıksal bir yazı tipi oluştururken çoğu parametreler için varsayılan ayarları kullanabilir. Her zaman belirli bir değer verilmelidir parametreler *nHeight* ve *lpszFacename*. Varsa *nHeight* ve *lpszFacename* ayarlı değil uygulama tarafından oluşturulan mantıksal yazı cihaz bağlıdır.

Bitirdiğinizde ile `CFont` tarafından oluşturulan nesne `CreateFont` işlev, kullanın `CDC::SelectObject` farklı bir yazı tipi cihaz bağlamına seçmek için delete `CFont` artık gerekli nesne.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#71](../../mfc/codesnippet/cpp/cfont-class_2.cpp)]

##  <a name="createfontindirect"></a>  CFont::CreateFontIndirect

Başlatan bir `CFont` nesne verilen özelliklere sahip bir [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta)yapısı.

```
BOOL CreateFontIndirect(const LOGFONT* lpLogFont);
```

### <a name="parameters"></a>Parametreler

*lpLogFont*<br/>
İşaret eden bir `LOGFONT` mantıksal yazı tipi özelliklerini tanımlayan yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Yazı tipi, daha sonra herhangi bir cihaz için geçerli yazı tipi olarak seçilebilir.

Bu yazı tipini belirtilen özelliklere sahip [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) yapısı. Yazı tipi seçildiğinde kullanarak [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) üye işlevi, GDI yazı tipi Eşleyici mantıksal yazı mevcut fiziksel yazı tipi ile eşleşecek şekilde çalışır. Mantıksal yazı tipi için tam bir eşleşme bulmak yazı tipi Eşleyici başarısız olursa, istenen özellikleri olabildiğince fazla sayıda özelliklerini eşleşen bir alternatif yazı tipi sağlar.

Artık gerektiğinde `CFont` tarafından oluşturulan nesne `CreateFontIndirect` işlev, kullanın `CDC::SelectObject` farklı bir yazı tipi cihaz bağlamına seçmek için delete `CFont` artık gerekli nesne.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#72](../../mfc/codesnippet/cpp/cfont-class_3.cpp)]

##  <a name="createpointfont"></a>  CFont::CreatePointFont

Bu işlev, belirtilen bir yazı tipi bir yazı tipi oluşturabilir ve nokta boyutu için basit bir yol sağlar.

```
BOOL CreatePointFont(
    int nPointSize,
    LPCTSTR lpszFaceName,
    CDC* pDC = NULL);
```

### <a name="parameters"></a>Parametreler

*nPointSize*<br/>
Yazı tipi yüksekliği noktası onda istedi. (Örneğin, bir 12 punto yazı tipi istemek için 120 geçirin.)

*lpszFaceName*<br/>
A `CString` ya da yazı tipini, yazı tipi adını belirten bir null ile sonlandırılmış dizeye yönelik işaretçi. Bu dizenin uzunluğu 30 karakterden uzun olmamalıdır. Windows ' EnumFontFamilies işlevi, şu anda kullanılabilen tüm yazı tiplerini numaralandırma için kullanılabilir. Varsa *lpszFaceName* NULL ise bir CİHAZDAN bağımsız yazı tipi GDI kullanır.

*pDC*<br/>
İşaretçi [CDC](../../mfc/reference/cdc-class.md) yüksekliğini dönüştürmek için kullanılacak nesne *nPointSize* mantıksal birimleri. NULL ise, bir ekran cihaz bağlamı dönüştürme için kullanılır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Yükseklik otomatik olarak dönüştürür *nPointSize* mantıksal birimler için bu CDC nesnesini kullanarak işaret ettiği *pDC*.

Bitirdiğinizde ile `CFont` tarafından oluşturulan nesne `CreatePointFont` işlev, ilk cihaz bağlamı dışında yazı tipini seçin ve ardından silme `CFont` nesne.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#73](../../mfc/codesnippet/cpp/cfont-class_4.cpp)]

##  <a name="createpointfontindirect"></a>  CFont::CreatePointFontIndirect

Bu işlev aynı şekilde, [CreateFontIndirect](#createfontindirect) dışında `lfHeight` üyesi `LOGFONT` onda cihaz yerine noktası birimi yorumlanır.

```
BOOL CreatePointFontIndirect(
    const LOGFONT* lpLogFont,
    CDC* pDC = NULL);
```

### <a name="parameters"></a>Parametreler

*lpLogFont*<br/>
İşaret eden bir [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) mantıksal yazı tipi özelliklerini tanımlayan yapısı. `lfHeight` Üyesi `LOGFONT` yapısı içinde bir nokta yerine mantıksal birimler onda ölçülür. (Örneğin, ayarlayın `lfHeight` 120'den 12 punto yazı tipi istemek için.)

*pDC*<br/>
İşaretçi [CDC](../../mfc/reference/cdc-class.md) yüksekliğini dönüştürmek için kullanılacak nesne `lfHeight` mantıksal birimleri. NULL ise, bir ekran cihaz bağlamı dönüştürme için kullanılır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev yüksekliğini otomatik olarak dönüştürür `lfHeight` mantıksal birimler için bu CDC nesnesini kullanarak işaret ettiği *pDC* geçirilmeden önce `LOGFONT` yapısı Windows açın.

Bitirdiğinizde ile `CFont` tarafından oluşturulan nesne `CreatePointFontIndirect` işlev, ilk cihaz bağlamı dışında yazı tipini seçin ve ardından silme `CFont` nesne.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#74](../../mfc/codesnippet/cpp/cfont-class_5.cpp)]

##  <a name="fromhandle"></a>  CFont::FromHandle

Bir işaretçi döndüren bir `CFont` HFONT tanıtıcı bir Windows GDI yazı nesnesine verildiğinde nesne.

```
static CFont* PASCAL FromHandle(HFONT hFont);
```

### <a name="parameters"></a>Parametreler

*hFont*<br/>
HFONT tanıtıcı bir Windows yazı.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir `CFont` nesne başarılı; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Varsa bir `CFont` nesne zaten iliştirilmemiş tanıtıcı, geçici bir `CFont` nesnesi oluşturulur ve bağlı. Bu geçici `CFont` tüm geçici grafik, zaman sonraki açışınızda uygulama boşta kalma süresi kendi olay döngüsü olana kadar nesneler silinir yalnızca nesne geçerlidir. Bunu belirten bir başka yolu geçici bir nesne yalnızca bir pencere iletisi işlenirken geçerli olmasıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#75](../../mfc/codesnippet/cpp/cfont-class_6.cpp)]

##  <a name="getlogfont"></a>  CFont::GetLogFont

Bir kopyasını almak için bu işlevi çağırın `LOGFONT` için yapı `CFont`.

```
int GetLogFont(LOGFONT* pLogFont);
```

### <a name="parameters"></a>Parametreler

*pLogFont*<br/>
İşaretçi [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) yapısı yazı tipi bilgileri almak için.

### <a name="return-value"></a>Dönüş Değeri

Aksi durumda 0 işlev başarılı olursa sıfır dışı.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#76](../../mfc/codesnippet/cpp/cfont-class_7.cpp)]

##  <a name="operator_hfont"></a>  HFONT CFont::operator

Bağlı yazı tipi Windows GDI tanıtıcısını almak için bu işleci kullanın `CFont` nesne.

```
operator HFONT() const;
```

### <a name="return-value"></a>Dönüş Değeri

Windows GDI yazı tipi nesne tanıtıcısını bağlı `CFont` başarılı; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Bu işleç dönüştürmelerinde otomatik olarak kullanıldığından `CFont` için [yazı tipleri ve metin](/windows/desktop/gdi/fonts-and-text), geçirebilirsiniz `CFont` HFONTs beklediğiniz işlev nesneleri.

Grafik nesneler kullanma hakkında daha fazla bilgi için bkz. [grafik nesneleri](/windows/desktop/gdi/graphic-objects) Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#77](../../mfc/codesnippet/cpp/cfont-class_8.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[CGdiObject Sınıfı](../../mfc/reference/cgdiobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
