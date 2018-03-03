---
title: "Tanımlayıcı ad derlemeleri (derleme imzalama) (C + +/ CLI) | Microsoft Docs"
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
- assemblies [C++]
- signing assemblies
- .NET Framework [C++], assembly signing
- assemblies [C++], signing
- linker [C++], assembly signing
- strong-named assemblies [C++]
ms.assetid: c337cd3f-e5dd-4c6f-a1ad-437e85dba1cc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 2099389131145838a70b579053c65698dbc3a857
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="strong-name-assemblies-assembly-signing-ccli"></a>Tanımlayıcı Ad Derlemeleri (Derleme İmzalama) (C++/CLI)
Bu konuda, genellikle derlemenizi güçlü bir ad verip olarak adlandırılan derlemenizi ne kaydolabilirsiniz anlatılmaktadır.  
  
## <a name="remarks"></a>Açıklamalar  
 Visual C++ kullanırken, derleme imzalama için CLR öznitelikleri için ilgili sorunlardan kaçınmak amacıyla, derlemenizi imzalamak için bağlayıcı seçenekleri kullanın:  
  
-   <xref:System.Reflection.AssemblyDelaySignAttribute>  
  
-   <xref:System.Reflection.AssemblyKeyFileAttribute>  
  
-   <xref:System.Reflection.AssemblyKeyNameAttribute>  
  
 Anahtar adı dosya adı gizli bilgileri içeriyorsa, bir güvenlik riski olabilecek derleme meta verilerde görünür olduğunu olgu öznitelikleri kullanmayan nedenleri içerir. Ayrıca, Visual C++ geliştirme ortamı tarafından kullanılan yapılandırma süreci bir derleme tanımlayıcı bir ad vermek için CLR öznitelikleri kullanın ve ardından derleme üzerinde mt.exe gibi işlem sonrası bir araç çalıştırırsanız, derleme imzalanmamış anahtarı geçersiz kılar.  
  
 Komut satırında derleme, derlemenizi imzalamak için bağlayıcı seçenekleri kullanın ve sonra işlem sonrası Aracı (mt.exe gibi) çalıştırırsanız, derleme sn.exe ile yeniden imzalamak gerekir. Alternatif olarak, yapı derlemenin imzalanmasını gecikme ve işlem sonrası araçlarını çalıştırdıktan sonra imzalamayı tamamlayabilirsiniz.  
  
 Geliştirme ortamında yapılandırırken imzalama özniteliklerini kullanırsanız, başarıyla derleme açıkça sn.exe çağırarak imzalayabilirsiniz ([Sn.exe (tanımlayıcı ad aracı)](/dotnet/framework/tools/sn-exe-strong-name-tool)) oluşturma sonrası olay. Daha fazla bilgi için bkz: [derleme olayları belirtme](../ide/specifying-build-events.md). Öznitelikler ve bağlayıcı seçenekleri kullanmaya kıyasla bir oluşturma sonrası olay kullanırsanız yapılandırma süreleri daha az olabilir.  
  
 Derleme imzalama aşağıdaki bağlayıcı seçeneklerini destekler:  
  
-   [/ DELAYSIGN (derlemeyi kısmen imzala)](../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [/ KEYFILE (derlemeyi imzalamak için anahtar veya anahtar çiftini belirt)](../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
-   [/ KEYCONTAINER (derlemeyi imzalamak için anahtar kapsayıcısını belirt)](../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
 Tanımlayıcı derlemeler hakkında daha fazla bilgi için bkz: [bkz](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)