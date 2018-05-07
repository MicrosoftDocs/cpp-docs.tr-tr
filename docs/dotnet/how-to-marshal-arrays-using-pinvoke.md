---
title: 'Nasıl yapılır: PInvoke kullanarak dizileri sıralama | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- marshaling [C++], arrays
- platform invoke [C++], arrays
- interop [C++], arrays
- data marshaling [C++], arrays
ms.assetid: a1237797-a2da-4df4-984a-6333ed3af406
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 03e3cf184828c33c63c5252344eb0041640729cb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-marshal-arrays-using-pinvoke"></a>Nasıl yapılır: PInvoke Kullanarak Dizileri Sıralama
Bu konuda, C stilinde dizeleri CLR dize türü kullanılarak çağrılabilir kabul nasıl yerel işlevler açıklanmaktadır <xref:System.String> desteği .NET Framework Platform çağırma kullanma. P/Invoke çok az derleme zamanı hata raporlama, tür kullanımı uyumlu değildir ve uygulaması can sıkıcı olabilir sağladığından visual C++ programcıları (uygunsa) C++ birlikte çalışabilirlik özellikleri kullanmaları önerilir. Yönetilmeyen API DLL olarak paketlenir ve kaynak kodu kullanılabilir değilse, P/Invoke tek seçenektir (Aksi takdirde bkz [C++ Çalışabilirliği kullanarak (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)).  
  
## <a name="example"></a>Örnek  
 Yerel ve yönetilen diziler bellekte farklı şekilde düzenlenmiştir olduğundan, bunları başarıyla yönetilen ve yönetilmeyen sınırından geçirme dönüştürme veya hazırlama gerektirir. Bu konu, yönetilen koddan nasıl basit (taşınabilir) öğeleri dizisi yerel işlevler geçirilebileceği gösterilmektedir.  
  
 Yönetilen ve yönetilmeyen verileri genel olarak, hazırlama true olarak <xref:System.Runtime.InteropServices.DllImportAttribute> özniteliği kullanılacak her yerel işlevi için bir yönetilen giriş noktası oluşturmak için kullanılır. Dizileri bağımsız değişkenler almayan işlevleri durumunda <xref:System.Runtime.InteropServices.MarshalAsAttribute> özniteliği de verileri nasıl sıralanacağını derleyiciye belirtmek için kullanılmalıdır. Aşağıdaki örnekte, <xref:System.Runtime.InteropServices.UnmanagedType> numaralandırma yönetilen dizi C stilinde bir dizi olarak sıralanmış olduğunu belirtmek için kullanılır.  
  
 Aşağıdaki kod, bir yönetilmeyen ve yönetilen bir modül oluşur. Yönetilmeyen modül dizisi kabul eden bir işlev tanımlayan bir DLL'dir. İkinci modül bu işlevi alır ancak yönetilen bir dizi açısından tanımlar ve kullanan bir yönetilen komut satırı uygulamasıdır <xref:System.Runtime.InteropServices.MarshalAsAttribute> dizi çağrıldığında yerel bir dizeye dönüştürülür olduğunu belirtmek için özniteliği.  
  
 Yönetilen modül/CLR ile derlenir.  
  
```cpp  
// TraditionalDll4.cpp  
// compile with: /LD /EHsc  
#include <iostream>  
  
#define TRADITIONALDLL_EXPORTS  
#ifdef TRADITIONALDLL_EXPORTS  
#define TRADITIONALDLL_API __declspec(dllexport)  
#else  
#define TRADITIONALDLL_API __declspec(dllimport)  
#endif  
  
extern "C" {  
   TRADITIONALDLL_API void TakesAnArray(int len, int[]);  
}  
  
void TakesAnArray(int len, int a[]) {  
   printf_s("[unmanaged]\n");  
   for (int i=0; i<len; i++)  
      printf("%d = %d\n", i, a[i]);  
}  
```  
  
```cpp  
// MarshalBlitArray.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
value struct TraditionalDLL {  
   [DllImport("TraditionalDLL4.dll")]  
   static public void TakesAnArray(  
   int len,[MarshalAs(UnmanagedType::LPArray)]array<int>^);  
};  
  
int main() {  
   array<int>^ b = gcnew array<int>(3);  
   b[0] = 11;  
   b[1] = 33;  
   b[2] = 55;  
   TraditionalDLL::TakesAnArray(3, b);  
  
   Console::WriteLine("[managed]");  
   for (int i=0; i<3; i++)  
      Console::WriteLine("{0} = {1}", i, b[i]);  
}  
```  
  
 Geleneksel aracılığıyla yönetilen koda DLL'nin hiçbir bölümünün maruz Not #include yönergesi. DLL yalnızca çalışma zamanında erişilir, aslında, işlevlerle ile içeri aktarılan sorunlar <xref:System.Runtime.InteropServices.DllImportAttribute> derleme zamanında algılanmaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++'ta Açık PInvoke Kullanma (DllImport Özniteliği)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)