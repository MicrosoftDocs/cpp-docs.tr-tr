---
title: Derleyici Uyarısı (düzey 4) C4220 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4220
dev_langs:
- C++
helpviewer_keywords:
- C4220
ms.assetid: aba18868-825f-4763-9af6-3296406a80e4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f5a48bc836bbead8bc9004f797855fcc4c1baaf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4220"></a>Derleyici Uyarısı (düzey 4) C4220
Kalan parametreleri VarArgs eşleşir  
  
 Varsayılan Microsoft Uzantıları (/Ze) altında bir işlev işaretçisi benzer, ancak değişken, bağımsız değişkenlere sahip bir işlev işaretçisi eşleşir.  
  
## <a name="example"></a>Örnek  
  
```  
// C4220.c  
// compile with: /W4  
  
int ( *pFunc1) ( int a, ... );  
int ( *pFunc2) ( int a, int b);  
  
int main()  
{  
   if ( pFunc1 != pFunc2 ) {};  // C4220  
}  
```  
  
 Bu tür işaretçileri ANSI Uyumluluğu altında eşleşmiyor ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).