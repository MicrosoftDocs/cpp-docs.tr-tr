---
description: 'Daha fazla bilgi edinin: makro tanımlarında öncelik'
title: Makro Tanımlarında Öncelik
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, precedence in macro definitions
- macros, precedence
ms.assetid: 0c13182d-83cb-4cbd-af2d-f4c916b62aeb
ms.openlocfilehash: 1738c4ba77f330103395278a6daae169b04fae4c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225901"
---
# <a name="precedence-in-macro-definitions"></a>Makro Tanımlarında Öncelik

Bir makroda birden çok tanım varsa NMAKE en yüksek öncelikli tanımı kullanır. Aşağıdaki listede, en yüksekten en düşüğe göre öncelik sırası gösterilmektedir:

1. Komut satırında tanımlanan makro

1. Derleme görevleri dosyası veya içerme dosyasında tanımlanan makro

1. Devralınan ortam değişkeni makrosu

1. Tools.ini dosyasında tanımlanan makro

1. [CC](command-macros-and-options-macros.md) ve [as](command-macros-and-options-macros.md) gibi önceden tanımlanmış bir makro

Ortam değişkenlerinden devralınan makroların aynı ada sahip derleme görevleri dosyası makrolarını geçersiz kılmasını sağlamak için/E kullanın. Kullanın **!** Komut satırını geçersiz kılmak IÇIN UNDEF.

## <a name="see-also"></a>Ayrıca bkz.

[NMAKE makrosu tanımlama](defining-an-nmake-macro.md)
