---
title: "Derleyici Hatası C3225 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3225
dev_langs: C++
helpviewer_keywords: C3225
ms.assetid: f5f66973-256e-4298-ac46-c87819cbde34
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4cf62ba7b0c3b95f22c27172546ccdd253ed9279
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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