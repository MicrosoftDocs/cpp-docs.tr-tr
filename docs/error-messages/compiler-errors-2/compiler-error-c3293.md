---
title: Derleyici Hatası C3293
ms.date: 07/21/2017
f1_keywords:
- C3293
helpviewer_keywords:
- C3293
ms.assetid: b772cf98-52e0-4e24-be23-1f5d87d999ac
ms.openlocfilehash: 84d539722474d5f5dfffe1f6fe121bb7349ba131
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62222593"
---
# <a name="compiler-error-c3293"></a>Derleyici Hatası C3293

'erişimcisi': 'type' sınıfının varsayılan özelliğine (Dizin Oluşturucu) erişmek için 'default' kullanın

Dizini oluşturulmuş özelliğe yanlış erişildi.  Bkz: [nasıl yapılır: İçindeki özellikleri kullanın C++/CLI](../../dotnet/how-to-use-properties-in-cpp-cli.md) daha fazla bilgi için.

**Visual Studio 2017 ve üzeri**: Visual Studio 2015 ve önceki sürümlerinde, bazı durumlarda, derleyici varsayılan bir özellik bir varsayılan dizin oluşturucu misidentified. Bir özelliğe erişmek için "varsayılan" tanımlayıcısını kullanarak sorunu çözmek mümkündü. Varsayılan olarak bir anahtar sözcük C ++ 11'de kullanıma sunulmuştur sonra geçici sorunlu hale geldi. Bu nedenle, Visual Studio 2017'de gerekli geçici hatalar düzeltilmiştir ve "varsayılan" bir sınıfının varsayılan özelliğine erişmek için kullanıldığında, derleyici artık bir hata oluşturur.

## <a name="example"></a>Örnek

Aşağıdaki örnek, Visual Studio 2015'te ve daha önce C3293 oluşturur.

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