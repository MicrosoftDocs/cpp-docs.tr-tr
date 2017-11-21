---
title: "Nasıl yapılır: C# dizin oluşturucusunu kullanma (C + +/ CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- C++, indexers
- indexers, consuming C#
ms.assetid: 5a11850c-a1a2-4a0a-b95e-f6dc5a87f439
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1e7938022bfe2ba1a8f97420a217590de659d9e1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-consume-a-c-indexer-ccli"></a>Nasıl yapılır: C# Dizin Oluşturucusunu Kullanma (C++/CLI)
Visual C++ oluşturucusu içermez; Özellikler dizine. Bir dizin oluşturulmuş özellik değilmiş gibi bir C# dizin oluşturucusunu kullanma, dizin oluşturucu erişim sağlar.  
  
 Dizin oluşturucular hakkında daha fazla bilgi için bkz:  
  
-   [Dizin oluşturucular](https://msdn.microsoft.com/library/6x16t2tx.aspx)  
  
## <a name="example"></a>Örnek  
 Aşağıdaki C# programı bir dizin oluşturucu tanımlar.  
  
```  
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
  
## <a name="example"></a>Örnek  
 Bu Visual C++ programı dizin oluşturucuyu tüketir.  
  
```  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Diğer .NET dilleri ile birlikte çalışabilirlik (C + +/ CLI)](../dotnet/interoperability-with-other-dotnet-languages-cpp-cli.md)