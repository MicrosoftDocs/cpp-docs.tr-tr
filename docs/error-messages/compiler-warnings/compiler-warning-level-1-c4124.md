---
title: Derleyici Uyarısı (düzey 1) C4124
ms.date: 11/04/2016
f1_keywords:
- C4124
helpviewer_keywords:
- C4124
ms.assetid: c08c3a65-9584-47a1-a147-44f00c4b230e
ms.openlocfilehash: 6408185c99a54d5411fa5b1058cd5ec09d3326d6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80176318"
---
# <a name="compiler-warning-level-1-c4124"></a>Derleyici Uyarısı (düzey 1) C4124

yığın denetimi ile __fastcall verimsiz

`__fastcall` anahtar sözcüğü yığın denetimi etkin olarak kullanıldı.

`__fastcall` kuralı daha hızlı kod üretir, ancak yığın denetimi daha yavaş koda neden olur. `__fastcall`kullanırken, **check_stack** pragma veya/Gile yığın denetimini devre dışı bırakın.

Bu uyarı yalnızca bu koşullarda belirtilen ilk işlev için verilir.
