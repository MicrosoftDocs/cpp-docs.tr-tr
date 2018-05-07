---
title: Derleyici Uyarısı (düzey 1) C4067 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4067
dev_langs:
- C++
helpviewer_keywords:
- C4067
ms.assetid: 1d10353e-8cd5-4b01-9184-a06189b965a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4eccec985e6a9e652f18c6513542942351ff6efc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4067"></a>Derleyici Uyarısı (düzey 1) C4067
Beklenmeyen belirteçleri aşağıdaki önişlemci yönergesi - beklenen bir satır başı karakteri  
  
 Derleyici bulundu ve önişlemci yönergesi sonraki fazladan karakterler yoksayıldı. Bu uyarı yalnızca ANSI Uyumluluğu altında görünür ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).  
  
```  
// C4067a.cpp  
// compile with: /DX /Za /W1  
#pragma warning(default:4067)  
#if defined(X)  
#else  
#endif v   // C4067  
int main()  
{  
}  
```  
  
### <a name="to-resolve-this-warning-try-the-following"></a>Bu uyarıyı çözmek için aşağıdakileri deneyin:  
  
1.  İle derleme **/Ze**.  
  
2.  Yorum ayırıcıları kullanın:  
  
```  
// C4067b.cpp  
// compile with: /DX /Za /W1  
#if defined(X)  
#else  
#endif  
int main()  
{  
}  
```