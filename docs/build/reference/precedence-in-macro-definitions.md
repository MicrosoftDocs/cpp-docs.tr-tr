---
title: Makro Tanımlarında Öncelik
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, precedence in macro definitions
- macros, precedence
ms.assetid: 0c13182d-83cb-4cbd-af2d-f4c916b62aeb
ms.openlocfilehash: 38a653a9f460beae81f9f88ea457870d30f25339
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57823556"
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
