---
title: 'Nasıl yapılır: PInvoke kullanarak dizeleri sıralama | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interop [C++], strings
- marshaling [C++], strings
- data marshaling [C++], strings
- platform invoke [C++], strings
ms.assetid: bcc75733-7337-4d9b-b1e9-b95a98256088
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1a377e7074e72693a1a63e392c64a6d60c5995b7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-marshal-strings-using-pinvoke"></a>Nasıl yapılır: PInvoke Kullanarak Dizeleri Sıralama
Bu konuda, C stilinde dizeleri CLR dizesi kullanılarak çağrılabilir kabul nasıl yerel işlevler açıklanmaktadır .NET Framework Platform çağırma desteğini kullanan System::String yazın. P/Invoke çok az derleme zamanı hata raporlama, tür kullanımı uyumlu değildir ve uygulaması can sıkıcı olabilir sağladığından visual C++ programcıları (uygunsa) C++ birlikte çalışabilirlik özellikleri kullanmaları önerilir. Yönetilmeyen API DLL olarak paketlenir ve kaynak kod kullanılabilir değilse, P/Invoke tek seçenektir ancak Aksi takdirde bkz [C++ Çalışabilirliği kullanarak (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md).  
  
 Yönetilen ve yönetilmeyen dizeleri farklı düzenlenir bellekte, bu nedenle dizelerden yönetilmeyen işlevlerle yönetilen gerektirir <xref:System.Runtime.InteropServices.MarshalAsAttribute> dize verilerini hazırlamak için gerekli dönüştürme düzeneklerini eklemek için görevlendirin özniteliği düzgün ve güvenli bir şekilde.  
  
 Yalnızca iç veri türlerini kullanan işlevler gibi ile <xref:System.Runtime.InteropServices.DllImportAttribute> C tarzı dizeler, işleyici olarak alıp bu giriş noktaları tanımlamak yerine dizeleri--geçirme için yerel işlevler halinde, ancak--yönetilen giriş noktalarını bildirmek için kullanılan <xref:System.String> türü Bunun yerine kullanılabilir. Bu, derleyicinin gerekli dönüştürmeyi gerçekleştiren kod eklemesini ister. Her işlev bağımsız değişkeni olarak bir dize alır yönetilmeyen bir işleve <xref:System.Runtime.InteropServices.MarshalAsAttribute> öznitelik dize nesnesi C stili dize olarak yerel işlevi sıralanması gerektiğini belirtmek için kullanılmalıdır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod, bir yönetilmeyen ve yönetilen bir modül oluşur. Yönetilmeyen modül char * biçiminde C türü ANSI dizesini kabul eder TakesAString adlı bir işlev tanımlayan bir DLL'dir. Yönetilen modül TakesAString işlevini alır, ancak bir char yerine yönetilen System.String olarak tanımlayan bir komut satırı uygulamasıdır\*. <xref:System.Runtime.InteropServices.MarshalAsAttribute> Özniteliği yönetilen dize TakesAString çağrıldığında nasıl gerektiğini belirtmek için kullanılır.  
  
```  
// TraditionalDll2.cpp  
// compile with: /LD /EHsc  
#include <windows.h>  
#include <stdio.h>  
#include <iostream>  
  
using namespace std;  
  
#define TRADITIONALDLL_EXPORTS  
#ifdef TRADITIONALDLL_EXPORTS  
#define TRADITIONALDLL_API __declspec(dllexport)  
#else  
#define TRADITIONALDLL_API __declspec(dllimport)  
#endif  
  
extern "C" {  
   TRADITIONALDLL_API void TakesAString(char*);  
}  
  
void TakesAString(char* p) {  
   printf_s("[unmanaged] %s\n", p);  
}  
```  
  
```  
// MarshalString.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
value struct TraditionalDLL  
{  
   [DllImport("TraditionalDLL2.dll")]  
      static public void   
      TakesAString([MarshalAs(UnmanagedType::LPStr)]String^);  
};  
  
int main() {  
   String^ s = gcnew String("sample string");  
    Console::WriteLine("[managed] passing managed string to unmanaged function...");  
   TraditionalDLL::TakesAString(s);  
   Console::WriteLine("[managed] {0}", s);  
}  
```  
  
 Bu teknik bir kopyasını dizeye yerel işlev tarafından yapılan değişiklikleri dize yönetilen kopyasında yansıtılmaz şekilde yönetilmeyen yığında oluşturulması için dizesinin neden olur.  
  
 Geleneksel aracılığıyla yönetilen koda DLL'nin hiçbir bölümünün maruz Not #include yönergesi. İle içeri aktarılan işlevlerle sorunlar aslında, DLL yalnızca çalışma zamanında erişilir, böylece `DllImport` derleme zamanında algılanmaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++'ta Açık PInvoke Kullanma (DllImport Özniteliği)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)