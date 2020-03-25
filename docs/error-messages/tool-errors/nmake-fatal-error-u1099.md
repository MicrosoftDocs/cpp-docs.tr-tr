---
title: NMAKE Önemli Hatası U1099
ms.date: 11/04/2016
f1_keywords:
- U1099
helpviewer_keywords:
- U1099
ms.assetid: 6688a805-43e6-4247-a2d0-14be082f0b13
ms.openlocfilehash: c963180059a48d9aa0b09103df1ed54f82b8a2f1
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80193401"
---
# <a name="nmake-fatal-error-u1099"></a>NMAKE Önemli Hatası U1099

yığın taşması

İşlenmekte olan derleme görevleri dosyası NMAKE içindeki geçerli yığın ayırması için çok karmaşıktı. NMAKE, 0x3000 (12K) ayırmayı içerir.

NMAKE 'in yığın ayırmayı artırmak için, [editbin/Stack](../../build/reference/stack.md) yardımcı programını daha büyük bir yığın seçeneğiyle çalıştırın:

**Editbin/STACK: yedek NMAKE. EXE**

Burada *ayrılan* , NMAKE içindeki geçerli yığın ayırmadan daha büyük bir sayıdır.
