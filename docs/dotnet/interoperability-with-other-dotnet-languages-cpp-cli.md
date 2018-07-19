---
title: Diğer .NET dilleri ile birlikte çalışabilirlik (C + +/ CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- C++, indexers
- indexers, consuming C#
- as C# keyword [C++]
- is C# keyword [C++]
- lock statement
- lock C# keyword [C++]
ms.assetid: a5902cf8-a14d-4559-aefb-c178615d45bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 000009eca8150774150ab1e1d8f6d228aaf5c912
ms.sourcegitcommit: 27be37ae07ee7b657a54d23ed34438220d977fdc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/18/2018
ms.locfileid: "39110305"
---
# <a name="interoperability-with-other-net-languages-ccli"></a>Diğer .NET Dilleri ile Birlikte Çalışabilirlik (C++/CLI)
Bu bölümdeki konular, derlemeler gelen kullanan veya C# veya Visual Basic'te yazılmış işlevselliği sağlamak için Visual C++'ta oluşturma işlemi gösterilmektedir.  
  
## <a name="consume_indexer"></a> Bir C# dizin oluşturucusunu kullanma
Visual C++, dizin oluşturucular içermez. özellikleri dizine. Dizini oluşturulmuş özelliğe değilmiş gibi bir C# dizin oluşturucusunu kullanma için dizin oluşturucuyu erişin.  
  
 Dizin oluşturucular hakkında daha fazla bilgi için bkz:  
  
-   [Dizin Oluşturucular](/dotnet/csharp/programming-guide/indexers/index)  
  
### <a name="example"></a>Örnek  
 Aşağıdaki C# programı bir dizin oluşturucu tanımlar.  
  
```csharp  
// consume_cs_indexers.cs  
// compile with: /target:library  
using System;  
public class IndexerClass {  
   private int [] myArray = new int[100];   
   public int this [int index] {   // Indexer declaration  
      get {  
         // Check the index limits.  
         if (index < 0 || index >= 100)  
            return 0;  
         else  
            return myArray[index];  
      }  
      set {  
         if (!(index < 0 || index >= 100))  
            myArray[index] = value;  
      }  
   }  
}  
/*  
// code to consume the indexer  
public class MainClass {  
   public static void Main() {  
      IndexerClass b = new IndexerClass();  
  
      // Call indexer to initialize elements 3 and 5  
      b[3] = 256;  
      b[5] = 1024;  
      for (int i = 0 ; i <= 10 ; i++)   
         Console.WriteLine("Element #{0} = {1}", i, b[i]);  
   }  
}  
*/  
```  
  
### <a name="example"></a>Örnek  
 Bu Visual C++ programında, dizin oluşturucu tüketir.  
  
```cpp  
// consume_cs_indexers_2.cpp  
// compile with: /clr  
#using "consume_cs_indexers.dll"  
using namespace System;  
  
int main() {  
   IndexerClass ^ ic = gcnew IndexerClass;  
   ic->default[0] = 21;  
   for (int i = 0 ; i <= 10 ; i++)  
      Console::WriteLine("Element #{0} = {1}", i, ic->default[i]);  
}  
```  
  
```Output  
Element #0 = 21  
Element #1 = 0  
Element #2 = 0  
Element #3 = 0  
Element #4 = 0  
Element #5 = 0  
Element #6 = 0  
Element #7 = 0  
Element #8 = 0  
Element #9 = 0  
Element #10 = 0  
```  

## <a name="implement_isas"></a> Uygulama olduğunu ve as C# anahtar sözcüklerini
Bu konuda işlevselliğini uygulamak nasıl gösterilmektedir `is` ve `as` Visual C++'ta C# anahtar sözcükleri.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// CS_is_as.cpp  
// compile with: /clr  
using namespace System;  
  
interface class I {  
public:  
   void F();  
};  
  
ref struct C : public I {  
   virtual void F( void ) { }  
};  
  
template < class T, class U >   
Boolean isinst(U u) {  
   return dynamic_cast< T >(u) != nullptr;  
}  
  
int main() {  
   C ^ c = gcnew C();  
   I ^ i = safe_cast< I ^ >(c);   // is (maps to castclass in IL)  
   I ^ ii = dynamic_cast< I ^ >(c);   // as (maps to isinst in IL)  
  
   // simulate 'as':  
   Object ^ o = "f";  
   if ( isinst< String ^ >(o) )  
      Console::WriteLine("o is a string");  
}  
```  
  
```Output  
o is a string  
```  

## <a name="implement_locak"></a> ' % S'lock C# anahtar sözcüğünü uygulama
Bu konuda, C# uygulamak gösterilmektedir `lock` Visual c++ anahtar sözcüğü. 
  
 Ayrıca `lock` C++ Destek Kitaplığı'nda sınıfı. Bkz: [eşitleme (lock sınıfı)](../dotnet/synchronization-lock-class.md) daha fazla bilgi için.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// CS_lock_in_CPP.cpp  
// compile with: /clr  
using namespace System::Threading;  
ref class Lock {  
   Object^ m_pObject;  
public:  
   Lock( Object ^ pObject ) : m_pObject( pObject ) {  
      Monitor::Enter( m_pObject );  
   }  
   ~Lock() {  
      Monitor::Exit( m_pObject );  
   }  
};  
  
ref struct LockHelper {  
   void DoSomething();  
};  
  
void LockHelper::DoSomething() {  
   // Note: Reference type with stack allocation semantics to provide   
   // deterministic finalization  
  
   Lock lock( this );     
   // LockHelper instance is locked  
}  
  
int main()  
{  
   LockHelper lockHelper;  
   lockHelper.DoSomething();  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
