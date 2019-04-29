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
ms.openlocfilehash: fb764dbd71d89ae3317816df3539c2881b9695b6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62322333"
---
# <a name="gray-and-dithered-bitmap-functions"></a>Gri ve Titremeli Bit Eşlem İşlevleri

**Gri bir bit eşlem işlevleri**

MFC devre dışı bırakılmış bir denetimin görünümünü bir bit eşlem vermek için iki işlev sağlar.

![Gri ve özgün simgesi sürümlerinin karşılaştırma](../../mfc/reference/media/vcgraybitmap.gif "gri ve özgün simgesi sürümleri karşılaştırma")

|||
|-|-|
|[AfxDrawGrayBitmap](#afxdrawgraybitmap)|Bir bit eşlem gri bir sürümünü çizer.|
|[AfxGetGrayBitmap](#afxgetgraybitmap)|Bir bit eşlem gri bir sürümünü kopyalar.|

**Titremeli bit eşlem işlevleri**

MFC bir bit eşleşmemin arka plan Titremeli desenle değiştirmek için iki işlev de sağlar.

![Titremeli ve özgün simgesi sürümlerinin karşılaştırma](../../mfc/reference/media/vcditheredbitmap.gif "Titremeli ve özgün simgesi sürümleri karşılaştırma")

|||
|-|-|
|[AfxDrawDitheredBitmap](#afxdrawditheredbitmap)|Bir bit eşlem ile Titremeli arka planı çizer.|
|[AfxGetDitheredBitmap](#afxgetditheredbitmap)|Titremeli arka plana sahip bit eşleme kopyalar.|

##  <a name="afxdrawgraybitmap"></a>  AfxDrawGrayBitmap

Bir bit eşlem gri bir sürümünü çizer.

```
void AFXAPI AfxDrawGrayBitmap(
    CDC* pDC,
    int x,
    int y,
    const CBitmap& rSrc,
    COLORREF crBackground);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
Hedef DC işaret eder.

*x*<br/>
Hedef x koordinatı.

*Y*<br/>
Hedef y koordinatı.

*rSrc*<br/>
Kaynak bit eşlemi.

*crBackground*<br/>
Yeni arka plan rengi (COLOR_MENU gibi genellikle gri).

### <a name="remarks"></a>Açıklamalar

İle çizilen bir bit eşlem `AfxDrawGrayBitmap` devre dışı bırakılmış bir denetimin görünümünü sahip olur.

![Gri ve özgün simgesi sürümlerinin karşılaştırma](../../mfc/reference/media/vcgraybitmap.gif "gri ve özgün simgesi sürümleri karşılaştırma")

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#191](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_1.cpp)]

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

##  <a name="afxgetgraybitmap"></a>  AfxGetGrayBitmap

Bir bit eşlem gri bir sürümünü kopyalar.

```
void AFXAPI AfxGetGrayBitmap(
    const CBitmap& rSrc,
    CBitmap* pDest,
    COLORREF crBackground);
```

### <a name="parameters"></a>Parametreler

*rSrc*<br/>
Kaynak bit eşlemi.

*pDest*<br/>
Hedef bit eşlemi.

*crBackground*<br/>
Yeni arka plan rengi (COLOR_MENU gibi genellikle gri).

### <a name="remarks"></a>Açıklamalar

Bir bit eşlem ile kopyalanan `AfxGetGrayBitmap` devre dışı bırakılmış bir denetimin görünümünü sahip olur.

![Gri ve özgün simgesi sürümlerinin karşılaştırma](../../mfc/reference/media/vcgraybitmap.gif "gri ve özgün simgesi sürümleri karşılaştırma")

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#193](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_2.cpp)]

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

##  <a name="afxdrawditheredbitmap"></a>  AfxDrawDitheredBitmap

Arka planı Titremeli (denetleyicisi) desen ile değiştirerek bir bit eşlem çizer.

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

*pDC*<br/>
Hedef DC işaret eder.

*x*<br/>
Hedef x koordinatı.

*Y*<br/>
Hedef y koordinatı.

*rSrc*<br/>
Kaynak bit eşlemi.

*cr1*<br/>
Bir iki renk paleti öykünmesi renkler, genellikle beyaz.

*cr2*<br/>
Diğer renk paleti öykünmesi rengi, genellikle açık gri (COLOR_MENU).

### <a name="remarks"></a>Açıklamalar

Kaynak bit eşlemi hedef DC iki renk ile çizilir (*cr1* ve *cr2*) Damalı desen bit eşleşmemin arka plan değiştirme. Kaynak bit eşlemi arka planı beyaz piksellerinin ve sol üst köşedeki bit eşlemin piksel rengi eşleşen tüm piksel olarak tanımlanır.

![Titremeli ve özgün simgesi sürümlerinin karşılaştırma](../../mfc/reference/media/vcditheredbitmap.gif "Titremeli ve özgün simgesi sürümleri karşılaştırma")

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#190](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_3.cpp)]

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

##  <a name="afxgetditheredbitmap"></a>  AfxGetDitheredBitmap

Arka planı Titremeli (denetleyicisi) desen ile değiştirerek bir bit eşlem kopyalar.

```
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
Hedef bit eşlemi.

*cr1*<br/>
Bir iki renk paleti öykünmesi renkler, genellikle beyaz.

*cr2*<br/>
Diğer renk paleti öykünmesi rengi, genellikle açık gri (COLOR_MENU).

### <a name="remarks"></a>Açıklamalar

Kaynak bit eşlemi hedef bit eşlemi iki renk ile kopyalanır (*cr1* ve *cr2*) kaynak bit eşleşmemin arka plan değiştirme Damalı deseni. Kaynak bit eşlemi arka planı beyaz piksellerinin ve sol üst köşedeki bit eşlemin piksel rengi eşleşen tüm piksel olarak tanımlanır.

![Titremeli ve özgün simgesi sürümlerinin karşılaştırma](../../mfc/reference/media/vcditheredbitmap.gif "vcditheredbitmap")

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#192](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_4.cpp)]

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

## <a name="see-also"></a>Ayrıca bkz.

[Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
