---
title: 'Nasıl yapılır: PInvoke kullanarak işlev işaretçilerini sıralama hazırlama'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- data marshaling [C++], callbacks and delegates
- interop [C++], callbacks and delegates
- platform invoke [C++], callbacks and delegates
- marshaling [C++], callbacks and delegates
ms.assetid: dcf396fd-a91d-49c0-ab0b-1ea160668a89
ms.openlocfilehash: 031bda0f93d6a95aa3c774553aefca0647d0518c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400571"
---
# <a name="how-to-marshal-function-pointers-using-pinvoke"></a>Nasıl yapılır: PInvoke kullanarak işlev işaretçilerini sıralama hazırlama

Bu konu açıklar nasıl yönetilen temsilciler .NET Framework P/Invoke özellikleri kullanarak işlevleri ile birlikte yönetilmeyen işlev işaretçileri yerine kullanılabilir. Ancak, çok az derleme zamanı hata raporlama, tür açısından güvenli değildir ve uygulamak can sıkıcı olabilir, P/Invoke sağlar çünkü Visual C++ programcıları (uygun olduğunda) C++ birlikte çalışabilirlik özellikleri kullanmaları önerilir. Yönetilmeyen API'ın bir DLL olarak paketlenmesi ve kaynak kodu kullanılabilir değilse, P/Invoke tek seçenektir. Aksi takdirde, aşağıdaki konulara bakın:

- [C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)

- [Nasıl yapılır: C++ Birlikte Çalışmayı Kullanarak Geri Çağrıları ve Temsilcileri Hazırlama](../dotnet/how-to-marshal-callbacks-and-delegates-by-using-cpp-interop.md)

Bağımsız değişkenler, yerel işlev işaretçisi yerine yönetilen bir temsilci ile yönetilen koddan çağrılabilir gibi işlevleri işaretçiler yönetilmeyen API'ler. Derleyici, otomatik olarak yönetilmeyen işlevleri için temsilci işlevi işaretçisi olarak sıralar ve gerekli yönetilen veya yönetilmeyen bir geçiş kodu ekler.

## <a name="example"></a>Örnek

Aşağıdaki kod, yönetilmeyen ve yönetilen bir modül oluşur. Yönetilmeyen bir işlev işaretçisi kabul eden TakesCallback adında bir işlevi tanımlayan bir DLL modülüdür. Bu adres işlevi yürütme için kullanılır.

Yönetilen modül kullanır ve yerel koda bir işlev işaretçisi olarak sıralanmış bir temsilci tanımlar <xref:System.Runtime.InteropServices.DllImportAttribute> yönetilen koda yerel TakesCallback işlevi kullanıma sunmak için özniteliği. Main işlevi, temsilci örneği oluşturulur ve TakesCallback işlevine geçirilir. Bu işlev yerel TakesCallback işlevi tarafından yürütülen üzere program çıktısını gösterir.

Yönetilen işlev çöp toplama işlemi için yerel işlevde yürütürken gelen temsilci yeniden konumlandırma çöp toplama .NET Framework önlemek yönetilen temsilci bastırır.

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

DLL hiçbir kısmı geleneksel kullanarak yönetilen kod için kullanıma sunulduğunu unutmayın #include yönergesi. Aslında, ile içeri aktarılan işlevlere sahip sorunlar için DLL yalnızca çalışma zamanında erişilir <xref:System.Runtime.InteropServices.DllImportAttribute> derleme zamanında algılanmaz.

## <a name="see-also"></a>Ayrıca bkz.

[C++'ta Açık PInvoke Kullanma (DllImport Özniteliği)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
