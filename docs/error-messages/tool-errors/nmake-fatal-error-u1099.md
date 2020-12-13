---
description: 'Hakkında daha fazla bilgi edinin: NMAKE önemli hatası U1099'
title: NMAKE Önemli Hatası U1099
ms.date: 11/04/2016
f1_keywords:
- U1099
helpviewer_keywords:
- U1099
ms.assetid: 6688a805-43e6-4247-a2d0-14be082f0b13
ms.openlocfilehash: 8044010cf967e4fe27b2235968022023d66ae1c3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345322"
---
# <a name="nmake-fatal-error-u1099"></a>NMAKE Önemli Hatası U1099

yığın taşması

İşlenmekte olan derleme görevleri dosyası NMAKE içindeki geçerli yığın ayırması için çok karmaşıktı. NMAKE, 0x3000 (12K) ayırmayı içerir.

NMAKE 'in yığın ayırmayı artırmak için, [editbin/Stack](../../build/reference/stack.md) yardımcı programını daha büyük bir yığın seçeneğiyle çalıştırın:

**Editbin/STACK: Reserve NMAKE.EXE**

Burada *ayrılan* , NMAKE içindeki geçerli yığın ayırmadan daha büyük bir sayıdır.
