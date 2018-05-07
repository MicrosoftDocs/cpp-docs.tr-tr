---
title: Derleyici Uyarısı (düzey 1) C4383 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4383
dev_langs:
- C++
helpviewer_keywords:
- C4383
ms.assetid: 96c0e52d-874e-4b57-a154-0e49b6a00fae
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b78209cf4e3e320cca8b161a4e6c99eaca6d771c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4383"></a>Derleyici Uyarısı (düzey 1) C4383
'instance_dereference_operator': bir kullanıcı tanımlı 'işleci' işleci mevcut; bir tanıtıcı başvurusunun kaldırılmasının anlamı, değiştirebilirler işlenen hakkında açık olması için statik bir işlevi olarak işleci yazma  
  
 Bir yönetilen türü kullanıcı tanımlı örnek geçersiz kılma başvuru işlecinin eklediğinizde, tutamacın nesne döndürme özelliği tür başvuru işlecinin potansiyel olarak geçersiz kılın. Göz önünde bulundurun, kullanıcı tarafından tanımlanan statik yazma başvuru işleci.  
  
 Daha fazla bilgi için bkz: [işlemek nesne işleci (^)](../../windows/handle-to-object-operator-hat-cpp-component-extensions.md) ve [izleme başvurusu işleci](../../windows/tracking-reference-operator-cpp-component-extensions.md).  
  
 Ayrıca, bir örnek işleci diğer dil derleyicileri başvurulan meta veri aracılığıyla kullanılabilir değil. Daha fazla bilgi için bkz: [kullanıcı tanımlı işleçler (C + +/ CLI)](../../dotnet/user-defined-operators-cpp-cli.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4383 oluşturur.  
  
```  
// C4383.cpp  
// compile with: /clr /W1  
  
ref struct S {  
   int operator*() { return 0; }   // C4383  
};  
  
ref struct T {  
   static int operator*(T%) { return 0; }  
};   
  
int main() {  
   S s;  
   S^ pS = %s;  
  
   T t;  
   T^ pT = %t;  
   T% rT = *pT;  
}  
```