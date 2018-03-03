---
title: "Nasıl yapılır: Windows kayıt defterinden veri okuma (C + +/ CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, reading from Windows Registry
- registry, reading
ms.assetid: aebf52c0-acc7-40e2-adbc-d34e0a1e467e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: dfb654ba2cce069086713322624e947e14bc26f4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-read-data-from-the-windows-registry-ccli"></a>Nasıl yapılır: Windows Kayıt Defterinden Veri Okuma (C++/CLI)
Aşağıdaki kod örneğinde <xref:Microsoft.Win32.Registry.CurrentUser> Windows kayıt defterinden veri okuma anahtarı. İlk olarak, alt anahtarlar kullanılarak numaralandırılır <xref:Microsoft.Win32.RegistryKey.GetSubKeyNames%2A> yöntemi ve ardından kimlikleri alt anahtarı kullanılarak açılır <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A> yöntemi. Kök anahtarları gibi her alt tarafından temsil edilen <xref:Microsoft.Win32.RegistryKey> sınıfı. Son olarak, yeni <xref:Microsoft.Win32.RegistryKey> nesnesi anahtar/değer çiftlerini numaralandırmak için kullanılır.  
  
## <a name="example"></a>Örnek  
  
### <a name="code"></a>Kod  
  
```  
// registry_read.cpp  
// compile with: /clr  
using namespace System;  
using namespace Microsoft::Win32;  
  
int main( )  
{  
   array<String^>^ key = Registry::CurrentUser->GetSubKeyNames( );  
  
   Console::WriteLine("Subkeys within CurrentUser root key:");  
   for (int i=0; i<key->Length; i++)  
   {  
      Console::WriteLine("   {0}", key[i]);  
   }  
  
   Console::WriteLine("Opening subkey 'Identities'...");  
   RegistryKey^ rk = nullptr;  
   rk = Registry::CurrentUser->OpenSubKey("Identities");  
   if (rk==nullptr)  
   {  
      Console::WriteLine("Registry key not found - aborting");  
      return -1;  
   }  
  
   Console::WriteLine("Key/value pairs within 'Identities' key:");  
   array<String^>^ name = rk->GetValueNames( );  
   for (int i=0; i<name->Length; i++)  
   {  
      String^ value = rk->GetValue(name[i])->ToString();  
      Console::WriteLine("   {0} = {1}", name[i], value);  
   }  
  
   return 0;  
}  
```  
  
## <a name="remarks"></a>Açıklamalar  
 <xref:Microsoft.Win32.Registry> Sınıfı yalnızca bir kapsayıcıdır statik örnekleri için <xref:Microsoft.Win32.RegistryKey>. Her örneğin bir kök kayıt defteri düğümünü temsil eder. Örnekleri olan <xref:Microsoft.Win32.Registry.ClassesRoot>, <xref:Microsoft.Win32.Registry.CurrentConfig>, <xref:Microsoft.Win32.Registry.CurrentUser>, <xref:Microsoft.Win32.Registry.LocalMachine>, ve <xref:Microsoft.Win32.Registry.Users>.  
  
 Olmanın yanı sıra statik nesnelerinde <xref:Microsoft.Win32.Registry> sınıfı salt okunur. Ayrıca, örnekler, <xref:Microsoft.Win32.RegistryKey> kayıt defteri içeriğine erişmek için oluşturulan sınıf nesneleri salt okunur olan de. Bu davranışı geçersiz kılmak nasıl bir örnek için bkz: [nasıl yapılır: Windows kayıt defterine veri yazma (C + +/ CLI)](../dotnet/how-to-write-data-to-the-windows-registry-cpp-cli.md).  
  
 İki ek nesne vardır <xref:Microsoft.Win32.Registry> sınıfı: <xref:Microsoft.Win32.Registry.DynData> ve <xref:Microsoft.Win32.Registry.PerformanceData>. Her ikisi de örnekleridir <xref:Microsoft.Win32.RegistryKey> sınıfı. <xref:Microsoft.Win32.Registry.DynData> Nesnesi yalnızca Windows 98 ve Windows Me desteklenen dinamik kayıt defteri bilgileri içerir <xref:Microsoft.Win32.Registry.PerformanceData> Nesnesini Windows performans izleme sistemi kullanan uygulamalar için performans sayacı bilgileri erişmek için kullanılabilir. <xref:Microsoft.Win32.Registry.PerformanceData> Düğümü gerçekte kayıt defterinde depolanmaz ve dolayısıyla Regedit.exe kullanarak görüntülenemeyen bilgileri temsil eder.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Windows kayıt defterine veri yazma (C + +/ CLI)](../dotnet/how-to-write-data-to-the-windows-registry-cpp-cli.md)   
 [Windows işlemleri (C + +/ CLI)](../dotnet/windows-operations-cpp-cli.md)   
 [C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)