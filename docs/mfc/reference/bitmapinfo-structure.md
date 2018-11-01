---
title: BITMAPINFO Yapısı
ms.date: 11/04/2016
f1_keywords:
- BITMAPINFO
helpviewer_keywords:
- BITMAPINFO structure [MFC]
ms.assetid: a00caa49-e4df-419f-89a7-ab03c13a1b5b
ms.openlocfilehash: 8e0586d197bc2f18a06fd675bf365750c6d129ad
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50542278"
---
# <a name="bitmapinfo-structure"></a>BITMAPINFO Yapısı

`BITMAPINFO` Boyutları ve bir Windows CİHAZDAN bağımsız bit eşlem (DIB) için renk bilgisi yapısını tanımlar.

## <a name="syntax"></a>Sözdizimi

```
typedef struct tagBITMAPINFO {
    BITMAPINFOHEADER bmiHeader;
    RGBQUAD bmiColors[1];
} BITMAPINFO;
```

#### <a name="parameters"></a>Parametreler

*bmiHeader*<br/>
Belirtir bir [BITMAPINFOHEADER](https://msdn.microsoft.com/library/windows/desktop/dd183376) boyutları ve CİHAZDAN bağımsız bit eşlem renk biçimi hakkında bilgi içeren yapısı.

*bmiColors*<br/>
Bir dizi belirtir [RGBQUAD](/windows/desktop/api/wingdi/ns-wingdi-tagrgbquad) ya da bit eşlem içinde Renk Tanımla DWORD veri türleri.

## <a name="remarks"></a>Açıklamalar

CİHAZDAN bağımsız bit eşlem iki farklı bölümden oluşur: bir `BITMAPINFO` renkleri bit eşlemin ve bit eşlemin piksel belirten bir bayt dizisi ve boyutları açıklar yapısı. Dizideki BITS birlikte paketlenmiş, ancak her bir tarama satır bitiş sıfırlarla sıfır olmalıdır bir **uzun** sınır. Yüksekliği pozitif ise, bit eşlem kaynağı sol alt köşesinde ' dir. Yüksekliği negatif ise, kaynak üst sol löşede ' dir.

A *paketlenmiş bir bit eşlem* yeri bayt dizisinin hemen izleyen bir bit eşlem ise `BITMAPINFO` yapısı. Paketlenmiş bit eşlemler, tek bir işaretçi tarafından başvurulur.

Hakkında daha fazla bilgi için `BITMAPINFO` yapısı ve üyeleri için uygun değerleri `BITMAPINFOHEADER` ve `RGBQUAD` yapıları, Windows SDK belgelerinde aşağıdaki konulara bakın.

- [BITMAPINFO yapısı](/windows/desktop/api/wingdi/ns-wingdi-tagbitmapinfo)

- [BITMAPINFOHEADER](https://msdn.microsoft.com/library/windows/desktop/dd183376) yapısı

- [RGBQUAD](/windows/desktop/api/wingdi/ns-wingdi-tagrgbquad) yapısı

## <a name="requirements"></a>Gereksinimler

**Başlık:** wingdi.h

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CBrush::CreateDIBPatternBrush](../../mfc/reference/cbrush-class.md#createdibpatternbrush)<br/>
[BITMAPINFOHEADER](https://msdn.microsoft.com/library/windows/desktop/dd183376)<br/>
[RGBQUAD](/windows/desktop/api/wingdi/ns-wingdi-tagrgbquad)

