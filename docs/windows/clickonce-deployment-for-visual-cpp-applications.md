---
title: Visual C++ Uygulamaları için ClickOnce Dağıtımı
ms.date: 11/04/2016
helpviewer_keywords:
- deploying applications [C++], ClickOnce
- application deployment [C++], ClickOnce
- ClickOnce deployment [C++], C++ applications
ms.assetid: 9988c546-0936-452c-932f-9c76daa42157
ms.openlocfilehash: 4408db9d129c03ee5df9b006b03c6586df02afb1
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69513759"
---
# <a name="clickonce-deployment-for-visual-c-applications"></a>Visual C++ Uygulamaları için ClickOnce Dağıtımı

Visual Studio, Windows uygulamalarını dağıtmak için iki farklı teknoloji sağlar: ClickOnce dağıtımı veya [Windows Installer](/windows/win32/Msi/windows-installer-portal) dağıtımı.

## <a name="clickonce-deployment-in-c"></a>İçinde ClickOnce dağıtımıC++

Görsel C++ geliştirme ortamı, ClickOnce Ile Visual Studio C++ projelerinin dağıtımını doğrudan desteklemez, ancak araçları kullanmak için kullanılabilir.

> [!NOTE]
>  Visual Studio, Visual C# ve Visual Basic geliştirme ortamlarında ClickOnce 'ı destekler. Visual Studio C++ projeniz bir görsel C# projenin bağımlılığı ise, uygulamayı (bağımlılıkları dahil) görsel C# geliştirme ortamından ClickOnce dağıtımını kullanarak yayımlayabilirsiniz.

ClickOnce kullanarak bir görsel C++ uygulamayı dağıtmak için, önce [Mage. exe (bildirim oluşturma ve düzenleme aracı)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool) veya kendi grafik kullanıcısını kullanarak bir [ClickOnce uygulama bildirimi](/visualstudio/deployment/clickonce-application-manifest) ve [ClickOnce dağıtım bildirimi](/visualstudio/deployment/clickonce-deployment-manifest) oluşturmanız gerekir arabirim sürümü (bilgi için bkz. [MageUI. exe (bildirim oluşturma ve düzenleme aracı, grafik istemci)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)).

İlk olarak, uygulama bildirimini oluşturmak için Mage. exe ' yi kullanın; elde edilen dosya. manifest uzantısına sahip olacaktır. Daha sonra dağıtım bildirimini oluşturmak için Mage. exe ' yi kullanabilirsiniz; elde edilen dosyanın uzantısı. Application olacaktır. Ardından bildirimleri imzalayın.

Uygulama bildiriminin hedef işlemciyi (**x86**, **x64**veya **ARM**) belirtmesi gerekir. Bu seçenekler hakkında bilgi için bkz. [64-bit uygulamalar Için önkoşulları dağıtma](/visualstudio/deployment/deploying-prerequisites-for-64-bit-applications) .

Ayrıca, uygulamanın adı ve dağıtım bildirimlerinin C++ uygulamanın adından farklı olması gerekir. Bu, Mage. exe tarafından oluşturulan uygulama bildirimi ve C++ uygulamanın parçası olan dış bildirim arasındaki çakışmayı önler.

Dağıtımınızın, uygulamanızın bağımlı olduğu tüm görsel C++ kitaplıkları yüklemesi gerekir. Belirli bir uygulamanın bağımlılıklarını öğrenmek için,/BAĞıMLıLAR seçeneğiyle Depends. exe veya DUMPBIN yardımcı programını kullanabilirsiniz. Bağımlılıklar hakkında daha fazla bilgi için bkz. [bir görsel C++ uygulamanın bağımlılıklarını anlama](understanding-the-dependencies-of-a-visual-cpp-application.md). VCRedist. exe ' yi çalıştırmanız gerekebilir. Bu yardımcı program, C++ Visual kitaplıklarını hedef bilgisayara kurar.

Önkoşul bileşenlerini dağıtmak üzere uygulamanız için bir önyükleyici (ön koşul Yükleyicisi) oluşturmanız da gerekebilir; önyükleyici hakkında daha fazla bilgi için bkz. [önyükleyici paketleri oluşturma](/visualstudio/deployment/creating-bootstrapper-packages).

Teknolojinin daha ayrıntılı bir açıklaması için bkz. [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment). ClickOnce dağıtımı hakkında ayrıntılı bir örnek için bkz [. İzlenecek yol: ClickOnce uygulamasını](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)el ile dağıtma.

## <a name="see-also"></a>Ayrıca bkz.

[Mage.exe (Bildirim Oluşturma ve Düzenleme Aracı)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)<br>
[MageUI.exe (Bildirim Oluşturma ve Düzenleme Aracı, Grafik İstemci)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)<br>
[MakeCert. exe (sertifika oluşturma aracı)](/windows/win32/SecCrypto/makecert)<br>
[Masaüstü uygulamaları dağıtma](deploying-native-desktop-applications-visual-cpp.md)<br>
[Uygulamaları, Hizmetleri ve Bileşenleri Dağıtma](/visualstudio/deployment/deploying-applications-services-and-components)<br>
[ClickOnce Güvenliği ve Dağıtımı](/visualstudio/deployment/clickonce-security-and-deployment)<br>
[Önyükleyici Paketleri Oluşturma](/visualstudio/deployment/creating-bootstrapper-packages)<br>
[C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)<br>
[Yerel ve.NET Birlikte Çalışabilirliği](../dotnet/native-and-dotnet-interoperability.md)
