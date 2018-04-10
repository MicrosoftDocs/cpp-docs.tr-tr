---
title: Derleyici Uyarısı (düzey 1) C4124 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C4124
dev_langs:
- C++
helpviewer_keywords:
- C4124
ms.assetid: c08c3a65-9584-47a1-a147-44f00c4b230e
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 38588fb242b5b4167984e15d101594d1b015ec86
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4124"></a>Derleyici Uyarısı (düzey 1) C4124
yığın denetlemesi ile birlikte __fastcall yetersiz olduğunu  
  
 `__fastcall` Anahtar sözcüğü yığın denetimi etkin kullanıldı.  
  
 `__fastcall` Kuralı daha hızlı kod oluşturur, ancak neden olan daha yavaş kod yığını denetleme. Kullanırken `__fastcall`, ile yığın denetimini devre dışı bırakma **check_stack** pragma veya /Gs.  
  
 Bu uyarı, yalnızca bu koşullar altında bildirilen ilk işlevi için görüntülenir.