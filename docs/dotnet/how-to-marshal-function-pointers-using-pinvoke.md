---
description: 'Daha fazla bilgi edinin: nasıl yapılır: PInvoke kullanarak Işlev Işaretçilerini sıralama'
title: 'Nasıl yapılır: PInvoke Kullanarak İşlev İşaretçilerini Sıralama'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- data marshaling [C++], callbacks and delegates
- interop [C++], callbacks and delegates
- platform invoke [C++], callbacks and delegates
- marshaling [C++], callbacks and delegates
ms.assetid: dcf396fd-a91d-49c0-ab0b-1ea160668a89
ms.openlocfilehash: bfe3f669cf023ed914bdccb3ae15ccafefbb49c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302588"
---
# <a name="how-to-marshal-function-pointers-using-pinvoke"></a>Nasıl yapılır: PInvoke Kullanarak İşlev İşaretçilerini Sıralama

Bu konu, yönetilen temsilcilerin .NET Framework P/Invoke özellikleri kullanılarak yönetilmeyen işlevlerle birlikte çalışırken işlev işaretçilerinin yerine nasıl kullanılabileceğini açıklar. Ancak, Visual C++ programcıların C++ birlikte çalışma özelliklerini kullanması önerilir, çünkü P/Invoke çok az sayıda derleme zamanı hatası raporlama sağladığından, tür kullanımı güvenli değildir ve uygulamak sıkıcı olabilir. Yönetilmeyen API bir DLL olarak paketlenmişse ve kaynak kodu kullanılabilir değilse, P/Invoke tek seçenektir. Aksi takdirde, aşağıdaki konulara bakın:

- [C++ birlikte çalışabilirliği kullanma (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)

- [Nasıl yapılır: C++ birlikte çalışabilirliği kullanarak geri çağırmaları ve temsilcileri sıralama](../dotnet/how-to-marshal-callbacks-and-delegates-by-using-cpp-interop.md)

Bağımsız değişken olarak işlev işaretçileri alan yönetilmeyen API 'Ler, yönetilen koddan yerel işlev işaretçisi yerine yönetilen bir temsilci ile çağrılabilir. Derleyici, bir işlev işaretçisi olarak yönetilmeyen işlevlere temsilciyi otomatik olarak sıralar ve gerekli yönetilen/yönetilmeyen geçiş kodunu ekler.

## <a name="example"></a>Örnek

Aşağıdaki kod, yönetilmeyen ve yönetilen bir modülden oluşur. Yönetilmeyen modül, bir işlev işaretçisini kabul eden TakesCallback adlı bir işlevi tanımlayan bir DLL 'dir. Bu adres, işlevi yürütmek için kullanılır.

Yönetilen modül, yerel koda bir işlev işaretçisi olarak sıralanmış bir temsilciyi tanımlar ve <xref:System.Runtime.InteropServices.DllImportAttribute> Yerel TakesCallback işlevini yönetilen koda göstermek için özniteliğini kullanır. Main işlevinde, temsilcinin bir örneği oluşturulur ve TakesCallback işlevine geçirilir. Program çıktısı, bu işlevin yerel TakesCallback işlevi tarafından yürütüldüğünü gösterir.

Yönetilen işlev, yerel işlev yürütülürken .NET Framework çöp toplamanın temsilciyi yeniden konumlandırmasını engellemek için, yönetilen temsilcinin çöp toplamayı bastırır.

```cpp
// TraditionalDll5.cpp
// compile with: /LD /EHsc
#include <iostream>
#define TRADITIONALDLL_EXPORTS
#ifdef TRADITIONALDLL_EXPORTS
#define TRADITIONALDLL_API __declspec(dllexport)
#else
#define TRADITIONALDLL_API __declspec(dllimport)
#endif

extern "C" {
   /* Declare an unmanaged function type that takes two int arguments
      Note the use of __stdcall for compatibility with managed code */
   typedef int (__stdcall *CALLBACK)(int);
   TRADITIONALDLL_API int TakesCallback(CALLBACK fp, int);
}

int TakesCallback(CALLBACK fp, int n) {
   printf_s("[unmanaged] got callback address, calling it...\n");
   return fp(n);
}
```

```cpp
// MarshalDelegate.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

public delegate int GetTheAnswerDelegate(int);
public value struct TraditionalDLL {
   [DllImport("TraditionalDLL5.dll")]
   static public int TakesCallback(GetTheAnswerDelegate^ pfn, int n);
};

int GetNumber(int n) {
   Console::WriteLine("[managed] callback!");
   static int x = 0;
   ++x;
   return x + n;
}

int main() {
   GetTheAnswerDelegate^ fp = gcnew GetTheAnswerDelegate(GetNumber);
   pin_ptr<GetTheAnswerDelegate^> pp = &fp;
   Console::WriteLine("[managed] sending delegate as callback...");

   int answer = TraditionalDLL::TakesCallback(fp, 42);
}
```

Geleneksel #include yönergesini kullanarak, DLL 'nin hiçbir kısmının yönetilen koda sunulmadığını unutmayın. Aslında, DLL 'ye yalnızca çalışma zamanında erişilir. bu nedenle, ile içeri aktarılan işlevlerle ilgili sorunlar <xref:System.Runtime.InteropServices.DllImportAttribute> derleme zamanında algılanmaz.

## <a name="see-also"></a>Ayrıca bkz.

[C++ ' ta açık PInvoke kullanma (DllImport özniteliği)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
