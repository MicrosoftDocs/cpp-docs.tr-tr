---
title: _crtDbgFlag | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _crtDbgFlag
- crtDbgFlag
dev_langs:
- C++
helpviewer_keywords:
- memory allocation, tracking flag
- crtDbgFlag constant
- _crtDbgFlag constant
- debug heap, tracking memory on
- debug heap, control flags
- enable memory allocation tracking flag
- memory, tracking on the debug heap
ms.assetid: 9e7adb47-8ab9-4e19-81d5-e2f237979973
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d9900d42a5bae3c7a613028a7ae4ffe4bdc0333
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46044918"
---
# <a name="crtdbgflag"></a>_crtDbgFlag

**_CrtDbgFlag** bayrağı nasıl hata ayıklama sürümü yığın bellek ayırmalarında izlenen, doğrulanan, bildirilen yazılan ve denetleyen beş bit alanlarını içerir. Bit alanları bayrağı kullanılarak ayarlanan [_CrtSetDbgFlag](../c-runtime-library/reference/crtsetdbgflag.md) işlevi. Bu bayrak ve bit alanları Crtdbg.h bildirilir. Bu bayrağı yalnızca kullanılabilir [_DEBUG](../c-runtime-library/debug.md) bayrağı uygulamada tanımlanmış.

Bu bayrak diğer hata ayıklama işlevleri ile birlikte kullanma hakkında daha fazla bilgi için bkz. [yığın durumu raporlama işlevleri](/visualstudio/debugger/crt-debug-heap-details).

## <a name="see-also"></a>Ayrıca Bkz.

[Denetim Bayrakları](../c-runtime-library/control-flags.md)