---
title: Derleyici Hatası C3225 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3225
dev_langs:
- C++
helpviewer_keywords:
- C3225
ms.assetid: f5f66973-256e-4298-ac46-c87819cbde34
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f9f6691ddacf6b3c1347b9fd4cac134433741a6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33250585"
---
# <a name="compiler-error-c3225"></a>Derleyici Hatası C3225
genel tür bağımsız değişkeni 'arg' için 'type' olamaz, bir değer türü veya türünü işlemek gerekir  
  
 Genel tür bağımsız değişkeni doğru türde değildi.  
  
 Daha fazla bilgi için bkz: [genel türler](../../windows/generics-cpp-component-extensions.md).  
  
## <a name="example"></a>Örnek  
 Yerel tür ile genel tür örneği oluşturulamıyor. Aşağıdaki örnek C3225 oluşturur.  
  
```  
// C3225.cpp  
// compile with: /clr  
class A {};  
  
ref class B {};  
  
generic <class T>  
ref class C {};  
  
int main() {  
   C<A>^ c = gcnew C<A>;   // C3225  
   C<B^>^ c2 = gcnew C<B^>;   // OK  
}  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, C# kullanarak bir bileşen oluşturur. Genel tür yalnızca bir değer türüyle oluşturulmasını kısıtlamayı belirtir dikkat edin.  
  
```  
// C3225_b.cs  
// compile with: /target:library  
// a C# program  
public class MyList<T> where T: struct {}  
```  
  
## <a name="example"></a>Örnek  
 Bu örnek C# tüketir-bileşen yazılan ve MyList yalnızca olabilir kısıtlamayı ihlal ediyor dışında bir değer türüyle örneği <xref:System.Nullable>. Aşağıdaki örnek C3225 oluşturur.  
  
```  
// C3225_c.cpp  
// compile with: /clr  
#using "C3225_b.dll"  
ref class A {};  
value class B {};  
int main() {  
   MyList<A> x;   // C3225  
   MyList<B> y;   // OK  
}  
```