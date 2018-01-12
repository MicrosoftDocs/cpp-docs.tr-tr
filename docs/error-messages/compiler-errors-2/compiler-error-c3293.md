---
title: "Derleyici Hatası C3293 | Microsoft Docs"
ms.custom: 
ms.date: 07/21/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3293
dev_langs: C++
helpviewer_keywords: C3293
ms.assetid: b772cf98-52e0-4e24-be23-1f5d87d999ac
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ccf6bd08b1ca540fcdf46d18631e0ab11c7fe4f6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3293"></a>Derleyici Hatası C3293
'erişimcisi': 'default' sınıfı 'type' için varsayılan özelliği (Dizin Oluşturucu) erişmek için kullanın  
  
 Dizinli bir özelliği yanlış erişildi.  Bkz: [nasıl yapılır: kullanım özellikleri C + +/ CLI](../../dotnet/how-to-use-properties-in-cpp-cli.md) daha fazla bilgi için.  

 **Visual Studio 2017 ve sonraki**: Visual Studio 2015 ve daha önceki bir varsayılan dizin oluşturucu olarak varsayılan bir özellik bazı durumlarda derleyici misidentified. Bir özelliğe erişmek için "varsayılan" tanımlayıcıyı kullanarak sorunu çözmek mümkündü. Varsayılan olarak bir anahtar sözcük C ++ 11 tanıtılan sonra geçici sorunlu hale geldi. Bu nedenle, Visual Studio 2017 içinde geçici çözüm gerekli hatalar düzeltilmiştir ve "varsayılan" bir sınıf için varsayılan özelliğine erişmek için kullanıldığında, derleyici şimdi hata başlatır.
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek Visual Studio 2015 ve daha önce C3293 oluşturur.  
  
```  
// C3293.cpp  
// compile with: /clr /c  
using namespace System;  
ref class IndexerClass {  
public:  
   // default indexer  
   property int default[int] {  
      int get(int index) { return 0; }  
      void set(int index, int value) {}  
   }  
};  
  
int main() {  
   IndexerClass ^ ic = gcnew IndexerClass;  
   ic->Item[0] = 21;   // C3293 in VS2015 OK in VS2017
   ic->default[0] = 21;   // OK in VS2015 and earlier
  
   String ^s = "Hello";  
   wchar_t wc = s->Chars[0];   // C3293 in VS2015 OK in VS2017
   wchar_t wc2 = s->default[0];   // OK in VS2015 and earlier  
   Console::WriteLine(wc2);  
}  
```