---
title: Visual C++ uygulamaları için ClickOnce dağıtımı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- deploying applications [C++], ClickOnce
- application deployment [C++], ClickOnce
- ClickOnce deployment [C++], C++ applications
ms.assetid: 9988c546-0936-452c-932f-9c76daa42157
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 82a290eb7695bbcd7c03cda0351445519352e80a
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43677730"
---
# <a name="clickonce-deployment-for-visual-c-applications"></a>Visual C++ Uygulamaları için ClickOnce Dağıtımı
Visual Studio, Windows uygulamalarını dağıtmak için iki farklı teknoloji sağlar: ClickOnce dağıtımı veya [Windows Installer](/windows/desktop/Msi/windows-installer-portal) dağıtım.  
  
## <a name="clickonce-deployment-in-c"></a>C++'da ClickOnce dağıtımı  
 Visual C++ geliştirme ortamına Visual C++ projeleriyle ClickOnce dağıtımını doğrudan desteklemez, ancak bunu kullanmak Araçlar kullanılabilir.  
  
> [!NOTE]
>  Visual Studio ClickOnce Visual C# ve Visual Basic geliştirme ortamlarında destekler. Visual C++ projenize bir Visual C# projesinin bir bağımlılık ise, (bağımlılıklarıyla birlikte) uygulamayı yayımlayabilmeniz için Visual C# geliştirme ortamından ClickOnce dağıtımını kullanarak.  
  
 ClickOnce kullanarak bir Visual C++ uygulaması dağıtmak için öncelikle oluşturulacak olması bir [ClickOnce Uygulama bildirimi](/visualstudio/deployment/clickonce-application-manifest) ve [ClickOnce dağıtım bildirimi](/visualstudio/deployment/clickonce-deployment-manifest) kullanarak [Mage.exe (bildirim Oluşturma ve düzenleme aracı)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool) veya grafik kullanıcı arabirimi sürümü (bilgi için [MageUI.exe (bildirim üretme ve düzenleme aracı, grafik istemci)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)).  

  
 Mage.exe önce uygulama bildirimini oluşturmak için kullanın. elde edilen dosyanın uzantısı .manifest olacaktır. Dağıtım bildirimi oluşturmak için Mage.exe'yi kullanın; elde edilen dosyanın uzantısı .application olacaktır. Bildirimleri imzalayın.  
  
 Uygulama bildirimi hedef işlemciyi belirtmelidir (**x86**, **x64**, veya **ARM**). Bkz: [64-bit uygulamalar için önkoşulları dağıtma](/visualstudio/deployment/deploying-prerequisites-for-64-bit-applications) Bu seçenekler hakkında daha fazla bilgi için.  
  
 Ayrıca, uygulama ve dağıtım bildirimlerinin adı C++ uygulamasının adından farklı olmalıdır. Bu, Mage.exe tarafından oluşturulan uygulama bildirimi ile C++ uygulamasının bir parçası olan harici bildirim arasında çakışma önler.  
  
 Dağıtımınızın, uygulamanızın bağımlı olduğu tüm Visual C++ kitaplıkları yüklemeniz gerekir. Belirli bir uygulamanın bağımlılıklarını belirlemek için depends.exe'yi veya DUMPBIN yardımcı programını/DEPENDENTS seçeneğiyle kullanabilirsiniz. Bağımlılıklar hakkında daha fazla bilgi için bkz. [Visual C++ uygulaması bağımlılıklarını anlama](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md). VCRedist.exe'yi çalıştırmanız gerekebilir. Bu yardımcı program hedef bilgisayarda Visual C++ kitaplıklarını yükler.  
  
 Uygulamanızın önkoşul bileşenleri dağıtması için bir önyükleyici (Önkoşul Yükleyici) derleme gerekebilir; hakkında daha fazla bilgi için bkz. [önyükleyici paketleri oluşturma](/visualstudio/deployment/creating-bootstrapper-packages).  
  
 Teknolojinin daha ayrıntılı bir açıklaması için bkz. [ClickOnce güvenliği ve dağıtımı](/visualstudio/deployment/clickonce-security-and-deployment). ClickOnce dağıtımının ayrıntılı bir örnek için bkz. [izlenecek yol: ClickOnce uygulamasını el ile dağıtma](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Mage.exe (bildirim üretme ve düzenleme aracı)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)   
 [MageUI.exe (bildirim üretme ve düzenleme aracı, grafik istemci)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)   
 [MakeCert.exe (sertifika oluşturma aracı)](https://msdn.microsoft.com/library/windows/desktop/aa386968)   
 [Masaüstü uygulamalarını dağıtma](../ide/deploying-native-desktop-applications-visual-cpp.md)   
 [Uygulamaları, hizmetleri ve bileşenleri dağıtma](/visualstudio/deployment/deploying-applications-services-and-components)   
 [ClickOnce güvenliği ve dağıtımı](/visualstudio/deployment/clickonce-security-and-deployment)   
 [Önyükleyici paketleri oluşturma](/visualstudio/deployment/creating-bootstrapper-packages)   
 [.NET programlama ile C + +/ CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [Yerel ve.NET Birlikte Çalışabilirliği](../dotnet/native-and-dotnet-interoperability.md)