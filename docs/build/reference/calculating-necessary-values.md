---
description: 'Hakkında daha fazla bilgi edinin: gerekli değerleri hesaplama'
title: Gereken Değerleri Hesaplama
ms.date: 11/04/2016
helpviewer_keywords:
- helper functions, calculating necessary values
ms.assetid: 4f037d0f-881a-4a48-a9d2-9f8872dfccb7
ms.openlocfilehash: 92d8462be2db55dbc10375629b133d9286560878
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179349"
---
# <a name="calculating-necessary-values"></a>Gereken Değerleri Hesaplama

İki kritik bilgi parçası, gecikme Yardımcısı yordamıyla hesaplanmalıdır. Bu uçta, bu bilgileri hesaplamak için delayhlp. cpp içinde iki satır içi işlev vardır.

- Birincisi, geçerli içeri aktarmanın dizinini üç farklı tabloya (içeri aktarma adres tablosu (ıAT), bağlı içeri aktarma adresi tablosu (BIAT) ve ilişkisiz içeri aktarma adres tablosu (UıAT)) hesaplar.

- İkincisi geçerli bir ıAT içindeki içeri aktarma sayısını sayar.

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

[Yardımcı Işlevini anlama](understanding-the-helper-function.md)
