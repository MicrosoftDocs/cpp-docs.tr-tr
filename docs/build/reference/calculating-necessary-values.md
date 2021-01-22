---
description: 'Daha fazla bilgi edinin: gecikme yüklemesi için gerekli değerleri hesaplama'
title: Gecikme yüklemesi için gerekli değerleri hesapla
ms.date: 01/19/2021
helpviewer_keywords:
- helper functions, calculating necessary values
ms.openlocfilehash: ae5e0c15b5b13f12fd90c1378a1e449516b55f43
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667443"
---
# <a name="calculate-necessary-values-for-delay-loading"></a>Gecikme yüklemesi için gerekli değerleri hesapla

Gecikme Yükleme Yardımcısı yordamının iki kritik bilgi parçasını hesaplaması gerekir. Yardım için, *`delayhlp.cpp`* Bu bilgileri hesaplamak üzere ' de iki satır içi işlev vardır.

- Birincisi, `IndexFromPImgThunkData` geçerli içeri aktarmanın dizinini üç farklı tabloya (içeri aktarma adres tablosu (ıAT), bağlı içeri aktarma adresi tablosu (BIAT) ve ilişkisiz içeri aktarma adres tablosu (UıAT)) hesaplar.

- İkincisi, `CountOfImports` geçerli BIR ıAT içindeki içeri aktarma sayısını sayar.

```C
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

[Yardımcı işlevini anlama](understanding-the-helper-function.md)
