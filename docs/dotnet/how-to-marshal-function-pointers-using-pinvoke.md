---
title: "Nasıl yapılır: PInvoke kullanarak işlev işaretçilerini sıralama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- data marshaling [C++], callbacks and delegates
- interop [C++], callbacks and delegates
- platform invoke [C++], callbacks and delegates
- marshaling [C++], callbacks and delegates
ms.assetid: dcf396fd-a91d-49c0-ab0b-1ea160668a89
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: cf7f23ea9337b499d4ec80b19e3104074429cc71
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-marshal-function-pointers-using-pinvoke"></a>Nasıl yapılır: PInvoke Kullanarak İşlev İşaretçilerini Sıralama
Bu konuda nasıl yönetilen temsilciler açıklanmaktadır P/Invoke .NET Framework özelliklerini kullanarak işlevleri ile birlikte yönetilmeyen işlev işaretçileri yerine kullanılabilir. Ancak, P/Invoke çok az derleme zamanı hata raporlama, tür kullanımı uyumlu değildir ve uygulaması can sıkıcı olabilir sağladığından Visual C++ programcıları (uygunsa) C++ birlikte çalışabilirlik özellikleri kullanmaları önerilir. Yönetilmeyen API DLL olarak paketlenir ve kaynak kodu kullanılabilir değilse, P/Invoke tek seçenektir. Aksi takdirde, aşağıdaki konulara bakın:  
  
-   [C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)  
  
-   [Nasıl yapılır: C++ Birlikte Çalışmayı Kullanarak Geri Çağrıları ve Temsilcileri Sıralama](../dotnet/how-to-marshal-callbacks-and-delegates-by-using-cpp-interop.md)  
  
 Bağımsız değişkenler yerel işlev işaretçisi yerine yönetilen bir temsilci ile yönetilen koddan çağrılabilir gibi işlev işaretçilerini ele yönetilmeyen API'ler. Derleyici otomatik olarak yönetilmeyen işlevlerle temsilci bir işlev işaretçisi olarak sıralar ve gerekli yönetilen ve yönetilmeyen geçiş kodunu ekler.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod, bir yönetilmeyen ve yönetilen bir modül oluşur. Yönetilmeyen modül bir işlev işaretçisi kabul TakesCallback adında bir işlevi tanımlayan bir DLL'dir. Bu adres işlevi yürütmek için kullanılır.  
  
 Yönetilen modül bir işlev işaretçisi olarak yerel kod için sıralanmış ve kullandığı bir temsilci tanımlar <xref:System.Runtime.InteropServices.DllImportAttribute> yerel TakesCallback işlevini yönetilen koda kullanıma sunmak için öznitelik. Main işlevi temsilci örneği oluşturulur ve TakesCallback işlevine geçirilir. Program çıktısı, bu işlev yerel TakesCallback işlevi tarafından yürütülen gösterir.  
  
 Çöp toplama yerel işlev yürütürken temsilci yerini değiştirme alanından .NET Framework atık toplama önlemek yönetilen temsilci için Yönetilen işlev göstermez.  
  
 / CLR, ancak/CLR ile yönetilen modül derlenmiş: pure de çalışır. **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı.  
  
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
  
 DLL hiçbir bölümünün geleneksel kullanarak yönetilen kod açıktır Not #include yönergesi. İle içeri aktarılan işlevlerle sorunlar aslında, DLL yalnızca çalışma zamanında erişilir, böylece <xref:System.Runtime.InteropServices.DllImportAttribute> derleme zamanında algılanmaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++'ta Açık PInvoke Kullanma (DllImport Özniteliği)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)