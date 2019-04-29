---
title: NMAKE Önemli Hatası U1059
ms.date: 08/27/2018
f1_keywords:
- U1059
helpviewer_keywords:
- U1059
ms.assetid: b21d9198-9c63-40d0-b589-80e17294ce24
ms.openlocfilehash: 3c148bf2feb7ba12686e00b29f5bf90cb9f2f2d7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62367297"
---
# <a name="nmake-fatal-error-u1059"></a>NMAKE Önemli Hatası U1059

> sözdizimi hatası: '}' bağımlıda eksik

Bağımlı bir arama yolunu yanlış şekilde belirtildi. Ya da bir alan yolu veya kapanış ayracı var (**}**) atlandı.

Bağımlı bir dizin belirtimi için sözdizimi

> **{** *dizinleri* **} bağımlı**

Burada *dizinleri* bir veya daha fazla yol, noktalı virgülle ayırarak belirtir (**;**). Boşluk olmayan izin verilir.

Kısmını veya tümünü bir arama yolu bir makro tarafından değiştirilirse, makro genişletme içinde boşluk olmadan var olduğundan emin olun.