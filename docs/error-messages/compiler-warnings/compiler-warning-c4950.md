---
title: Derleyici Uyarısı C4950 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4950
dev_langs:
- C++
helpviewer_keywords:
- C4950
ms.assetid: 50226a5c-c664-4d09-ac59-e9e874ca244f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 55221cc233c74e612dd4a521641be90a6dbf9314
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33272031"
---
# <a name="compiler-warning-c4950"></a>Derleyici Uyarısı C4950
'type_or_member': kullanımdan kaldırılmış olarak işaretlenmiş  
  
Bir üye ya da türü ile kullanımdan kaldırılmış olarak işaretlenmiş <xref:System.ObsoleteAttribute> özniteliği.  
  
C4950 her zaman hata olarak verilir. Kullanarak bu uyarıyı devre dışı bırakabilir [uyarı](../../preprocessor/warning.md) pragma yönergesi veya [/wd](../../build/reference/compiler-option-warning-level.md) derleyici seçeneği.  
  
## <a name="example"></a>Örnek  
Aşağıdaki örnek C4950 oluşturur:  
  
```cpp  
// C4950.cpp  
// compile with: /clr  
using namespace System;  
  
// Any reference to Func3 should generate an error with message  
[System::ObsoleteAttribute("Will be removed in next version", true)]  
Int32 Func3(Int32 a, Int32 b) {  
   return (a + b);  
}  
  
int main() {  
   Int32 MyInt3 = ::Func3(2, 2);   // C4950  
}  
```