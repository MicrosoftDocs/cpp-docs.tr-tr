---
title: Boş ve Tanımlanmamış Makrolar
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, undefined macros
- Null macros in NMAKE
- macros, null and undefined
- undefined macros and NMAKE
- NMAKE program, null macros
ms.assetid: 1db4611a-1755-4328-b00f-d35365af8b6c
ms.openlocfilehash: f6f294234f7244b65137742e1fe8abaa37a676a5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50498923"
---
# <a name="null-and-undefined-macros"></a>Boş ve Tanımlanmamış Makrolar

Null dizeler için null ve tanımlanmamış makrolar genişletin, ancak boş bir dize olarak tanımlanmış bir makro ifadeleri önişlemde tanımlı olarak kabul edilir. Makro boş bir dize tanımlamak için herhangi bir karakter boşluk veya sekme sonra hariç eşittir (=) bir komut satırı veya komut dosyası ve boş bir dize veya tanımı çift tırnak işaretleri içine alın belirtin (""). Makro tanımını kaldırmaya kullanın **! UNDEF.** Daha fazla bilgi için [derleme görevleri dosyası önişleme yönergeleri](../build/makefile-preprocessing-directives.md).

## <a name="see-also"></a>Ayrıca Bkz.

[NMAKE Makrosu Tanımlama](../build/defining-an-nmake-macro.md)