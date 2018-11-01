---
title: _crtDbgFlag
ms.date: 11/04/2016
f1_keywords:
- _crtDbgFlag
- crtDbgFlag
helpviewer_keywords:
- memory allocation, tracking flag
- crtDbgFlag constant
- _crtDbgFlag constant
- debug heap, tracking memory on
- debug heap, control flags
- enable memory allocation tracking flag
- memory, tracking on the debug heap
ms.assetid: 9e7adb47-8ab9-4e19-81d5-e2f237979973
ms.openlocfilehash: 5abb0418b5ffb1f95bf7b362f621f99f411094d6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50435301"
---
# <a name="crtdbgflag"></a>_crtDbgFlag

**_CrtDbgFlag** bayrağı nasıl hata ayıklama sürümü yığın bellek ayırmalarında izlenen, doğrulanan, bildirilen yazılan ve denetleyen beş bit alanlarını içerir. Bit alanları bayrağı kullanılarak ayarlanan [_CrtSetDbgFlag](../c-runtime-library/reference/crtsetdbgflag.md) işlevi. Bu bayrak ve bit alanları Crtdbg.h bildirilir. Bu bayrağı yalnızca kullanılabilir [_DEBUG](../c-runtime-library/debug.md) bayrağı uygulamada tanımlanmış.

Bu bayrak diğer hata ayıklama işlevleri ile birlikte kullanma hakkında daha fazla bilgi için bkz. [yığın durumu raporlama işlevleri](/visualstudio/debugger/crt-debug-heap-details).

## <a name="see-also"></a>Ayrıca Bkz.

[Denetim Bayrakları](../c-runtime-library/control-flags.md)