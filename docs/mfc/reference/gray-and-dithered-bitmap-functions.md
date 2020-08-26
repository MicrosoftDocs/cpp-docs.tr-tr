---
title: Gri ve Titremeli Bit Eşlem İşlevleri
ms.date: 11/19/2018
f1_keywords:
- AFXWIN/AfxDrawGrayBitmap
- AFXWIN/AfxGetGrayBitmap
- AFXWIN/AfxDrawDitheredBitmap
- AFXWIN/AfxGetDitheredBitmap
helpviewer_keywords:
- gray and dithered bitmap functions [MFC]
ms.assetid: cb139a77-b85e-4504-9d93-24156ad77a41
ms.openlocfilehash: 57f163fd36c0f25508d94a84495fcaf1956e277d
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88837209"
---
# <a name="gray-and-dithered-bitmap-functions"></a>Gri ve Titremeli Bit Eşlem İşlevleri

**Gri bit eşlem Işlevleri**

MFC devre dışı bir denetimin görüntüsünü bir bit eşlem vermek için iki işlev sağlar.

![Gri ve özgün simge sürümlerinin karşılaştırması](../../mfc/reference/media/vcgraybitmap.gif "Gri ve özgün simge sürümlerinin karşılaştırması")

|Ad|Açıklama|
|-|-|
|[Afxdrawgribit eşlem](#afxdrawgraybitmap)|Bit eşlemin gri sürümünü çizer.|
|[Afxgetgribit eşlem](#afxgetgraybitmap)|Bit eşlemin gri sürümünü kopyalar.|

**Titremeli bit eşlem Işlevleri**

MFC, bir bit eşlemin arka planını bir titremeli düzeniyle değiştirmek için iki işlev de sağlar.

![Titremeli ve özgün simge sürümlerinin karşılaştırması](../../mfc/reference/media/vcditheredbitmap.gif "Titremeli ve özgün simge sürümlerinin karşılaştırması")

|Ad|Açıklama|
|-|-|
|[Afxdrawdıtheredbitmap](#afxdrawditheredbitmap)|Titremeli arka planına sahip bir bit eşlem çizer.|
|[AfxGetDitheredBitmap](#afxgetditheredbitmap)|Bir bit eşlemi titremeli arka planıyla kopyalar.|

## <a name="afxdrawgraybitmap"></a><a name="afxdrawgraybitmap"></a> Afxdrawgribit eşlem

Bit eşlemin gri sürümünü çizer.

```cpp
void AFXAPI AfxDrawGrayBitmap(
    CDC* pDC,
    int x,
    int y,
    const CBitmap& rSrc,
    COLORREF crBackground);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
Hedef DC 'ye işaret eder.

*x*<br/>
Hedef x koordinatı.

*Iz*<br/>
Hedef y koordinatı.

*rSrc*<br/>
Kaynak bit eşlemi.

*crBackground*<br/>
Yeni arka plan rengi (genellikle COLOR_MENU gibi gri).

### <a name="remarks"></a>Açıklamalar

İle çizilen bir bit eşlem `AfxDrawGrayBitmap` , devre dışı bir denetimin görünümüne sahip olur.

![Gri ve özgün simge sürümlerinin karşılaştırması](../../mfc/reference/media/vcgraybitmap.gif "Gri ve özgün simge sürümlerinin karşılaştırması")

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#191](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_1.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="afxgetgraybitmap"></a><a name="afxgetgraybitmap"></a> Afxgetgribit eşlem

Bit eşlemin gri sürümünü kopyalar.

```cpp
void AFXAPI AfxGetGrayBitmap(
    const CBitmap& rSrc,
    CBitmap* pDest,
    COLORREF crBackground);
```

### <a name="parameters"></a>Parametreler

*rSrc*<br/>
Kaynak bit eşlemi.

*pDest*<br/>
Hedef bit eşlem.

*crBackground*<br/>
Yeni arka plan rengi (genellikle COLOR_MENU gibi gri).

### <a name="remarks"></a>Açıklamalar

İle kopyalanmış bir bit eşlem `AfxGetGrayBitmap` , devre dışı bir denetimin görünümüne sahip olur.

![Gri ve özgün simge sürümlerinin karşılaştırması](../../mfc/reference/media/vcgraybitmap.gif "Gri ve özgün simge sürümlerinin karşılaştırması")

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#193](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_2.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="afxdrawditheredbitmap"></a><a name="afxdrawditheredbitmap"></a> Afxdrawdıtheredbitmap

Arka planını bir titremeli (Checker) düzeniyle değiştirerek bir bit eşlem çizer.

```cpp
void AFXAPI AfxDrawDitheredBitmap(
    CDC* pDC,
    int x,
    int y,
    const CBitmap& rSrc,
    COLORREF cr1  ,
    COLORREF cr2);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
Hedef DC 'ye işaret eder.

*x*<br/>
Hedef x koordinatı.

*Iz*<br/>
Hedef y koordinatı.

*rSrc*<br/>
Kaynak bit eşlemi.

*cr1*<br/>
İki renk taklidi renginden biri genellikle beyaz.

*cr2*<br/>
Diğer titreme rengi, genellikle açık gri (COLOR_MENU).

### <a name="remarks"></a>Açıklamalar

Kaynak bit eşlem, hedef DC 'de, bit eşlemin arka planını değiştiren iki renkli (*cr1* ve *CR2*) damalı düzeniyle çizilir. Kaynak bit eşlemin arka planı, beyaz piksel ve bit eşlemin sol üst köşesindeki pikselin rengi ile eşleşen tüm pikseller olarak tanımlanır.

![Titremeli ve özgün simge sürümlerinin karşılaştırması](../../mfc/reference/media/vcditheredbitmap.gif "Titremeli ve özgün simge sürümlerinin karşılaştırması")

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#190](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_3.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="afxgetditheredbitmap"></a><a name="afxgetditheredbitmap"></a> AfxGetDitheredBitmap

Arka planını bir titremeli (Checker) düzeniyle değiştirerek bir bit eşlemi kopyalar.

```cpp
void AFXAPI AfxGetDitheredBitmap(
    const CBitmap& rSrc,
    CBitmap* pDest,
    COLORREF cr1  ,
    COLORREF cr2);
```

### <a name="parameters"></a>Parametreler

*rSrc*<br/>
Kaynak bit eşlemi.

*pDest*<br/>
Hedef bit eşlem.

*cr1*<br/>
İki renk taklidi renginden biri genellikle beyaz.

*cr2*<br/>
Diğer titreme rengi, genellikle açık gri (COLOR_MENU).

### <a name="remarks"></a>Açıklamalar

Kaynak bit eşlem, kaynak bit eşlemin arka planını değiştiren iki renkli (*cr1* ve *CR2*) damalı düzenine sahip hedef bit eşlemine kopyalanır. Kaynak bit eşlemin arka planı, beyaz piksel ve bit eşlemin sol üst köşesindeki pikselin rengi ile eşleşen tüm pikseller olarak tanımlanır.

![Titremeli ve özgün simge sürümlerinin karşılaştırması](../../mfc/reference/media/vcditheredbitmap.gif "vcditheredbitmap")

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#192](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_4.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](../../mfc/reference/mfc-macros-and-globals.md)
