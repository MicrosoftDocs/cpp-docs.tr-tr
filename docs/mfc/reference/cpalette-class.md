---
title: CPalette Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CPalette
- AFXWIN/CPalette
- AFXWIN/CPalette::CPalette
- AFXWIN/CPalette::AnimatePalette
- AFXWIN/CPalette::CreateHalftonePalette
- AFXWIN/CPalette::CreatePalette
- AFXWIN/CPalette::FromHandle
- AFXWIN/CPalette::GetEntryCount
- AFXWIN/CPalette::GetNearestPaletteIndex
- AFXWIN/CPalette::GetPaletteEntries
- AFXWIN/CPalette::ResizePalette
- AFXWIN/CPalette::SetPaletteEntries
helpviewer_keywords:
- CPalette [MFC], CPalette
- CPalette [MFC], AnimatePalette
- CPalette [MFC], CreateHalftonePalette
- CPalette [MFC], CreatePalette
- CPalette [MFC], FromHandle
- CPalette [MFC], GetEntryCount
- CPalette [MFC], GetNearestPaletteIndex
- CPalette [MFC], GetPaletteEntries
- CPalette [MFC], ResizePalette
- CPalette [MFC], SetPaletteEntries
ms.assetid: 8cd95498-53ed-4852-85e1-70e522541114
ms.openlocfilehash: f5740b3b073c4f564f9cac0fa04e5687ce1d8f00
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753680"
---
# <a name="cpalette-class"></a>CPalette Sınıfı

Bir Windows renk paletini kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CPalette : public CGdiObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CPalette::CPalette](#cpalette)|Ekli Windows `CPalette` paleti olmayan bir nesne oluşturuyor. Kullanılmadan önce `CPalette` nesneyi başlatma üye işlevlerinden biriyle başlatmanız gerekir.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CPalette::AnimatePalette](#animatepalette)|`CPalette` Nesne tarafından tanımlanan mantıksal paletteki girişleri değiştirir. Windows, sistem paletine yeni girişleri hemen eşlediği için uygulamanın istemci alanını güncelleştirmesi gerekmez.|
|[CPalette::CreateHalftonePalette](#createhalftonepalette)|Aygıt bağlamı için bir yarı ton paleti oluşturur `CPalette` ve nesneye bağlar.|
|[CPalette::CreatePalette](#createpalette)|Bir Windows renk paleti oluşturur ve `CPalette` nesneye bağlar.|
|[CPalette::FromHandle](#fromhandle)|Bir Windows palet `CPalette` nesnesine tutamacı verildiğinde bir işaretçiyi nesneye döndürür.|
|[CPalette::GetEntryCount](#getentrycount)|Mantıksal bir paletteki palet girişlerinin sayısını alır.|
|[CPalette::GetNearestPaletteIndex](#getnearestpaletteindex)|Bir renk değeriyle en yakından eşleşen mantıksal paletteki giriş dizini döndürür.|
|[CPalette::GetPaletteEntries](#getpaletteentries)|Mantıksal bir paletteki çeşitli palet girdilerini alır.|
|[CPalette::Yeniden BoyutlandırmaPalette](#resizepalette)|`CPalette` Nesne tarafından belirtilen mantıksal paletin boyutunu belirtilen giriş sayısıyla değiştirir.|
|[CPalette::SetPaletteEntries](#setpaletteentries)|RGB renk değerlerini ve bayraklarını mantıksal bir paletteki çeşitli girişlerde ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CPalette::operatör HPALETTE](#operator_hpalette)|Bağlı Olan HPALETTE'yi `CPalette`döndürür.|

## <a name="remarks"></a>Açıklamalar

Palet, uygulama ve renk çıktıaygıtı (görüntü aygıtı gibi) arasında bir arabirim sağlar. Arabirim, uygulamanın diğer uygulamalar tarafından görüntülenen renklere ciddi şekilde müdahale etmeden çıktı aygıtının renk özelliklerinden tam olarak yararlanmasını sağlar. Windows, kullanılan renkleri belirlemek için uygulamanın mantıksal paletini (gerekli renklerin listesi) ve sistem paletini (kullanılabilir renkleri tanımlayan) kullanır.

Nesne, `CPalette` nesne tarafından başvurulan paletin manipüle etmek için üye işlevler sağlar. Bir `CPalette` nesne oluşturun ve gerçek palet, bir grafik aygıtı arabirimi (GDI) nesnesi oluşturmak ve girişlerini ve diğer özelliklerini işlemek için üye işlevlerini kullanın.

Kullanma `CPalette`hakkında daha fazla bilgi için [Bkz. Grafik Nesneler.](../../mfc/graphic-objects.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Cgdiobject](../../mfc/reference/cgdiobject-class.md)

`CPalette`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="cpaletteanimatepalette"></a><a name="animatepalette"></a>CPalette::AnimatePalette

`CPalette` Nesneye iliştirilen mantıksal paletteki girişleri değiştirir.

```cpp
void AnimatePalette(
    UINT nStartIndex,
    UINT nNumEntries,
    LPPALETTEENTRY lpPaletteColors);
```

### <a name="parameters"></a>Parametreler

*nBaşlangıç Endeksi*<br/>
Paletteki ilk girişin animasyonlu olmasını belirtir.

*nümgirişleri*<br/>
Animasyonlanacak paletteki giriş sayısını belirtir.

*lpPaletteColors*<br/>
*nStartIndex* ve *nNumEntries*tarafından tanımlanan palet girişlerini değiştirmek için [PALETTEENTRY](/previous-versions/dd162769\(v=vs.85\)) yapıları dizisinin ilk üyesini işaret edin.

### <a name="remarks"></a>Açıklamalar

Bir uygulama `AnimatePalette`aradığında, istemci alanını güncelleştirmesi gerekmez, çünkü Windows yeni girişleri sistem paletine hemen eşler.

İşlev `AnimatePalette` yalnızca `palPaletteEntry` `CPalette` nesneye bağlı [LOGPALETTE](/windows/win32/api/wingdi/ns-wingdi-logpalette) yapısının ilgili üyesinde ayarlanan PC_RESERVED bayrağıyla girişleri değiştirir. Bu yapı hakkında daha fazla bilgi için Windows SDK'daki LOGPALETTE'ye bakın.

## <a name="cpalettecpalette"></a><a name="cpalette"></a>CPalette::CPalette

Bir `CPalette` nesne inşa eder.

```
CPalette();
```

### <a name="remarks"></a>Açıklamalar

Birini takmak için arayana `CreatePalette` kadar nesnenin bağlı paleti yoktur.

## <a name="cpalettecreatehalftonepalette"></a><a name="createhalftonepalette"></a>CPalette::CreateHalftonePalette

Aygıt bağlamı için yarı ton paleti oluşturur.

```
BOOL CreateHalftonePalette(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
Aygıt bağlamını tanımlar.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bir aygıt bağlamının germe modu HALFTONE olarak ayarlandığında bir uygulama yarım ton bir palet oluşturmalıdır. [CreateHalftonePalette](/windows/win32/api/wingdi/nf-wingdi-createhalftonepalette) üye işlevi tarafından döndürülen mantıksal yarı ton paleti [cdc::StretchBlt](../../mfc/reference/cdc-class.md#stretchblt) veya [StretchDIBits](/windows/win32/api/wingdi/nf-wingdi-stretchdibits) işlevi çağrılmadan önce seçilip aygıt bağlamına gerçekleştirilmelidir.

Hakkında `CreateHalftonePalette` daha fazla bilgi için `StretchDIBits`Windows SDK'ya bakın ve .

## <a name="cpalettecreatepalette"></a><a name="createpalette"></a>CPalette::CreatePalette

Windows mantıksal `CPalette` renk paleti oluşturup `CPalette` nesneye takarak nesneyi başolarak başolarak karşılar.

```
BOOL CreatePalette(LPLOGPALETTE lpLogPalette);
```

### <a name="parameters"></a>Parametreler

*lpLogPalette*<br/>
Mantıksal paletteki renkler hakkında bilgi içeren bir [LOGPALETT](/windows/win32/api/wingdi/ns-wingdi-logpalette) yapısına işaret edin.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Yapı hakkında daha fazla bilgi `LOGPALETTE` için Windows SDK'ya bakın.

## <a name="cpalettefromhandle"></a><a name="fromhandle"></a>CPalette::FromHandle

Bir Windows palet `CPalette` nesnesine tutamacı verildiğinde bir işaretçiyi nesneye döndürür.

```
static CPalette* PASCAL FromHandle(HPALETTE hPalette);
```

### <a name="parameters"></a>Parametreler

*hPalette*<br/>
Windows GDI renk paletinin tutamacı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa `CPalette` nesneye işaretçi; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Windows `CPalette` paletine zaten bir nesne eklenmemişse, geçici `CPalette` bir nesne oluşturulur ve eklenir. Bu `CPalette` geçici nesne yalnızca, uygulamanın olay döngüsünde boşta kalma süresine sahip olduğu ve tüm geçici grafik nesnelerinin silindiği bir sonraki zamana kadar geçerlidir. Başka bir deyişle, geçici nesne yalnızca bir pencere iletisinin işlenmesi sırasında geçerlidir.

## <a name="cpalettegetentrycount"></a><a name="getentrycount"></a>CPalette::GetEntryCount

Belirli bir mantıksal paletteki giriş sayısını almak için bu üye işlevi arayın.

```
int GetEntryCount();
```

### <a name="return-value"></a>Dönüş Değeri

Mantıksal bir paletteki giriş sayısı.

## <a name="cpalettegetnearestpaletteindex"></a><a name="getnearestpaletteindex"></a>CPalette::GetNearestPaletteIndex

Belirtilen renk değeriyle en yakından eşleşen mantıksal paletteki giriş dizini verir.

```
UINT GetNearestPaletteIndex(COLORREF crColor) const;
```

### <a name="parameters"></a>Parametreler

*crColor*<br/>
Eşleşecek rengi belirtir.

### <a name="return-value"></a>Dönüş Değeri

Mantıksal bir paletteki girişin dizini. Giriş, belirtilen renge en çok eşleşen rengi içerir.

## <a name="cpalettegetpaletteentries"></a><a name="getpaletteentries"></a>CPalette::GetPaletteEntries

Mantıksal bir paletteki çeşitli palet girdilerini alır.

```
UINT GetPaletteEntries(
    UINT nStartIndex,
    UINT nNumEntries,
    LPPALETTEENTRY lpPaletteColors) const;
```

### <a name="parameters"></a>Parametreler

*nBaşlangıç Endeksi*<br/>
Alınacak mantıksal paletteki ilk girişi belirtir.

*nümgirişleri*<br/>
Alınacak mantıksal paletteki giriş sayısını belirtir.

*lpPaletteColors*<br/>
Palet girişlerini almak için [paletteentry](/previous-versions/dd162769\(v=vs.85\)) veri yapıları bir dizi işaret. Dizi, *nNumEntries*tarafından belirtildiği gibi en az sayıda veri yapıları içermelidir.

### <a name="return-value"></a>Dönüş Değeri

Mantıksal paletten alınan giriş sayısı; Fonksiyon başarısız olduysa 0.

## <a name="cpaletteoperator-hpalette"></a><a name="operator_hpalette"></a>CPalette::operatör HPALETTE

`CPalette` Nesnenin ekli Windows GDI tutamacını almak için bu işleci kullanın.

```
operator HPALETTE() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, nesne tarafından temsil edilen Windows `CPalette` GDI nesnesine bir tanıtıcı; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Bu işleç, bir HPALETTE nesnesinin doğrudan kullanımını destekleyen bir döküm operatörüdür.

Grafik nesneleri kullanma hakkında daha fazla bilgi için Windows SDK'daki [Grafik Nesneler](/windows/win32/gdi/graphic-objects) makalesine bakın.

## <a name="cpaletteresizepalette"></a><a name="resizepalette"></a>CPalette::Yeniden BoyutlandırmaPalette

`CPalette` Nesneye iliştirilen mantıksal paletin boyutunu *nNumEntries*tarafından belirtilen giriş sayısıyla değiştirir.

```
BOOL ResizePalette(UINT nNumEntries);
```

### <a name="parameters"></a>Parametreler

*nümgirişleri*<br/>
Yeniden boyutlandırıldıktan sonra paletteki giriş sayısını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Palet başarıyla yeniden boyutlandırılırsa sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir uygulama `ResizePalette` paletboyutunu küçültmek için çağırırsa, yeniden boyutlandırılmış palette kalan girişler değişmez. Uygulama paleti `ResizePalette` büyütmek için çağrıda bulunuyorsa, ek palet girişleri siyaha ayarlanır (kırmızı, yeşil ve mavi değerlerin tümü 0'dır) ve tüm ek girişlerin bayrakları 0 olarak ayarlanır.

Windows API `ResizePalette`hakkında daha fazla bilgi için Windows SDK'daki [ResizePalette'e](/windows/win32/api/wingdi/nf-wingdi-resizepalette) bakın.

## <a name="cpalettesetpaletteentries"></a><a name="setpaletteentries"></a>CPalette::SetPaletteEntries

RGB renk değerlerini ve bayraklarını mantıksal bir paletteki çeşitli girişlerde ayarlar.

```
UINT SetPaletteEntries(
    UINT nStartIndex,
    UINT nNumEntries,
    LPPALETTEENTRY lpPaletteColors);
```

### <a name="parameters"></a>Parametreler

*nBaşlangıç Endeksi*<br/>
Ayarlanacak mantıksal paletteki ilk girişi belirtir.

*nümgirişleri*<br/>
Ayarlanacak mantıksal paletteki giriş sayısını belirtir.

*lpPaletteColors*<br/>
Palet girişlerini almak için [paletteentry](/previous-versions/dd162769\(v=vs.85\)) veri yapıları bir dizi işaret. Dizi, *nNumEntries*tarafından belirtildiği gibi en az sayıda veri yapıları içermelidir.

### <a name="return-value"></a>Dönüş Değeri

Mantıksal palette ayarlanan giriş sayısı; Fonksiyon başarısız olduysa 0.

### <a name="remarks"></a>Açıklamalar

Uygulama aradığında `SetPaletteEntries`mantıksal palet bir aygıt bağlamına seçilirse, uygulama CDC çağırana kadar değişiklikler etkili [olmaz::RealizePalette](../../mfc/reference/cdc-class.md#realizepalette).

Daha fazla bilgi için Windows SDK'daki [PALETTEENTRY'ye](/previous-versions/dd162769\(v=vs.85\)) bakın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek DIBLOOK](../../overview/visual-cpp-samples.md)<br/>
[CGdiObject Sınıfı](../../mfc/reference/cgdiobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CPalette::GetPaletteEntries](#getpaletteentries)<br/>
[CPalette::SetPaletteEntries](#setpaletteentries)
