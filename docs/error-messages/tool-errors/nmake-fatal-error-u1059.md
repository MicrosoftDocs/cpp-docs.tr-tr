---
title: NMAKE Önemli Hatası U1059
ms.date: 08/27/2018
f1_keywords:
- U1059
helpviewer_keywords:
- U1059
ms.assetid: b21d9198-9c63-40d0-b589-80e17294ce24
ms.openlocfilehash: 3c148bf2feb7ba12686e00b29f5bf90cb9f2f2d7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50645035"
---
# <a name="nmake-fatal-error-u1059"></a>NMAKE Önemli Hatası U1059

> sözdizimi hatası: '}' bağımlıda eksik

Bağımlı bir arama yolunu yanlış şekilde belirtildi. Ya da bir alan yolu veya kapanış ayracı var (**}**) atlandı.

Bağımlı bir dizin belirtimi için sözdizimi

> **{** *dizinleri* **} bağımlı**

Burada *dizinleri* bir veya daha fazla yol, noktalı virgülle ayırarak belirtir (**;**). Boşluk olmayan izin verilir.

Kısmını veya tümünü bir arama yolu bir makro tarafından değiştirilirse, makro genişletme içinde boşluk olmadan var olduğundan emin olun.