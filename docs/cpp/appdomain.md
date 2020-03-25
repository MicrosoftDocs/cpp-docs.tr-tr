---
title: appdomain
ms.date: 11/04/2016
f1_keywords:
- appdomain_cpp
helpviewer_keywords:
- appdomain __declspec keyword
- __declspec keyword [C++], appdomain
ms.assetid: 29d843cb-cb6b-4d1b-a48d-d928a877234d
ms.openlocfilehash: 7ac74e8774204b316712a15975f7af3fb8835a9e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80181492"
---
# <a name="appdomain"></a>appdomain

Yönetilen uygulamanızın her bir uygulama etki alanının belirli bir genel değişkenin veya statik üye değişkeninin kendi kopyasına sahip olması gerektiğini belirtir. Daha fazla bilgi için bkz. [uygulama etki alanları ve görsel C++ ](../dotnet/application-domains-and-visual-cpp.md) .

Her uygulama etki alanının kendi AppDomain bağımsız değişkeninin kendi kopyası vardır. Bir uygulama etki alanına bir derleme yüklendiğinde bir AppDomain değişkeninin Oluşturucusu yürütülür ve uygulama etki alanı kaldırıldığında yıkıcı yürütülür.

Ortak dil çalışma zamanındaki bir işlem içindeki tüm uygulama etki alanlarının genel bir değişkeni paylaşmasına istiyorsanız `__declspec(process)` değiştiricisini kullanın. `__declspec(process)`, [/clr](../build/reference/clr-common-language-runtime-compilation.md)altında varsayılan olarak etkindir. **/Clr: Pure** ve **/clr: Safe** derleyici seçenekleri Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ' de desteklenmez.

`__declspec(appdomain)` yalnızca **/clr** derleyici seçeneklerinden biri kullanıldığında geçerlidir. Yalnızca bir genel değişken, statik üye değişkeni veya statik bir yerel değişken `__declspec(appdomain)`ile işaretlenebilir. Bu davranışa her zaman sahip olduklarından, yönetilen türlerin statik üyelerine `__declspec(appdomain)` uygulamak bir hatadır.

`__declspec(appdomain)` kullanmak, [Iş parçacığı yerel depolaması (TLS)](../parallel/thread-local-storage-tls.md)ile benzerdir. İş parçacıklarının, uygulama etki alanları olarak kendi depolama alanları vardır. `__declspec(appdomain)` kullanmak, genel değişkenin bu uygulama için oluşturulan her uygulama etki alanında kendi depolama alanı olmasını sağlar.

İşlem başına ve AppDomain değişkenleri başına kullanımını karıştırma sınırlamaları vardır; daha fazla bilgi için [işleme](../cpp/process.md) bakın.

Örneğin, program başlangıcında, tüm işlem başına değişkenler başlatılır, sonra tüm AppDomain değişkenleri başlatılır. Bu nedenle, işlem başına değişken başlatıldığında, uygulama başına etki alanı değişkeninin değerine bağlı olamaz. AppDomain başına ve işlem değişkenleri başına kullanımını (atamayı) karıştırmak hatalı bir uygulamadır.

Belirli bir uygulama etki alanında bir işlevi çağırma hakkında daha fazla bilgi için bkz. [Call_in_appdomain işlevi](../dotnet/call-in-appdomain-function.md).

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

[__declspec](../cpp/declspec.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
