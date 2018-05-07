---
title: Derleyici Hatası C3293 | Microsoft Docs
ms.custom: ''
ms.date: 07/21/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3293
dev_langs:
- C++
helpviewer_keywords:
- C3293
ms.assetid: b772cf98-52e0-4e24-be23-1f5d87d999ac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b195a91825b0f20445b29e330f67810329584db7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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