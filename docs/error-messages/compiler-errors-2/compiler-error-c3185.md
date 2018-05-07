---
title: Derleyici Hatası C3185 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3185
dev_langs:
- C++
helpviewer_keywords:
- C3185
ms.assetid: 5bf96279-043c-4981-9d02-b4550071b192
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ce6eea7c9a40f9dd38bf6892995eaa52ac540de7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3185"></a>Derleyici Hatası C3185
'kullanılan TypeID' yönetilen veya WinRT türü 'type', 'işleci' bunun yerine kullanın  
  
 Uygulayamazsınız [TypeID](../../cpp/typeid-operator.md) yönetilen işlecine veya kullanın; türü WinRT [TypeID](../../windows/typeid-cpp-component-extensions.md) yerine.  
  
 Aşağıdaki örnek C3185 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C3185a.cpp  
// compile with: /clr  
ref class Base {};  
ref class Derived : public Base {};  
  
int main() {  
   Derived ^ pd = gcnew Derived;  
   Base ^pb = pd;  
   const type_info & t1 = typeid(pb);   // C3185  
   System::Type ^ MyType = Base::typeid;   // OK  
};  
```  
