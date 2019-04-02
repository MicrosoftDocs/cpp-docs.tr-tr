---
title: Visual C++ Uygulamaları için ClickOnce Dağıtımı
ms.date: 11/04/2016
helpviewer_keywords:
- deploying applications [C++], ClickOnce
- application deployment [C++], ClickOnce
- ClickOnce deployment [C++], C++ applications
ms.assetid: 9988c546-0936-452c-932f-9c76daa42157
ms.openlocfilehash: 83ee85dbf952fd78a1cd1b8d0c932b9dcd02682d
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58787074"
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

Dağıtımınızın, uygulamanızın bağımlı olduğu tüm Visual C++ kitaplıkları yüklemeniz gerekir. Belirli bir uygulamanın bağımlılıklarını belirlemek için depends.exe'yi veya DUMPBIN yardımcı programını/DEPENDENTS seçeneğiyle kullanabilirsiniz. Bağımlılıklar hakkında daha fazla bilgi için bkz. [Visual C++ uygulaması bağımlılıklarını anlama](understanding-the-dependencies-of-a-visual-cpp-application.md). VCRedist.exe'yi çalıştırmanız gerekebilir. Bu yardımcı program hedef bilgisayarda Visual C++ kitaplıklarını yükler.

Uygulamanızın önkoşul bileşenleri dağıtması için bir önyükleyici (Önkoşul Yükleyici) derleme gerekebilir; hakkında daha fazla bilgi için bkz. [önyükleyici paketleri oluşturma](/visualstudio/deployment/creating-bootstrapper-packages).

Teknolojinin daha ayrıntılı bir açıklaması için bkz. [ClickOnce güvenliği ve dağıtımı](/visualstudio/deployment/clickonce-security-and-deployment). ClickOnce dağıtımı ayrıntılı bir örnek için bkz: [izlenecek yol: Bir ClickOnce uygulamasını el ile dağıtma](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application).

## <a name="see-also"></a>Ayrıca bkz.

[Mage.exe (Bildirim Oluşturma ve Düzenleme Aracı)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)<br>
[MageUI.exe (Bildirim Oluşturma ve Düzenleme Aracı, Grafik İstemci)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)<br>
[MakeCert.exe (sertifika oluşturma aracı)](https://msdn.microsoft.com/library/windows/desktop/aa386968)<br>
[Masaüstü uygulamalarını dağıtma](deploying-native-desktop-applications-visual-cpp.md)<br>
[Uygulamaları, Hizmetleri ve Bileşenleri Dağıtma](/visualstudio/deployment/deploying-applications-services-and-components)<br>
[ClickOnce Güvenliği ve Dağıtımı](/visualstudio/deployment/clickonce-security-and-deployment)<br>
[Önyükleyici Paketleri Oluşturma](/visualstudio/deployment/creating-bootstrapper-packages)<br>
[C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)<br>
[Yerel ve.NET Birlikte Çalışabilirliği](../dotnet/native-and-dotnet-interoperability.md)
