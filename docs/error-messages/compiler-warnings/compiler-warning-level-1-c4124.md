---
title: Derleyici Uyarısı (düzey 1) C4124 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4124
dev_langs:
- C++
helpviewer_keywords:
- C4124
ms.assetid: c08c3a65-9584-47a1-a147-44f00c4b230e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: accd58c123bcd74e54176eed5eb974c3df33dbab
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4124"></a>Derleyici Uyarısı (düzey 1) C4124
yığın denetlemesi ile birlikte __fastcall yetersiz olduğunu  
  
 `__fastcall` Anahtar sözcüğü yığın denetimi etkin kullanıldı.  
  
 `__fastcall` Kuralı daha hızlı kod oluşturur, ancak neden olan daha yavaş kod yığını denetleme. Kullanırken `__fastcall`, ile yığın denetimini devre dışı bırakma **check_stack** pragma veya /Gs.  
  
 Bu uyarı, yalnızca bu koşullar altında bildirilen ilk işlevi için görüntülenir.