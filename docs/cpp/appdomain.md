---
title: AppDomain | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: appdomain_cpp
dev_langs: C++
helpviewer_keywords:
- appdomain __declspec keyword
- __declspec keyword [C++], appdomain
ms.assetid: 29d843cb-cb6b-4d1b-a48d-d928a877234d
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: eb8ebb1c13627f794032437b4c814fb933833b5d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="appdomain"></a>appdomain
Her uygulama etki alanı, yönetilen uygulamanızın belirli genel değişkeni ya da statik üye değişkeni kopyasını sahip olması gerektiğini belirtir. Bkz: [uygulama etki alanları ve Visual C++](../dotnet/application-domains-and-visual-cpp.md) daha fazla bilgi için.  
  
 Her uygulama etki alanı başına appdomain değişkeni kopyasını sahiptir. Bir appdomain değişkenin bir oluşturucu bütünleştirilmiş uygulama etki alanına yüklü olduğunda ve uygulama etki alanı kaldırıldığında yıkıcı yürütülür yürütülür.  
  
 Genel değişkeni paylaşmak için ortak dil çalışma zamanında bir işlemdeki tüm uygulama etki alanları istiyorsanız kullanın `__declspec(process)` değiştiricisi. `__declspec(process)`Varsayılan olarak altında yürürlükte olan [/CLR](../build/reference/clr-common-language-runtime-compilation.md) ve `__declspec(appdomain)` altında varsayılan olarak etkindir **/CLR: pure**. `__declspec(appdomain)`altında zorlanan **/CLR: safe**. **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı.  
  
 `__declspec(appdomain)`yalnızca geçerli olduğunda birini **/CLR** derleyici seçenekleri kullanılır. Yalnızca genel değişkeni, statik üye değişkeni veya statik yerel değişkeni ile işaretlenebilir `__declspec(appdomain)`. Uygulamak için bir hata olduğunu `__declspec(appdomain)` statik üyeleri için her zaman bu davranış olduğundan yönetilen türleri.  
  
 Kullanarak `__declspec(appdomain)` kullanmaya benzer [iş parçacığı yerel depolaması (TLS)](../parallel/thread-local-storage-tls.md). Uygulama etki alanları gibi iş parçacıkları kendi depolama alanına sahip. Kullanarak `__declspec(appdomain)` genel değişkeni, bu uygulama için oluşturulan her bir uygulama etki alanında kendi depolama alanını sahip sağlar.  
  
 Appdomain değişkenleri ve işlem başına kullanımını karıştırma sınırlama vardır; bkz: [işlem](../cpp/process.md) daha fazla bilgi için.  
  
 Örneğin, program başlangıç, tüm işlem başına değişkenler başlatılır ve ardından tüm appdomain başına değişkenler başlatılır. Bu nedenle bir işlemi başına değişkeni başlatılır, herhangi bir uygulama başına etki alanı Değişken değerini bağımlı olamaz. Kullanımı (ataması) ve işleme değişkenleri appdomain başına karışık hatalı bir uygulamadır.  
  
 Belirli uygulama etki alanında bir işlevi çağırmak nasıl daha fazla bilgi için bkz: [call_in_appdomain işlevi](../dotnet/call-in-appdomain-function.md).  
  
## <a name="example"></a>Örnek  
  
```  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__declspec](../cpp/declspec.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)