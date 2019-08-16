---
title: CPalette sınıfı
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
ms.openlocfilehash: 27f4f14c9e93091728e256c890dcffee26a43de4
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502996"
---
# <a name="cpalette-class"></a>CPalette sınıfı

Bir Windows renk paletini kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CPalette : public CGdiObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CPalette:: CPalette](#cpalette)|İliştirilmiş Windows `CPalette` paleti olmayan bir nesne oluşturur. Kullanılmadan önce, `CPalette` başlatma üye işlevlerinden birini kullanarak nesneyi başlatmalısınız.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CPalette:: AnimatePalette](#animatepalette)|`CPalette` Nesne tarafından tanımlanan mantıksal Paletteki girişleri değiştirir. Windows yeni girdileri sistem paletine anında eşletiğinden uygulamanın istemci alanını güncelleştirmesi gerekmez.|
|[CPalette:: Createnoktalı Tonepaleti](#createhalftonepalette)|Cihaz bağlamı için bir yarı ton paleti oluşturur ve `CPalette` nesneye ekler.|
|[CPalette:: CreatePalette](#createpalette)|Bir Windows renk paleti oluşturur ve `CPalette` nesneye iliştirir.|
|[CPalette:: FromHandle](#fromhandle)|Bir Windows paleti nesnesine bir `CPalette` tanıtıcı verildiğinde nesnenin işaretçisini döndürür.|
|[CPalette:: GetEntryCount](#getentrycount)|Bir mantıksal Paletteki palet girişi sayısını alır.|
|[CPalette:: Getnearestpaletteındex](#getnearestpaletteindex)|Mantıksal Paletteki, bir renk değeriyle en yakından eşleşen girdinin dizinini döndürür.|
|[CPalette:: GetPaletteEntries](#getpaletteentries)|Bir mantıksal Paletteki palet girişi aralığını alır.|
|[CPalette:: ResizePalette](#resizepalette)|`CPalette` Nesne tarafından belirtilen mantıksal paletin boyutunu belirtilen girdi sayısı olarak değiştirir.|
|[CPalette:: SetPaletteEntries](#setpaletteentries)|Mantıksal bir paletteki bir giriş aralığındaki RGB renk değerlerini ve bayraklarını ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CPalette:: operator HPALETI](#operator_hpalette)|Öğesine eklenen HPALETI döndürür `CPalette`.|

## <a name="remarks"></a>Açıklamalar

Palet, bir uygulama ile renk çıkış aygıtı (örneğin, bir görüntü cihazı) arasında bir arabirim sağlar. Arabirim, uygulamanın çıkış cihazının renk yeteneklerini, diğer uygulamalar tarafından görüntülenmeksizin ciddi bir şekilde etkilenmeden tam olarak yararlanmasını sağlar. Windows, kullanılan renklerin belirlenmesi için uygulamanın mantıksal paletini (gerekli renklerin listesini) ve sistem paletini (kullanılabilir renkleri tanımlar) kullanır.

`CPalette` Nesnesi, nesne tarafından başvurulan paleti işlemek için üye işlevleri sağlar. Bir `CPalette` nesne oluşturun ve kendi üye işlevlerini kullanarak gerçek palet, bir grafik cihaz arabirimi (GDI) nesnesi oluşturun ve girişlerini ve diğer özelliklerini değiştirin.

Kullanma `CPalette`hakkında daha fazla bilgi için bkz. [grafik nesneleri](../../mfc/graphic-objects.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CPalette`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

##  <a name="animatepalette"></a>CPalette:: AnimatePalette

`CPalette` Nesneye eklenen mantıksal Paletteki girişleri değiştirir.

```
void AnimatePalette(
    UINT nStartIndex,
    UINT nNumEntries,
    LPPALETTEENTRY lpPaletteColors);
```

### <a name="parameters"></a>Parametreler

*nStartIndex*<br/>
Paletteki animasyon eklenecek ilk girişi belirtir.

*nNumEntries*<br/>
Paletteki animasyon eklenecek girişlerin sayısını belirtir.

*lpPaletteColors*<br/>
*NStartIndex* ve *nNumEntries*tarafından tanımlanan palet girişlerinin yerini alacak bir [paletteentry](/previous-versions/dd162769\(v=vs.85\)) yapıları dizisinin ilk üyesini işaret eder.

### <a name="remarks"></a>Açıklamalar

Bir uygulama aradığında `AnimatePalette`, Windows yeni girdileri sistem paletine anında eşlediğinden, istemci alanını güncelleştirmek zorunda değildir.

İşlevi yalnızca, nesnesine`CPalette` bağlı olan [LOGPALETTE](/windows/win32/api/wingdi/ns-wingdi-logpalette) yapısının karşılık gelen `palPaletteEntry` üyesinde, girdileri yalnızca PC_RESERVED bayrağını ayarlanmış olarak değiştirir. `AnimatePalette` Bu yapı hakkında daha fazla bilgi için bkz. Windows SDK LOGPALETTE.

##  <a name="cpalette"></a>CPalette:: CPalette

Bir `CPalette` nesnesi oluşturur.

```
CPalette();
```

### <a name="remarks"></a>Açıklamalar

Eklemek için çağrı `CreatePalette` yapana kadar nesnenin iliştirilmiş paleti yok.

##  <a name="createhalftonepalette"></a>CPalette:: Createnoktalı Tonepaleti

Cihaz bağlamı için bir yarı ton paleti oluşturur.

```
BOOL CreateHalftonePalette(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
Cihaz bağlamını tanımlar.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bir uygulama, bir cihaz bağlamının uzatma modu yarı ton olarak ayarlandığında bir yarı ton paleti oluşturmalıdır. [Createyarı noktalı Tonepalette](/windows/win32/api/wingdi/nf-wingdi-createhalftonepalette) üye işlevi tarafından döndürülen mantıksal noktalı palet, [CDC:: ıbblt](../../mfc/reference/cdc-class.md#stretchblt) veya ıdidıgeler işlevi çağrılmadan önce cihaz bağlamına seçilmelidir ve [](/windows/win32/api/wingdi/nf-wingdi-stretchdibits) gerçekleştirilmelidir.

`CreateHalftonePalette` Ve`StretchDIBits`hakkında daha fazla bilgi için Windows SDK bakın.

##  <a name="createpalette"></a>CPalette:: CreatePalette

Bir Windows `CPalette` mantıksal renk paleti oluşturup `CPalette` nesneye ekleyerek bir nesneyi başlatır.

```
BOOL CreatePalette(LPLOGPALETTE lpLogPalette);
```

### <a name="parameters"></a>Parametreler

*lpLogPalette*<br/>
Mantıksal Paletteki renkler hakkında bilgi içeren bir [LOGPALETTE](/windows/win32/api/wingdi/ns-wingdi-logpalette) yapısına işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`LOGPALETTE` Yapı hakkında daha fazla bilgi için Windows SDK bakın.

##  <a name="fromhandle"></a>CPalette:: FromHandle

Bir Windows paleti nesnesine bir `CPalette` tanıtıcı verildiğinde nesnenin işaretçisini döndürür.

```
static CPalette* PASCAL FromHandle(HPALETTE hPalette);
```

### <a name="parameters"></a>Parametreler

*hPalette*<br/>
Windows GDI renk paleti için bir tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa `CPalette` nesne için bir işaretçi; Aksi takdirde null.

### <a name="remarks"></a>Açıklamalar

Bir `CPalette` nesne Windows paletine zaten iliştirilmişse, geçici `CPalette` bir nesne oluşturulur ve eklenir. Bu geçici `CPalette` nesne yalnızca uygulamanın olay döngüsünde bir sonraki kez boşta kalması durumunda geçerlidir. bu süre, tüm geçici grafik nesneleri silinir. Diğer bir deyişle, geçici nesne yalnızca bir pencere iletisi işlenirken geçerlidir.

##  <a name="getentrycount"></a>CPalette:: GetEntryCount

Verilen bir mantıksal Paletteki giriş sayısını almak için bu üye işlevi çağırın.

```
int GetEntryCount();
```

### <a name="return-value"></a>Dönüş Değeri

Mantıksal bir paletteki giriş sayısı.

##  <a name="getnearestpaletteindex"></a>CPalette:: Getnearestpaletteındex

Mantıksal Paletteki, belirtilen renk değeriyle en yakından eşleşen girdinin dizinini döndürür.

```
UINT GetNearestPaletteIndex(COLORREF crColor) const;
```

### <a name="parameters"></a>Parametreler

*crColor*<br/>
Eşleştirilecek rengi belirtir.

### <a name="return-value"></a>Dönüş Değeri

Mantıksal palet içindeki bir girdinin dizini. Giriş, belirtilen renkle en neredeyse eşleşen rengi içerir.

##  <a name="getpaletteentries"></a>CPalette:: GetPaletteEntries

Bir mantıksal Paletteki palet girişi aralığını alır.

```
UINT GetPaletteEntries(
    UINT nStartIndex,
    UINT nNumEntries,
    LPPALETTEENTRY lpPaletteColors) const;
```

### <a name="parameters"></a>Parametreler

*nStartIndex*<br/>
Alınacak mantıksal Paletteki ilk girişi belirtir.

*nNumEntries*<br/>
Alınacak mantıksal Paletteki giriş sayısını belirtir.

*lpPaletteColors*<br/>
Palet girişlerini almak için bir [paletteentry](/previous-versions/dd162769\(v=vs.85\)) veri yapıları dizisine işaret eder. Dizi, *nNumEntries*tarafından belirtilen en az sayıda veri yapısı içermelidir.

### <a name="return-value"></a>Dönüş Değeri

Mantıksal paletten alınan giriş sayısı; işlev başarısız olursa 0.

##  <a name="operator_hpalette"></a>CPalette:: operator HPALETI

`CPalette` Nesnenin ekli Windows GDI işleyicisini almak için bu işleci kullanın.

```
operator HPALETTE() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, `CPalette` nesne tarafından temsil edilen Windows GDI nesnesine yönelik bir tanıtıcı; Aksi takdirde null.

### <a name="remarks"></a>Açıklamalar

Bu işleç, bir HPALETTE nesnesinin doğrudan kullanımını destekleyen bir atama işleçtir.

Grafik nesnelerini kullanma hakkında daha fazla bilgi için, Windows SDK [grafik nesneleri](/windows/win32/gdi/graphic-objects) makalesine bakın.

##  <a name="resizepalette"></a>CPalette:: ResizePalette

`CPalette` Nesnesine eklenen mantıksal paletin boyutunu *nNumEntries*tarafından belirtilen giriş sayısına dönüştürür.

```
BOOL ResizePalette(UINT nNumEntries);
```

### <a name="parameters"></a>Parametreler

*nNumEntries*<br/>
Yeniden boyutlandıralındıktan sonra paletteki giriş sayısını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Palet başarıyla yeniden boyutlandırılmışsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir uygulama, paletin `ResizePalette` boyutunu azaltmak için çağrı yaparsanız, yeniden boyutlandırılmış palet içinde kalan girişler değiştirilmez. Uygulama paleti büyütmek için `ResizePalette` çağırırsa, ek palet girişleri siyah (kırmızı, yeşil ve mavi değerleri 0 ' dır) olarak ayarlanır ve tüm ek girdilerin bayrakları 0 olarak ayarlanır.

Windows API 'si `ResizePalette`hakkında daha fazla bilgi için Windows SDK [ResizePalette](/windows/win32/api/wingdi/nf-wingdi-resizepalette) bölümüne bakın.

##  <a name="setpaletteentries"></a>CPalette:: SetPaletteEntries

Mantıksal bir paletteki bir giriş aralığındaki RGB renk değerlerini ve bayraklarını ayarlar.

```
UINT SetPaletteEntries(
    UINT nStartIndex,
    UINT nNumEntries,
    LPPALETTEENTRY lpPaletteColors);
```

### <a name="parameters"></a>Parametreler

*nStartIndex*<br/>
Ayarlanacak mantıksal Paletteki ilk girişi belirtir.

*nNumEntries*<br/>
Ayarlanacak mantıksal Paletteki giriş sayısını belirtir.

*lpPaletteColors*<br/>
Palet girişlerini almak için bir [paletteentry](/previous-versions/dd162769\(v=vs.85\)) veri yapıları dizisine işaret eder. Dizi, *nNumEntries*tarafından belirtilen en az sayıda veri yapısı içermelidir.

### <a name="return-value"></a>Dönüş Değeri

Mantıksal palette ayarlanan giriş sayısı; işlev başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Uygulama çağrı `SetPaletteEntries`yaparken mantıksal palet bir cihaz bağlamına seçildiyse, uygulama [CDC:: RealizePalette](../../mfc/reference/cdc-class.md#realizepalette)öğesini çağırana kadar değişiklikler geçerli olmayacaktır.

Daha fazla bilgi için Windows SDK [paletteentry](/previous-versions/dd162769\(v=vs.85\)) bölümüne bakın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek DIBLOOK](../../overview/visual-cpp-samples.md)<br/>
[CGdiObject Sınıfı](../../mfc/reference/cgdiobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CPalette:: GetPaletteEntries](#getpaletteentries)<br/>
[CPalette:: SetPaletteEntries](#setpaletteentries)
