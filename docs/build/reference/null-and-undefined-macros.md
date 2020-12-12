---
description: 'Hakkında daha fazla bilgi edinin: null ve tanımsız makrolar'
title: Boş ve Tanımlanmamış Makrolar
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, undefined macros
- Null macros in NMAKE
- macros, null and undefined
- undefined macros and NMAKE
- NMAKE program, null macros
ms.assetid: 1db4611a-1755-4328-b00f-d35365af8b6c
ms.openlocfilehash: 639afda727f1ebb1f4d7d602ed7cf01d6c914a33
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209730"
---
# <a name="null-and-undefined-macros"></a>Boş ve Tanımlanmamış Makrolar

Null ve tanımsız makrolar, null dizelere genişletilir, ancak bir null dize olarak tanımlanan bir makro, ön işleme ifadelerinde tanımlanmış olarak kabul edilir. Bir makroyu null dize olarak tanımlamak için, bir komut satırı veya komut dosyasında eşittir işaretinden (=) sonra boşluk veya sekme dışında bir karakter belirtmeyin ve null dize veya tanımı çift tırnak işaretleri ("") içine alın. Bir makroyu tanımlamak için kullanın **! UNDEF.** Daha fazla bilgi için bkz. [makefile ön Işleme yönergeleri](makefile-preprocessing-directives.md).

## <a name="see-also"></a>Ayrıca bkz.

[NMAKE makrosu tanımlama](defining-an-nmake-macro.md)
