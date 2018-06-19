---
title: 'Nasıl yapılır: Windows kayıt defterine veri yazma (C + +/ CLI) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- registry, writing to
- Visual C++, writing to Windows Registry
ms.assetid: 3d40b978-4baa-4779-bfe3-47e2917b757f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 304bc224be8776c9793af07283c6a5697a4e49eb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33130808"
---
# <a name="how-to-write-data-to-the-windows-registry-ccli"></a>Nasıl yapılır: Windows Kayıt Defterine Veri Yazma (C++/CLI)
Aşağıdaki kod örneğinde <xref:Microsoft.Win32.Registry.CurrentUser> yazılabilir bir örneğini oluşturmak için anahtar <xref:Microsoft.Win32.RegistryKey> sınıfı karşılık gelen **yazılım** anahtarı. <xref:Microsoft.Win32.RegistryKey.CreateSubKey%2A> Yöntemi yeni bir anahtar oluşturun ve anahtar/değer çiftleri eklemek için sonra kullanılır.  
  
## <a name="example"></a>Örnek  
  
### <a name="code"></a>Kod  
  
```  
// registry_write.cpp  
// compile with: /clr  
using namespace System;  
using namespace Microsoft::Win32;  
  
int main()  
{  
   // The second OpenSubKey argument indicates that  
   // the subkey should be writable.   
   RegistryKey^ rk;  
   rk  = Registry::CurrentUser->OpenSubKey("Software", true);  
   if (!rk)  
   {  
      Console::WriteLine("Failed to open CurrentUser/Software key");  
      return -1;  
   }  
  
   RegistryKey^ nk = rk->CreateSubKey("NewRegKey");  
   if (!nk)  
   {  
      Console::WriteLine("Failed to create 'NewRegKey'");  
      return -1;  
   }  
  
   String^ newValue = "NewValue";  
   try  
   {  
      nk->SetValue("NewKey", newValue);  
      nk->SetValue("NewKey2", 44);  
   }  
   catch (Exception^)  
   {  
      Console::WriteLine("Failed to set new values in 'NewRegKey'");  
      return -1;  
   }  
  
   Console::WriteLine("New key created.");  
   Console::Write("Use REGEDIT.EXE to verify ");  
   Console::WriteLine("'CURRENTUSER/Software/NewRegKey'\n");  
   return 0;  
}  
```  
  
## <a name="remarks"></a>Açıklamalar  
 .NET Framework ile kayıt defterine erişim için kullanabileceğiniz <xref:Microsoft.Win32.Registry> ve [RegistryKey](https://msdn.microsoft.com/en-us/library/microsoft.win32.registrykey.aspx) her ikisi de sınıfları tanımlanan <xref:Microsoft.Win32> ad alanı. **Kayıt defteri** sınıfı statik örnekleri için bir kapsayıcıdır <xref:Microsoft.Win32.RegistryKey> sınıfı. Her örneğin bir kök kayıt defteri düğümünü temsil eder. Örnekleri olan <xref:Microsoft.Win32.Registry.ClassesRoot>, <xref:Microsoft.Win32.Registry.CurrentConfig>, <xref:Microsoft.Win32.Registry.CurrentUser>, <xref:Microsoft.Win32.Registry.LocalMachine>, ve <xref:Microsoft.Win32.Registry.Users>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Windows kayıt defterinden veri okuma (C + +/ CLI)](../dotnet/how-to-read-data-from-the-windows-registry-cpp-cli.md)   
 [C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)