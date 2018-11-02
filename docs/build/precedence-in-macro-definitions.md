---
title: Makro Tanımlarında Öncelik
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, precedence in macro definitions
- macros, precedence
ms.assetid: 0c13182d-83cb-4cbd-af2d-f4c916b62aeb
ms.openlocfilehash: 8829b3cdbc7b2324ef3d118f8ca45dd2a1621e7e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50619091"
---
# <a name="precedence-in-macro-definitions"></a>Makro Tanımlarında Öncelik

NMAKE bir makro birden fazla tanım var, en yüksek öncelikli tanımı kullanır. Aşağıdaki liste, yüksekten en düşüğe öncelik sırasını gösterir:

1. Komut satırında tanımlanan bir makrosu

1. Makro bir derleme görevleri dosyasında tanımlanan veya dosyasını dahil edin

1. Devralınan bir ortam değişkeni makrosu

1. Tools.ini dosyasında tanımlanan bir makrosu

1. Önceden tanımlanmış bir makro gibi [CC](../build/command-macros-and-options-macros.md) ve [AS](../build/command-macros-and-options-macros.md)

Aynı ada sahip derleme görevleri dosyası makroları geçersiz kılmak için ortam değişkenlerini devralınan makroları neden /E kullanın. Kullanım **! UNDEF** bir komut satırı geçersiz kılmak için.

## <a name="see-also"></a>Ayrıca Bkz.

[NMAKE Makrosu Tanımlama](../build/defining-an-nmake-macro.md)