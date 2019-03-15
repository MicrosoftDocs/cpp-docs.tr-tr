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
ms.openlocfilehash: 0f4905473dd6914547ad6ac129d34e438992c2af
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57824122"
---
# <a name="null-and-undefined-macros"></a>Boş ve Tanımlanmamış Makrolar

Null dizeler için null ve tanımlanmamış makrolar genişletin, ancak boş bir dize olarak tanımlanmış bir makro ifadeleri önişlemde tanımlı olarak kabul edilir. Makro boş bir dize tanımlamak için herhangi bir karakter boşluk veya sekme sonra hariç eşittir (=) bir komut satırı veya komut dosyası ve boş bir dize veya tanımı çift tırnak işaretleri içine alın belirtin (""). Makro tanımını kaldırmaya kullanın **! UNDEF.** Daha fazla bilgi için [derleme görevleri dosyası önişleme yönergeleri](makefile-preprocessing-directives.md).

## <a name="see-also"></a>Ayrıca bkz.

[NMAKE Makrosu Tanımlama](defining-an-nmake-macro.md)
