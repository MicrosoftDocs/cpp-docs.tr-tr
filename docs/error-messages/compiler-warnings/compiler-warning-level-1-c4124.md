---
title: Derleyici Uyarısı (düzey 1) C4124
ms.date: 11/04/2016
f1_keywords:
- C4124
helpviewer_keywords:
- C4124
ms.assetid: c08c3a65-9584-47a1-a147-44f00c4b230e
ms.openlocfilehash: 59860bef108a3cd3e8bbbc6ff0790e17dbdaa0d4
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214496"
---
# <a name="compiler-warning-level-1-c4124"></a>Derleyici Uyarısı (düzey 1) C4124

yığın denetimi ile __fastcall verimsiz

**`__fastcall`** Anahtar sözcüğü yığın denetimi etkin olarak kullanıldı.

**`__fastcall`** Kural daha hızlı kod üretir, ancak yığın denetimi daha yavaş koda neden olur. Kullanırken **`__fastcall`** , **check_stack** pragma veya/Gile yığın denetimini devre dışı bırakın.

Bu uyarı yalnızca bu koşullarda belirtilen ilk işlev için verilir.
