---
title: Derleyici Hatası C3645 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3645
dev_langs:
- C++
helpviewer_keywords:
- C3645
ms.assetid: 346da528-ae86-4cd0-9654-f41bee26ac0d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a711f37e3ab54de5e3cfad77b82fbd603edfaf6e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33263833"
---
# <a name="compiler-error-c3645"></a>Derleyici Hatası C3645
'function': __clrcall yerel koda derlenmiş işlevleri kullanılamaz  
  
 Bir işlevdeki bazı anahtar sözcükleri varlığını için yerel derlenecek işlevi neden olur.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3645 oluşturur.  
  
```  
// C3645.cpp  
// compile with: /clr /c  
#pragma unmanaged   
int __clrcall dog() {}   // C3645  
```