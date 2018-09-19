---
title: NMAKE önemli hatası U1099 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1099
dev_langs:
- C++
helpviewer_keywords:
- U1099
ms.assetid: 6688a805-43e6-4247-a2d0-14be082f0b13
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f3ef75a1435d8c922087fcdd21d1941961bc82cd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46113389"
---
# <a name="nmake-fatal-error-u1099"></a>NMAKE Önemli Hatası U1099

yığın taşması

NMAKE içindeki geçerli yığın ayırma için çok karmaşık işlenmekte olan derleme görevleri dosyası. NMAKE 0x3000 (12 K) ayırma vardır.

NMAKE'ün yığın ayırma artırmak için çalıştırma [editbin /stack](../../build/reference/stack.md) yardımcı programı ile daha büyük bir yığın seçeneği:

**edıtbın /STACK:reserve NMAKE. EXE**

Burada *rezerve* geçerli yığın ayırma NMAKE içindeki daha büyük bir sayıdır.