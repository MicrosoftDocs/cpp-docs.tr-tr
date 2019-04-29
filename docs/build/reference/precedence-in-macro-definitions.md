---
title: Makro Tanımlarında Öncelik
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, precedence in macro definitions
- macros, precedence
ms.assetid: 0c13182d-83cb-4cbd-af2d-f4c916b62aeb
ms.openlocfilehash: 38a653a9f460beae81f9f88ea457870d30f25339
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320168"
---
# <a name="precedence-in-macro-definitions"></a>Makro Tanımlarında Öncelik

NMAKE bir makro birden fazla tanım var, en yüksek öncelikli tanımı kullanır. Aşağıdaki liste, yüksekten en düşüğe öncelik sırasını gösterir:

1. Komut satırında tanımlanan bir makrosu

1. Makro bir derleme görevleri dosyasında tanımlanan veya dosyasını dahil edin

1. Devralınan bir ortam değişkeni makrosu

1. Tools.ini dosyasında tanımlanan bir makrosu

1. Önceden tanımlanmış bir makro gibi [CC](command-macros-and-options-macros.md) ve [AS](command-macros-and-options-macros.md)

Aynı ada sahip derleme görevleri dosyası makroları geçersiz kılmak için ortam değişkenlerini devralınan makroları neden /E kullanın. Kullanım **! UNDEF** bir komut satırı geçersiz kılmak için.

## <a name="see-also"></a>Ayrıca bkz.

[NMAKE Makrosu Tanımlama](defining-an-nmake-macro.md)
