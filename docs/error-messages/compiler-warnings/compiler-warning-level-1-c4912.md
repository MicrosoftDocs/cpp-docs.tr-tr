---
title: Derleyici Uyarısı (düzey 1) C4912 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4912
dev_langs:
- C++
helpviewer_keywords:
- C4912
ms.assetid: ba1f1a66-8c20-4792-9ac8-43e49f729ae2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b40e4500554d04c39e4009aeef104e0d8eacb7c8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302204"
---
# <a name="compiler-warning-level-1-c4912"></a>Derleyici Uyarısı (düzey 1) C4912
'öznitelik': öznitelik iç içe geçmiş UDT davranışı tanımlı olmayan  
  
 İç içe geçmiş atama (typedef, UNION veya yapı olabilen kullanıcı tanımlı türü) için geçerli öznitelikleri yoksayılabilir.  
  
 Aşağıdaki kod, nasıl bu uyarı oluşturulacağını gösterir:  
  
```  
// C4912.cpp  
// compile with: /W1  
#include <windows.h>  
[emitidl, module(name="xx")];  
  
[object, uuid("00000000-0000-0000-0000-000000000002")]  
__interface IMy  
{  
};  
  
[coclass, default(IMy), appobject, uuid("00000000-0000-0000-0000-000000000001")]  
class CMy : public IMy  
{  
   [export, v1_enum] typedef enum myEnum { k3_1 = 1, k3_2 = 2 } myEnumv;   // C4912  
};  
int main()  
{  
}  
```