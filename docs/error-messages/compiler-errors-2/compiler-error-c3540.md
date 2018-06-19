---
title: Derleyici Hatası C3540 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3540
dev_langs:
- C++
helpviewer_keywords:
- C3540
ms.assetid: 3c0c959c-e3b7-40eb-b922-ccac44bd9d85
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 27bae73d387612be41d8462bf0e5e0d82516ba1a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33256050"
---
# <a name="compiler-error-c3540"></a>Derleyici Hatası C3540
'type': sizeof 'auto' içeren bir türü için uygulanamaz  
  
 [Sizeof](../../cpp/sizeof-operator.md) işleci içerdiğinden belirtilen türe uygulanamaz `auto` tanımlayıcısı.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3540 verir.  
  
```  
// C3540.cpp  
// Compile with /Zc:auto  
int main() {  
    auto x = 123;  
    sizeof(x);    // OK  
    sizeof(auto); // C3540  
    return 0;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Auto anahtar sözcüğü](../../cpp/auto-keyword.md)   
 [/ZC:Auto (değişken türünü)](../../build/reference/zc-auto-deduce-variable-type.md)   
 [sizeof İşleci](../../cpp/sizeof-operator.md)