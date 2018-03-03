---
title: Desteklenen platformlar (Visual C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, platforms supported
- platforms [C++]
ms.assetid: 0d893056-4008-411a-b3d1-5f57fd7da95c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4080fa1bac30ac88edca33f6de32b0a6490f4341
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="supported-platforms-visual-c"></a>Desteklenen Platformlar (Visual C++)

Kullanılarak oluşturulan uygulamaların [!INCLUDE[vsprvs](assembler/masm/includes/vsprvs_md.md)] çeşitli platformlar için şu şekilde hedeflenebilir.  
  
|İşletim sistemi|x86|X64|ARM|  
|----------------------|---------|---------|---------|  
|Windows XP|X *|X *||  
|[!INCLUDE[WinXPSvr](build/includes/winxpsvr_md.md)]|X *|X *||  
|Windows Vista|X|X||  
|Windows Server 2008|X|X||  
|Windows 7|X|X||  
|Windows Server 2012 R2|X|X||  
|Windows 8|X|X|X|  
|Windows 8.1|X|X|X|  
|Windows 10|X|X|X|  
|Android **|X|X|X|  
|iOS **|X|X|X|  
|Linux ***|X|X|X|  
  
\*Visual Studio 2017, Visual Studio 2015, Visual Studio 2013 ve Visual Studio 2012 Update 1 veya daha sonra Windows XP oluşturmak için dahil Windows XP platform araç takımı kullanabilirsiniz ve [!INCLUDE[WinXPSvr](build/includes/winxpsvr_md.md)] projeleri. Bu platform araç takımı kullanma hakkında daha fazla bilgi için bkz: [yapılandırma programlar için Windows XP](build/configuring-programs-for-windows-xp.md). Platform araç kümesini değiştirme hakkında ek bilgi için bkz: [nasıl yapılır: hedef Framework ve Platform araç kümesini değiştirme](build/how-to-modify-the-target-framework-and-platform-toolset.md).  
  
\*\*Yükleyebileceğiniz **C++ ile Mobil Geliştirme** Visual Studio yükleyicisi iş yükündeki (veya isteğe bağlı **platformlar arası Mobil Geliştirme için Visual C++** Visual Studio 2015 kurulumundaki bileşen) için Hedef iOS veya Android platformları. Yönergeler için bkz: [platformlar arası Mobil Geliştirme için Visual C++ yüklemek](/visualstudio/cross-platform/install-visual-cpp-for-cross-platform-mobile-development). İOS kodu oluşturmak için bir Mac bilgisayara sahip olmanız ve diğer gereksinimleri karşılaması gerekir. Önkoşullar ve yükleme yönergeleri listesi için bkz: [yükleme ve yapılandırma araçları iOS kullanılarak derleme](/visualstudio/cross-platform/install-and-configure-tools-to-build-using-ios). X86 veya hedef donanım eşleştirmek için ARM kod oluşturabilirsiniz. İOS simülatörü, Android için Microsoft Visual Studio öykünücüsü ve bazı Android cihazlar için oluşturmak için yapılandırmaları x86 kullan. İOS cihazları ve çoğu Android cihazlar için oluşturmak için ARM yapılandırmaları kullanın.  
  
\*\*\*Yükleyebileceğiniz **C++ ile Linux geliştirme** hedef Linux platformlar için Visual Studio yükleyicisinde iş yükü. Yönergeler için bkz: [indirme, yükleme ve Linux iş yükü Kurulum](linux/download-install-and-setup-the-linux-development-workload.md). Desteklenen her mimari için oluşturabilmeniz bu araç takımı, yürütülebilir dosyayı hedef makinede derler.  

Hedef platform yapılandırması ayarlama hakkında daha fazla bilgi için bkz: [nasıl yapılır: Visual C++ projeleri hedef 64-Bit, x64 yapılandırma platformları](build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[Visual C++ Araçları ve Visual Studio sürümlerinde özellikleri](ide/visual-cpp-tools-and-features-in-visual-studio-editions.md)   
[Başlarken](/visualstudio/ide/getting-started-with-visual-cpp-in-visual-studio)