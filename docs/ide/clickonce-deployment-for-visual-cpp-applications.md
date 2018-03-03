---
title: "Visual C++ uygulamaları için ClickOnce dağıtımı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- deploying applications [C++], ClickOnce
- application deployment [C++], ClickOnce
- ClickOnce deployment [C++], C++ applications
ms.assetid: 9988c546-0936-452c-932f-9c76daa42157
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e1a036a1520a747448c5541f367f0b43711e30b1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="clickonce-deployment-for-visual-c-applications"></a>Visual C++ Uygulamaları için ClickOnce Dağıtımı
Visual Studio, Windows uygulamalarını dağıtmak için iki farklı teknolojiler sağlar: ClickOnce dağıtım veya [Windows Installer](http://msdn.microsoft.com/library/cc185688) dağıtım.  
  
## <a name="clickonce-deployment-in-c"></a>C++'da ClickOnce dağıtımı  
 Visual C++ geliştirme ortamı Visual C++ projeleri ClickOnce ile dağıtımını doğrudan desteklemez, ancak araçları kullanmak kullanılabilir.  
  
> [!NOTE]
>  Visual Studio, Visual C# ve Visual Basic geliştirme ortamlarında ClickOnce desteklemiyor. Visual C++ projeniz Visual C# projesinde bağımlılığıdır varsa (bağımlılıklarını dahil) uygulama yayımlayabilirsiniz kullanarak bir Visual C# geliştirme ortamı'ndan ClickOnce dağıtımı.  
  
 ClickOnce kullanarak bir Visual C++ uygulaması dağıtmak için önce oluşturmak zorunda bir [ClickOnce Uygulama bildirimi](/visualstudio/deployment/clickonce-application-manifest) ve [ClickOnce dağıtım bildirimi](/visualstudio/deployment/clickonce-deployment-manifest) kullanarak [Mage.exe (bildirim Oluşturma ve düzenleme aracı)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool) veya onun bir grafik kullanıcı arabirimi sürümünü (bilgi için bkz: [MageUI.exe (bildirim üretme ve düzenleme aracı, grafik istemci)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)).  

  
 İlk uygulama bildirimi oluşturmak için Mage.exe kullanın; elde edilen dosya uzantısı .manifest olacaktır. Ardından dağıtım bildirimi oluşturmak için Mage.exe kullanın; elde edilen dosya uzantısı .application olacaktır. Bildirimleri imzalayın.  
  
 Uygulama bildirimi hedef işlemciyi belirtmeniz gerekir (**x86**, **x64**, veya **ARM**). Bkz: [64-bit uygulamalar için önkoşulları dağıtma](/visualstudio/deployment/deploying-prerequisites-for-64-bit-applications) Bu seçenekler hakkında bilgi için.  
  
 Ayrıca, uygulama ve dağıtım bildirimlerini adını C++ uygulaması adından farklı olmalıdır. Mage.exe tarafından oluşturulan uygulama bildirimi ve C++ uygulaması parçası olan dış bildirimi arasında çakışma önler.  
  
 Dağıtımınız, uygulamanızın bağımlı olduğu tüm Visual C++ kitaplıkları yüklemeniz gerekir. Belirli bir uygulama için bağımlılıkları belirlemek için/DEPENDENTS seçeneğiyle depends.exe veya DUMPBIN yardımcı programını kullanabilirsiniz. Bağımlılıklar hakkında daha fazla bilgi için bkz: [bir Visual C++ uygulaması bağımlılıklarını anlama](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md). VCRedist.exe'yi çalıştırmanız gerekebilir; Bu yardımcı program Visual C++ kitaplıkları hedef bilgisayara yükler.  
  
 Önkoşul bileşenlerini dağıtmak, uygulamanız için bir önyükleyici (Önkoşul Yükleyici) yapı gerekebilir; önyükleyici hakkında daha fazla bilgi için bkz: [önyükleyici paketleri oluşturma](/visualstudio/deployment/creating-bootstrapper-packages).  
  
 Teknolojinin daha ayrıntılı bir açıklaması için bkz: [ClickOnce güvenliği ve dağıtımı](/visualstudio/deployment/clickonce-security-and-deployment). ClickOnce dağıtımı ayrıntılı bir örnek için bkz: [izlenecek yol: bir ClickOnce uygulamasını el ile dağıtma](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Mage.exe (bildirim üretme ve düzenleme aracı)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)   
 [MageUI.exe (bildirim üretme ve düzenleme aracı, grafik istemci)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)   
 [MakeCert.exe (sertifika oluşturma aracı)](https://msdn.microsoft.com/library/windows/desktop/aa386968)   
 [Masaüstü uygulamaları dağıtma](../ide/deploying-native-desktop-applications-visual-cpp.md)   
 [Uygulamaları, hizmetleri ve bileşenleri dağıtma](/visualstudio/deployment/deploying-applications-services-and-components)   
 [Windows Installer dağıtımı](http://msdn.microsoft.com/en-us/121be21b-b916-43e2-8f10-8b080516d2a0)   
 [ClickOnce güvenliği ve dağıtımı](/visualstudio/deployment/clickonce-security-and-deployment)   
 [Önyükleyici paketleri oluşturma](/visualstudio/deployment/creating-bootstrapper-packages)   
 [.NET programlama ile C + +/ CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [Yerel ve.NET Birlikte Çalışabilirliği](../dotnet/native-and-dotnet-interoperability.md)