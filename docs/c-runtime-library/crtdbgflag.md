---
description: 'Hakkında daha fazla bilgi edinin: _crtDbgFlag'
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
ms.openlocfilehash: ef3c72b89ea9e5e557a567af9a9c52c8e85370ce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97246777"
---
# <a name="_crtdbgflag"></a>_crtDbgFlag

**_CrtDbgFlag** bayrağı, yığının hata ayıklama sürümündeki bellek ayırmalarının nasıl izleneceğini, doğrulanacağını, raporlandığını ve döküldiğini denetleyen beş bitlik alandan oluşur. Bayrağın bit alanları [_CrtSetDbgFlag](../c-runtime-library/reference/crtsetdbgflag.md) işlevi kullanılarak ayarlanır. Bu bayrak ve kendi bit alanları Crtdbg. h içinde gösterilir. Bu bayrak yalnızca uygulamada [_DEBUG](../c-runtime-library/debug.md) bayrağı tanımlandığında kullanılabilir.

Bu bayrağı diğer hata ayıklama işlevleriyle birlikte kullanma hakkında daha fazla bilgi için bkz. [yığın durum raporlama işlevleri](/visualstudio/debugger/crt-debug-heap-details).

## <a name="see-also"></a>Ayrıca bkz.

[Denetim bayrakları](../c-runtime-library/control-flags.md)
