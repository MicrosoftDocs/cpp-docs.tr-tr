---
title: "Derleyici Uyarısı (düzey 1) C4124 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4124
dev_langs: C++
helpviewer_keywords: C4124
ms.assetid: c08c3a65-9584-47a1-a147-44f00c4b230e
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3de13cb50444530fc0917330771b693f60a7e5f5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4124"></a>Derleyici Uyarısı (düzey 1) C4124
yığın denetlemesi ile birlikte __fastcall yetersiz olduğunu  
  
 `__fastcall` Anahtar sözcüğü yığın denetimi etkin kullanıldı.  
  
 `__fastcall` Kuralı daha hızlı kod oluşturur, ancak neden olan daha yavaş kod yığını denetleme. Kullanırken `__fastcall`, ile yığın denetimini devre dışı bırakma **check_stack** pragma veya /Gs.  
  
 Bu uyarı, yalnızca bu koşullar altında bildirilen ilk işlevi için görüntülenir.