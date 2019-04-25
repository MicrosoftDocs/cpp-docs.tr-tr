---
title: Gereken Değerleri Hesaplama
ms.date: 11/04/2016
helpviewer_keywords:
- helper functions, calculating necessary values
ms.assetid: 4f037d0f-881a-4a48-a9d2-9f8872dfccb7
ms.openlocfilehash: 75952bbcdf823aa675b35702841c81e511105ca8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62272656"
---
# <a name="calculating-necessary-values"></a>Gereken Değerleri Hesaplama

İki kritik bilgilere gecikme Yardımcısı yordamından hesaplanması gerekir. Bu amaçla bu bilgileri hesaplamak delayhlp.cpp içindeki iki satır içi işlevleri vardır.

- İlk geçerli içeri aktarma (içeri aktarma adres tablosu (IAT) ve ilişkili içeri aktarma adres tablosunda (BIAT) ilişkisiz içeri aktarma adres tablosunda (UIAT)) üç farklı tablolara dizinini hesaplar.

- İkinci bir geçerli IAT Imports sayar.

```cpp
// utility function for calculating the index of the current import
// for all the tables (INT, BIAT, UIAT, and IAT).
__inline unsigned
IndexFromPImgThunkData(PCImgThunkData pitdCur, PCImgThunkData pitdBase) {
    return pitdCur - pitdBase;
    }

// utility function for calculating the count of imports given the base
// of the IAT. NB: this only works on a valid IAT!
__inline unsigned
CountOfImports(PCImgThunkData pitdBase) {
    unsigned        cRet = 0;
    PCImgThunkData  pitd = pitdBase;
    while (pitd->u1.Function) {
        pitd++;
        cRet++;
        }
    return cRet;
    }
```

## <a name="see-also"></a>Ayrıca bkz.

[Yardımcı İşlevini Anlama](understanding-the-helper-function.md)
