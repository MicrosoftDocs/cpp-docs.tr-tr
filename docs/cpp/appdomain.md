---
title: AppDomain | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- appdomain_cpp
dev_langs:
- C++
helpviewer_keywords:
- appdomain __declspec keyword
- __declspec keyword [C++], appdomain
ms.assetid: 29d843cb-cb6b-4d1b-a48d-d928a877234d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 52b371d0dedc03c3f14ede1472221077d081ae8f
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402308"
---
# <a name="appdomain"></a>appdomain

Her uygulama etki alanı, yönetilen uygulamanızın bir belirli genel değişken veya statik üye değişkeni kendine ait kopyasını olması gerektiğini belirtir. Bkz: [uygulama etki alanları ve Visual C++](../dotnet/application-domains-and-visual-cpp.md) daha fazla bilgi için.

Her uygulama etki alanı, kendi başına appdomain değişken kopyasına sahip olur. Appdomain değişkeninin bir oluşturucu, bir derleme bir uygulama etki alanına yüklenir ve uygulama etki alanı kaldırıldığında yıkıcı yürütülür yürütülür.

Genel değişken paylaşmak için ortak dil çalışma zamanı bir işlemdeki tüm uygulama etki alanları istiyorsanız kullanın `__declspec(process)` değiştiricisi. `__declspec(process)` Varsayılan olarak etkin olan [/CLR](../build/reference/clr-common-language-runtime-compilation.md). **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor.

`__declspec(appdomain)` yalnızca geçerli olduğunda birini **/CLR** derleyici seçenekleri kullanılır. Genel bir değişkenin, statik üye değişkeninin veya statik bir yerel değişken ile işaretlenebilir `__declspec(appdomain)`. Uygulamak için bir hata olduğunu `__declspec(appdomain)` statik üyeleri için her zaman bu davranışı olduğundan yönetilen türleri.

Kullanarak `__declspec(appdomain)` kullanmaya benzer [iş parçacığı yerel depolaması (TLS)](../parallel/thread-local-storage-tls.md). Uygulama etki alanları gibi iş parçacığı kendi depolama sahip. Kullanarak `__declspec(appdomain)` genel değişkeni, bu uygulama için oluşturulan her uygulama etki alanında kendi depolama sahip olmasını sağlar.

Appdomain değişkenleri ve işlem başına kullanımını karıştırma sınırlama vardır; bkz: [işlem](../cpp/process.md) daha fazla bilgi için.

Örneğin, program başlangıç, tüm işlem içi değişkenler başlatılır ve ardından tüm appdomain başına değişkenleri başlatılır. Bu nedenle bir işlem içi değişken başlatılır, herhangi bir uygulama başına etki alanı değişkeninin değerine bağımlı olamaz. Kullanımı (atama) ve işleme değişkenleri uygulama etki alanı başına karıştırmak için hatalı bir uygulamadır.

Belirli uygulama etki alanında bir işlevi çağırmak nasıl daha fazla bilgi için bkz: [call_in_appdomain işlevi](../dotnet/call-in-appdomain-function.md).

## <a name="example"></a>Örnek

```cpp
// declspec_appdomain.cpp
// compile with: /clr
#include <stdio.h>
using namespace System;

class CGlobal {
public:
   CGlobal(bool bProcess) {
      Counter = 10;
      m_bProcess = bProcess;
      Console::WriteLine("__declspec({0}) CGlobal::CGlobal constructor", m_bProcess ? (String^)"process" : (String^)"appdomain");
   }

   ~CGlobal() {
      Console::WriteLine("__declspec({0}) CGlobal::~CGlobal destructor", m_bProcess ? (String^)"process" : (String^)"appdomain");
   }

   int Counter;

private:
   bool m_bProcess;
};

__declspec(process) CGlobal process_global = CGlobal(true);
__declspec(appdomain) CGlobal appdomain_global = CGlobal(false);

value class Functions {
public:
   static void change() {
      ++appdomain_global.Counter;
   }

   static void display() {
      Console::WriteLine("process_global value in appdomain '{0}': {1}",
         AppDomain::CurrentDomain->FriendlyName,
         process_global.Counter);

      Console::WriteLine("appdomain_global value in appdomain '{0}': {1}",
         AppDomain::CurrentDomain->FriendlyName,
         appdomain_global.Counter);
   }
};

int main() {
   AppDomain^ defaultDomain = AppDomain::CurrentDomain;
   AppDomain^ domain = AppDomain::CreateDomain("Domain 1");
   AppDomain^ domain2 = AppDomain::CreateDomain("Domain 2");
   CrossAppDomainDelegate^ changeDelegate = gcnew CrossAppDomainDelegate(&Functions::change);
   CrossAppDomainDelegate^ displayDelegate = gcnew CrossAppDomainDelegate(&Functions::display);

   // Print the initial values of appdomain_global in all appdomains.
   Console::WriteLine("Initial value");
   defaultDomain->DoCallBack(displayDelegate);
   domain->DoCallBack(displayDelegate);
   domain2->DoCallBack(displayDelegate);

   // Changing the value of appdomain_global in the domain and domain2
   // appdomain_global value in "default" appdomain remain unchanged
   process_global.Counter = 20;
   domain->DoCallBack(changeDelegate);
   domain2->DoCallBack(changeDelegate);
   domain2->DoCallBack(changeDelegate);

   // Print values again
   Console::WriteLine("Changed value");
   defaultDomain->DoCallBack(displayDelegate);
   domain->DoCallBack(displayDelegate);
   domain2->DoCallBack(displayDelegate);

   AppDomain::Unload(domain);
   AppDomain::Unload(domain2);
}
```

```Output
__declspec(process) CGlobal::CGlobal constructor
__declspec(appdomain) CGlobal::CGlobal constructor
Initial value
process_global value in appdomain 'declspec_appdomain.exe': 10
appdomain_global value in appdomain 'declspec_appdomain.exe': 10
__declspec(appdomain) CGlobal::CGlobal constructor
process_global value in appdomain 'Domain 1': 10
appdomain_global value in appdomain 'Domain 1': 10
__declspec(appdomain) CGlobal::CGlobal constructor
process_global value in appdomain 'Domain 2': 10
appdomain_global value in appdomain 'Domain 2': 10
Changed value
process_global value in appdomain 'declspec_appdomain.exe': 20
appdomain_global value in appdomain 'declspec_appdomain.exe': 10
process_global value in appdomain 'Domain 1': 20
appdomain_global value in appdomain 'Domain 1': 11
process_global value in appdomain 'Domain 2': 20
appdomain_global value in appdomain 'Domain 2': 12
__declspec(appdomain) CGlobal::~CGlobal destructor
__declspec(appdomain) CGlobal::~CGlobal destructor
__declspec(appdomain) CGlobal::~CGlobal destructor
__declspec(process) CGlobal::~CGlobal destructor
```

## <a name="see-also"></a>Ayrıca bkz.
[__declspec](../cpp/declspec.md)  
[Anahtar Sözcükler](../cpp/keywords-cpp.md)  