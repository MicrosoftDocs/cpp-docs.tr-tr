---
title: Makro tanımlarında öncelik | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, precedence in macro definitions
- macros, precedence
ms.assetid: 0c13182d-83cb-4cbd-af2d-f4c916b62aeb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 21a3d8873fd1fee61afec865181bab27305bebfd
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45722221"
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