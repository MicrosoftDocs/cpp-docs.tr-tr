---
title: CPalette sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d4a2b161368b39f586c6393bbf1916d64dacd833
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46381406"
---
# <a name="cpalette-class"></a>CPalette sınıfı

Bir Windows renk paleti kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CPalette : public CGdiObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CPalette::CPalette](#cpalette)|Oluşturur bir `CPalette` eklenmiş Windows palet nesne. Başlatması gerekir `CPalette` kullanılmadan önce başlatma üye işlevleri biriyle nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CPalette::AnimatePalette](#animatepalette)|Tarafından tanımlanan mantıksal paletini girişleri değiştirir `CPalette` nesne. Windows Sistem paleti içine yeni girişler hemen eşlediğinden, istemci alanını güncelleştirmek uygulama yok.|
|[CPalette::CreateHalftonePalette](#createhalftonepalette)|Cihaz bağlamı için bir noktalı paleti oluşturur ve ona ekler `CPalette` nesne.|
|[CPalette::CreatePalette](#createpalette)|Bir Windows renk paleti oluşturur ve ona ekler `CPalette` nesne.|
|[CPalette::FromHandle](#fromhandle)|Bir işaretçi döndüren bir `CPalette` nesne tanıtıcı bir Windows palet nesnesine verildiğinde.|
|[CPalette::GetEntryCount](#getentrycount)|Mantıksal paletteki paleti girdileri sayısını alır.|
|[CPalette::GetNearestPaletteIndex](#getnearestpaletteindex)|Bir renk değeri en yakından eşleşen mantıksal palette giriş dizinini döndürür.|
|[CPalette::GetPaletteEntries](#getpaletteentries)|Mantıksal paletteki paleti girdileri aralığını alır.|
|[CPalette::ResizePalette](#resizepalette)|Tarafından belirtilen mantıksal paletini boyutunu değiştirir `CPalette` girişleri belirtilen sayıda nesne.|
|[CPalette::SetPaletteEntries](#setpaletteentries)|Bir mantıksal paleti girdileri aralığında RGB renk değerleri ve bayraklarını ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[HPALETTE CPalette::operator](#operator_hpalette)|HPALETTE döndürür iliştirilmiş `CPalette`.|

## <a name="remarks"></a>Açıklamalar

Palet bir uygulama ile bir renk çıktı cihazına (örneğin, bir görüntü cihazı) arasında bir arabirim sağlar. Arabirim, diğer uygulamalar tarafından görüntülenen renklerle ciddi bir şekilde müdahale etmeden çıkış cihazın rengi özelliklerinin avantajlarından faydalanmak üzere uygulamayı sağlar. Windows, uygulamanın mantıksal paletini (gerekli renkleri listesini) ve (kullanılabilir renklerin tanımlayan) sistem paleti kullanılan renkleri belirlemek için kullanır.

A `CPalette` nesnesi, nesne tarafından başvurulan paleti düzenleme için üye işlevleri sağlar. Oluşturmak bir `CPalette` nesne ve gerçek paleti, bir grafik cihaz arabirimi (GDI) nesnesi oluşturma ve girişlerin geçerlilik ve diğer özelliklerini değiştirmek için kendi üye işlevleri kullanın.

Kullanma hakkında daha fazla bilgi için `CPalette`, bkz: [grafik nesneleri](../../mfc/graphic-objects.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CPalette`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

##  <a name="animatepalette"></a>  CPalette::AnimatePalette

Ekli mantıksal paletini girişleri değiştirir `CPalette` nesne.

```
void AnimatePalette(
    UINT nStartIndex,
    UINT nNumEntries,
    LPPALETTEENTRY lpPaletteColors);
```

### <a name="parameters"></a>Parametreler

*nStartIndex*<br/>
İlk giriş animasyonlu hale getirilmesini palette belirtir.

*nNumEntries*<br/>
Animasyonlu hale getirilmesini palette giriş sayısını belirtir.

*lpPaletteColors*<br/>
Bir dizi ilk üyesine işaret [PALETTEENTRY](https://msdn.microsoft.com/library/windows/desktop/dd162769) yapıları tarafından tanımlanan paleti girdileri değiştirilecek *nStartIndex* ve *nNumEntries*.

### <a name="remarks"></a>Açıklamalar

Bir uygulama çağırdığında `AnimatePalette`, Windows Sistem paleti içine yeni girişler hemen eşlediğinden, istemci alanını güncelleştirmek yok.

`AnimatePalette` İşlevi yalnızca değiştirecek girişleri ilgili ayarlamak PC_RESERVED bayrağıyla `palPaletteEntry` üyesi [LOGPALETTE](/windows/desktop/api/wingdi/ns-wingdi-taglogpalette) iliştirildiği yapısı `CPalette` nesne. Bu yapı hakkında daha fazla bilgi için Windows SDK'sındaki LOGPALETTE bakın.

##  <a name="cpalette"></a>  CPalette::CPalette

Oluşturur bir `CPalette` nesne.

```
CPalette();
```

### <a name="remarks"></a>Açıklamalar

Çağırana kadar ekli palet nenesindeki `CreatePalette` birini eklemek için.

##  <a name="createhalftonepalette"></a>  CPalette::CreateHalftonePalette

Cihaz bağlamı için bir noktalı paleti oluşturur.

```
BOOL CreateHalftonePalette(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
Cihaz bağlamı tanımlar.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında bir değer, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bir cihaz bağlamının Uzatma modunu için noktalı olarak ayarlandığında bir uygulama bir noktalı paleti oluşturmanız gerekir. Tarafından döndürülen mantıksal noktalı palet [CreateHalftonePalette](/windows/desktop/api/wingdi/nf-wingdi-createhalftonepalette) üye işlevi daha sonra seçilen verilecek ve önce cihaz bağlamına gerçekleşen [CDC::StretchBlt](../../mfc/reference/cdc-class.md#stretchblt) veya [ StretchDIBits](/windows/desktop/api/wingdi/nf-wingdi-stretchdibits) işlevi çağrılır.

Daha fazla bilgi için Windows SDK'sı hakkında bilgi alın `CreateHalftonePalette` ve `StretchDIBits`.

##  <a name="createpalette"></a>  CPalette::CreatePalette

Başlatan bir `CPalette` Windows mantıksal renk paleti oluşturarak ve eklemeyi nesne `CPalette` nesne.

```
BOOL CreatePalette(LPLOGPALETTE lpLogPalette);
```

### <a name="parameters"></a>Parametreler

*lpLogPalette*<br/>
İşaret eden bir [LOGPALETTE](/windows/desktop/api/wingdi/ns-wingdi-taglogpalette) mantıksal palet renkleri hakkında bilgi içeren yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK'sı hakkında bilgi alın `LOGPALETTE` yapısı.

##  <a name="fromhandle"></a>  CPalette::FromHandle

Bir işaretçi döndüren bir `CPalette` nesne tanıtıcı bir Windows palet nesnesine verildiğinde.

```
static CPalette* PASCAL FromHandle(HPALETTE hPalette);
```

### <a name="parameters"></a>Parametreler

*hPalette*<br/>
GDI Windows renk paleti işleyici.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir `CPalette` nesne başarılı; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Varsa bir `CPalette` nesne zaten iliştirilmemiş Windows paleti, geçici bir `CPalette` nesnesi oluşturulur ve bağlı. Bu geçici `CPalette` tüm geçici grafik, zaman sonraki açışınızda uygulama boşta kalma süresi kendi olay döngüsü olana kadar nesneler silinir yalnızca nesne geçerlidir. Diğer bir deyişle, yalnızca bir pencere ileti işleme sırasında geçici nesne geçerli değil.

##  <a name="getentrycount"></a>  CPalette::GetEntryCount

Belirli bir mantıksal paletini içerisindeki giriş sayısını almak için bu üye işlevini çağırın.

```
int GetEntryCount();
```

### <a name="return-value"></a>Dönüş Değeri

Bir mantıksal paletini giriş sayısı.

##  <a name="getnearestpaletteindex"></a>  CPalette::GetNearestPaletteIndex

Belirtilen renk değeri en yakından eşleşen mantıksal palette giriş dizinini döndürür.

```
UINT GetNearestPaletteIndex(COLORREF crColor) const;
```

### <a name="parameters"></a>Parametreler

*crColor*<br/>
Eşleştirilecek rengini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bir mantıksal paletini giriş dizini. En fazla belirtilen rengiyle eşleşen renk giriş içerir.

##  <a name="getpaletteentries"></a>  CPalette::GetPaletteEntries

Mantıksal paletteki paleti girdileri aralığını alır.

```
UINT GetPaletteEntries(
    UINT nStartIndex,
    UINT nNumEntries,
    LPPALETTEENTRY lpPaletteColors) const;
```

### <a name="parameters"></a>Parametreler

*nStartIndex*<br/>
İlk Giriş alınacak, mantıksal paletini belirtir.

*nNumEntries*<br/>
Girdi sayısı alınacak, mantıksal paletini belirtir.

*lpPaletteColors*<br/>
İşaret dizilerine [PALETTEENTRY](https://msdn.microsoft.com/library/windows/desktop/dd162769) paleti girdileri almak için veri yapıları. Dizi en az sayıda veri yapıları tarafından belirtilen içermelidir *nNumEntries*.

### <a name="return-value"></a>Dönüş Değeri

Girdi sayısı mantıksal paletinden alınır; işlev başarısız olursa 0.

##  <a name="operator_hpalette"></a>  HPALETTE CPalette::operator

Ekli Windows GDI tanıtıcısını almak için bu işleci kullanın `CPalette` nesne.

```
operator HPALETTE() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı, Windows GDI nesnesi için bir tanıtıcı tarafından temsil edilen varsa `CPalette` nesne; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

HPALETTE nesne doğrudan kullanımını destekleyen bir yayım işleciyle işlecidir.

Grafik nesneler kullanma hakkında daha fazla bilgi için bkz [grafik nesneleri](/windows/desktop/gdi/graphic-objects) Windows SDK.

##  <a name="resizepalette"></a>  CPalette::ResizePalette

Ekli mantıksal paletini boyutunu değiştirir `CPalette` girdi sayısı bu değeri tarafından belirtilen bir nesneye *nNumEntries*.

```
BOOL ResizePalette(UINT nNumEntries);
```

### <a name="parameters"></a>Parametreler

*nNumEntries*<br/>
Girdi sayısı bu yeniden boyutlandırıldı sonra palette belirtir.

### <a name="return-value"></a>Dönüş Değeri

Palet başarıyla yeniden boyutlandırılmış olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bir uygulama çağırırsa `ResizePalette` paleti boyutunu azaltmak için yeniden boyutlandırılan palette kalan Girişleri değiştirilmez. Uygulama çağırırsa `ResizePalette` paleti genişletmek için ek paleti girdileri (kırmızı, yeşil ve mavi değerler tüm 0) siyah olarak ayarlanır ve tüm ek girdiler için bayraklar 0 olarak ayarlanır.

Windows API hakkında daha fazla bilgi için `ResizePalette`, bkz: [ResizePalette](/windows/desktop/api/wingdi/nf-wingdi-resizepalette) Windows SDK.

##  <a name="setpaletteentries"></a>  CPalette::SetPaletteEntries

Bir mantıksal paleti girdileri aralığında RGB renk değerleri ve bayraklarını ayarlar.

```
UINT SetPaletteEntries(
    UINT nStartIndex,
    UINT nNumEntries,
    LPPALETTEENTRY lpPaletteColors);
```

### <a name="parameters"></a>Parametreler

*nStartIndex*<br/>
İlk giriş ayarlamak için mantıksal paletini belirtir.

*nNumEntries*<br/>
Girdi sayısı bu değeri ayarlamak için mantıksal paletini belirtir.

*lpPaletteColors*<br/>
İşaret dizilerine [PALETTEENTRY](https://msdn.microsoft.com/library/windows/desktop/dd162769) paleti girdileri almak için veri yapıları. Dizi en az sayıda veri yapıları tarafından belirtilen içermelidir *nNumEntries*.

### <a name="return-value"></a>Dönüş Değeri

Girdi sayısı mantıksal palette ayarlayın; işlev başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Mantıksal paletini uygulaması çağırdığında bir cihaz bağlamına seçilirse `SetPaletteEntries`, değişiklikleri uygulama çağrıları kadar etkili olmaz [CDC::RealizePalette](../../mfc/reference/cdc-class.md#realizepalette).

Windows yapısı hakkında daha fazla bilgi için `PALETTEENTRY`, bkz: [PALETTEENTRY](https://msdn.microsoft.com/library/windows/desktop/dd162769) Windows SDK.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC örnek DIBLOOK](../../visual-cpp-samples.md)<br/>
[CGdiObject Sınıfı](../../mfc/reference/cgdiobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CPalette::GetPaletteEntries](#getpaletteentries)<br/>
[CPalette::SetPaletteEntries](#setpaletteentries)



