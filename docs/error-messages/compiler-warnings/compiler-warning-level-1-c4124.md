---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4124'
title: Derleyici Uyarısı (düzey 1) C4124
ms.date: 11/04/2016
f1_keywords:
- C4124
helpviewer_keywords:
- C4124
ms.assetid: c08c3a65-9584-47a1-a147-44f00c4b230e
ms.openlocfilehash: 97fe65f8513f656d85059714ae598ffad9f7a49c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267397"
---
# <a name="compiler-warning-level-1-c4124"></a>Derleyici Uyarısı (düzey 1) C4124

yığın denetimi ile __fastcall verimsiz

**`__fastcall`** Anahtar sözcüğü yığın denetimi etkin olarak kullanıldı.

**`__fastcall`** Kural daha hızlı kod üretir, ancak yığın denetimi daha yavaş koda neden olur. Kullanırken **`__fastcall`** , **check_stack** pragma veya/Gile yığın denetimini devre dışı bırakın.

Bu uyarı yalnızca bu koşullarda belirtilen ilk işlev için verilir.
