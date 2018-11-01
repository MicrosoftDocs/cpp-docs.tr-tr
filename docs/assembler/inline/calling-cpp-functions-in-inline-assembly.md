---
title: Satır İçi Derlemede C++ İşlevlerini Çağırma
ms.date: 08/30/2018
helpviewer_keywords:
- functions [C++], calling in inline assembly
- function calls, C++ functions
- function calls, in inline assembly
- Visual C++, functions
- inline assembly, calling functions
- __asm keyword [C++], calling functions
ms.assetid: 1f0d1eb3-54cf-45d5-838d-958188616b38
ms.openlocfilehash: 666f7b2a59f0d48a14be54a439b6402f2a4d3128
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50458234"
---
# <a name="calling-c-functions-in-inline-assembly"></a>Satır İçi Derlemede C++ İşlevlerini Çağırma

**Microsoft'a özgü**

Bir `__asm` blok yalnızca aşırı yüklenmemiş genel C++ işlevleri çağırabilir. Aşırı yüklenmiş bir genel C++ işlev veya C++ üye işlevini çağırın, derleyici bir hata verir.

Bildirilen tüm işlevleri de çağırabilirsiniz **extern "C"** bağlantı. Böylece bir `__asm` bloğu içinde tüm standart üst bilgi dosyaları için kitaplık işlevleri bildirdiğinizden C Kitaplık işlevleri çağırmak için bir C++ programını **extern "C"** bağlantı.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Satır İçi Assembler](../../assembler/inline/inline-assembler.md)<br/>