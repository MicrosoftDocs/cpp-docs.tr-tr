---
title: NMAKE Önemli Hatası U1099
ms.date: 11/04/2016
f1_keywords:
- U1099
helpviewer_keywords:
- U1099
ms.assetid: 6688a805-43e6-4247-a2d0-14be082f0b13
ms.openlocfilehash: 395f25d8d27bc5e9b6132c87390c8c3bc19b6cc4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62298249"
---
# <a name="nmake-fatal-error-u1099"></a>NMAKE Önemli Hatası U1099

yığın taşması

NMAKE içindeki geçerli yığın ayırma için çok karmaşık işlenmekte olan derleme görevleri dosyası. NMAKE 0x3000 (12 K) ayırma vardır.

NMAKE'ün yığın ayırma artırmak için çalıştırma [editbin /stack](../../build/reference/stack.md) yardımcı programı ile daha büyük bir yığın seçeneği:

**edıtbın /STACK:reserve NMAKE. EXE**

Burada *rezerve* geçerli yığın ayırma NMAKE içindeki daha büyük bir sayıdır.