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
ms.openlocfilehash: bbc64aad0d65c0430ad23b96f635be8fe2b396e0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81357034"
---
# <a name="gray-and-dithered-bitmap-functions"></a>Gri ve Titremeli Bit Eşlem İşlevleri

**Gri Bitmap Fonksiyonları**

MFC, bir bitmap'e devre dışı bırakma denetimi görünümünü vermek için iki işlev sağlar.

![Gri ve orijinal simge sürümlerinin karşılaştırılması](../../mfc/reference/media/vcgraybitmap.gif "Gri ve orijinal simge sürümlerinin karşılaştırılması")

|||
|-|-|
|[AfxDrawGrayBitmap](#afxdrawgraybitmap)|Biteşin gri bir sürümünü çizer.|
|[AfxGetGrayBitmap](#afxgetgraybitmap)|Bit eşlenin gri bir sürümünü kopyalar.|

**Dithered Bitmap Fonksiyonları**

MFC ayrıca, bitmap'in arka planını dithered desenle değiştirmek için iki işlev de sağlar.

![Dithered ve orijinal simge sürümlerinin karşılaştırılması](../../mfc/reference/media/vcditheredbitmap.gif "Dithered ve orijinal simge sürümlerinin karşılaştırılması")

|||
|-|-|
|[AfxDrawDitheredBitmap](#afxdrawditheredbitmap)|Dithered arka plan ile bir bit eşlemi çizer.|
|[AfxGetDitheredBitmap](#afxgetditheredbitmap)|Dithered arka plan ile bir bit eşlemi kopyalar.|

## <a name="afxdrawgraybitmap"></a><a name="afxdrawgraybitmap"></a>AfxDrawGrayBitmap

Biteşin gri bir sürümünü çizer.

```
void AFXAPI AfxDrawGrayBitmap(
    CDC* pDC,
    int x,
    int y,
    const CBitmap& rSrc,
    COLORREF crBackground);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
Hedef DC'yi işaret edin.

*X*<br/>
Hedef x-koordinat.

*Y*<br/>
Hedef y-koordinat.

*rSrc*<br/>
Kaynak bit haritası.

*crArka plan*<br/>
Yeni arka plan rengi (genellikle COLOR_MENU gibi gri).

### <a name="remarks"></a>Açıklamalar

Bir bitmap `AfxDrawGrayBitmap` ile çizilmiş bir devre dışı denetim görünümüne sahip olacaktır.

![Gri ve orijinal simge sürümlerinin karşılaştırılması](../../mfc/reference/media/vcgraybitmap.gif "Gri ve orijinal simge sürümlerinin karşılaştırılması")

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#191](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_1.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="afxgetgraybitmap"></a><a name="afxgetgraybitmap"></a>AfxGetGrayBitmap

Bit eşlenin gri bir sürümünü kopyalar.

```
void AFXAPI AfxGetGrayBitmap(
    const CBitmap& rSrc,
    CBitmap* pDest,
    COLORREF crBackground);
```

### <a name="parameters"></a>Parametreler

*rSrc*<br/>
Kaynak bit haritası.

*pDest*<br/>
Hedef bit haritası.

*crArka plan*<br/>
Yeni arka plan rengi (genellikle COLOR_MENU gibi gri).

### <a name="remarks"></a>Açıklamalar

Kopyalanan bir biteş, devre dışı bırakma denetimi görünümüne sahip `AfxGetGrayBitmap` olacaktır.

![Gri ve orijinal simge sürümlerinin karşılaştırılması](../../mfc/reference/media/vcgraybitmap.gif "Gri ve orijinal simge sürümlerinin karşılaştırılması")

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#193](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_2.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="afxdrawditheredbitmap"></a><a name="afxdrawditheredbitmap"></a>AfxDrawDitheredBitmap

Arka planını bir dithered (denetleyici) desenle değiştirerek bir bit eşlemi çizer.

```
void AFXAPI AfxDrawDitheredBitmap(
    CDC* pDC,
    int x,
    int y,
    const CBitmap& rSrc,
    COLORREF cr1  ,
    COLORREF cr2);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
Hedef DC'yi işaret edin.

*X*<br/>
Hedef x-koordinat.

*Y*<br/>
Hedef y-koordinat.

*rSrc*<br/>
Kaynak bit haritası.

*cr1*<br/>
İki renk renkten biri, genellikle beyaz.

*cr2*<br/>
Diğer renk tesnivar rengi, genellikle açık gri (COLOR_MENU).

### <a name="remarks"></a>Açıklamalar

Kaynak bit eşlemi, biteşin arka planının yerine iki renkli *(cr1* ve *cr2)* damalı desenle hedef DC'ye çizilir. Kaynak bit eşleminin arka planı, beyaz pikselleri ve bit eşleminin sol üst köşesindeki pikselin rengiyle eşleşen tüm pikseller olarak tanımlanır.

![Dithered ve orijinal simge sürümlerinin karşılaştırılması](../../mfc/reference/media/vcditheredbitmap.gif "Dithered ve orijinal simge sürümlerinin karşılaştırılması")

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#190](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_3.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="afxgetditheredbitmap"></a><a name="afxgetditheredbitmap"></a>AfxGetDitheredBitmap

Bir bit eşlemi kopyalayarak arka planını dithered (denetleyici) desenle değiştirir.

```
void AFXAPI AfxGetDitheredBitmap(
    const CBitmap& rSrc,
    CBitmap* pDest,
    COLORREF cr1  ,
    COLORREF cr2);
```

### <a name="parameters"></a>Parametreler

*rSrc*<br/>
Kaynak bit haritası.

*pDest*<br/>
Hedef bit haritası.

*cr1*<br/>
İki renk renkten biri, genellikle beyaz.

*cr2*<br/>
Diğer renk tesnivar rengi, genellikle açık gri (COLOR_MENU).

### <a name="remarks"></a>Açıklamalar

Kaynak bit eşlemi, kaynak bit eşlemesinin arka planının yerine iki renkli *(cr1* ve *cr2)* damalı desenle hedef bit eşlemekopyalanır. Kaynak bit eşleminin arka planı, beyaz pikselleri ve bit eşleminin sol üst köşesindeki pikselin rengiyle eşleşen tüm pikseller olarak tanımlanır.

![Dithered ve orijinal simge sürümlerinin karşılaştırılması](../../mfc/reference/media/vcditheredbitmap.gif "vcditheredbitmap")

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#192](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_4.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve Küreseller](../../mfc/reference/mfc-macros-and-globals.md)
