---
title: Derleyici Hatası C3104 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3104
dev_langs:
- C++
helpviewer_keywords:
- C3104
ms.assetid: b5648d47-e5d3-4b45-a3c0-f46e04eae731
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ded5185e3f87ce7f1b5a4a7015ce3c4476c949b5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33246473"
---
# <a name="compiler-error-c3104"></a>Derleyici Hatası C3104
Geçersiz öznitelik bağımsız değişkeni  
  
 Bir öznitelik için geçersiz bağımsız değişken belirtilmiş.  
  
 Bkz: [öznitelik parametre türleri](../../windows/attribute-parameter-types-cpp-component-extensions.md) daha fazla bilgi için.  
  
 Bu hata için Visual C++ 2005 yapıldığı derleyici uyumluluğu iş sonucunda oluşturulabilir: yönetilen diziler için özel öznitelikler geçirirken, dizi türü artık toplu başlatma listeden anlaşılabilen. Derleyici şimdi başlatıcı listesi yanı sıra dizi türünü belirtmenizi gerektirir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3104 oluşturur.  
  
```  
// C3104a.cpp  
// compile with: /clr /c  
using namespace System;  
  
[AttributeUsage(AttributeTargets::Class)]  
public ref struct ABC : public Attribute {  
   ABC(array<int>^){}  
   array<double> ^ param;  
};  
  
[ABC( {1,2,3}, param = {2.71, 3.14})]   // C3104  
// try the following line instead  
// [ABC( gcnew array<int> {1,2,3}, param = gcnew array<double>{2.71, 3.14})]   
ref struct AStruct{};  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3104 oluşturur.  
  
```  
// C3104b.cpp  
// compile with: /clr /c  
// C3104 expected  
using namespace System;  
  
int func() {  
   return 0;   
}  
  
[attribute(All)]  
ref class A {  
public:   
   A(int) {}  
};  
  
// Delete the following 2 lines to resolve.  
[A(func())]  
ref class B {};  
  
// OK  
[A(0)]  
ref class B {};  
```  
