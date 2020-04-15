---
title: Visual C++ Uygulamaları için ClickOnce Dağıtımı
ms.date: 11/04/2016
helpviewer_keywords:
- deploying applications [C++], ClickOnce
- application deployment [C++], ClickOnce
- ClickOnce deployment [C++], C++ applications
ms.assetid: 9988c546-0936-452c-932f-9c76daa42157
ms.openlocfilehash: 4726fda8c5eca70ce7acde19f141a7c096395e95
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81316617"
---
# <a name="clickonce-deployment-for-visual-c-applications"></a>Visual C++ Uygulamaları için ClickOnce Dağıtımı

Visual Studio, Windows uygulamalarını dağıtmak için iki farklı teknoloji sağlar: ClickOnce dağıtım veya [Windows Installer](/windows/win32/Msi/windows-installer-portal) dağıtımı.

## <a name="clickonce-deployment-in-c"></a>C++'da ClickOnce Dağıtım

Visual C++ geliştirme ortamı, Visual Studio C++ projelerinin ClickOnce ile dağıtımını doğrudan desteklemez, ancak bunları kullanmak için araçlar kullanılabilir.

> [!NOTE]
> Visual Studio, Visual C# ve Visual Basic geliştirme ortamlarında ClickOnce'yi destekler. Visual Studio C++ projeniz Visual C# projesinin bir bağımlılığıysa, Visual C# geliştirme ortamından ClickOnce dağıtımını kullanarak uygulamayı (bağımlılıkları dahil) yayımlayabilirsiniz.

ClickOnce'yi kullanarak Görsel C++ uygulamasını dağıtmak için öncelikle [Mage.exe (Manifest Generation and Editing Tool) veya](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool) grafik kullanıcı arabirimi sürümünü kullanarak [clickonce Uygulama Bildirimi](/visualstudio/deployment/clickonce-application-manifest) ve [ClickOnce Dağıtım Bildirimi](/visualstudio/deployment/clickonce-deployment-manifest) oluşturmanız gerekir (bilgi için [bkz. MageUI.exe (Manifest Oluşturma ve Düzenleme Aracı, Grafik İstemci)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)).

İlk uygulama bildirimi oluşturmak için Mage.exe kullanın; ortaya çıkan dosya uzantısı .manifest olacaktır. Daha sonra dağıtım bildirimi oluşturmak için Mage.exe kullanın; ortaya çıkan dosya uzantısı .application olacaktır. Daha sonra manifestoları imzalarsınız.

Uygulama bildirimi hedef işlemciyi **(x86**, **x64**veya **ARM)** belirtmelidir. Bu seçenekler hakkında bilgi [için 64 bit Uygulamalar için Ön Koşulları Dağıtma'ya](/visualstudio/deployment/deploying-prerequisites-for-64-bit-applications) bakın.

Ayrıca, uygulama ve dağıtım bildirimlerinin adı C++ uygulamasının adından farklı olmalıdır. Bu, Mage.exe tarafından oluşturulan uygulama bildirimi ile C++ uygulamasının bir parçası olan dış bildirim arasındaki çakışmayı önler.

Dağıtımınızın, uygulamanızın bağlı olduğu Visual C++ kitaplıklarını yüklemesi gerekir. Belirli bir uygulamanın bağımlılıklarını belirlemek için depends.exe veya /DEPENDS seçeneği ile DUMPBIN yardımcı programını kullanabilirsiniz. Bağımlılıklar hakkında daha fazla bilgi için [bkz.](understanding-the-dependencies-of-a-visual-cpp-application.md) VCRedist.exe çalıştırmak gerekebilir; bu yardımcı program hedef bilgisayara Visual C++ kitaplıklarını yükler.

Ayrıca, önkoşul bileşenleri dağıtmak için uygulamanız için bir bootstrapper (önkoşul yükleyici) oluşturmanız gerekebilir; bootstrapper hakkında bilgi için, [Bootstrapper Paketleri oluşturma](/visualstudio/deployment/creating-bootstrapper-packages)bakın.

Teknolojinin daha ayrıntılı bir açıklaması için [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment)bölümüne bakın. ClickOnce dağıtımının ayrıntılı bir örneği için [Bkz. Walkthrough: ClickOnce Uygulamasını el ile dağıtma](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application).

## <a name="see-also"></a>Ayrıca bkz.

[Mage.exe (Manifesto Oluşturma ve Düzenleme Aracı)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)<br>
[MageUI.exe (Manifesto Oluşturma ve Düzenleme Aracı, Grafik İstemci)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)<br>
[Makecert.exe (Sertifika Oluşturma Aracı)](/windows/win32/SecCrypto/makecert)<br>
[Masaüstü Uygulamalarını Dağıtma](deploying-native-desktop-applications-visual-cpp.md)<br>
[Uygulamaları, Hizmetleri ve Bileşenleri Dağıtma](/visualstudio/deployment/deploying-applications-services-and-components)<br>
[ClickOnce Güvenliği ve Dağıtımı](/visualstudio/deployment/clickonce-security-and-deployment)<br>
[Önyükleyici Paketleri Oluşturma](/visualstudio/deployment/creating-bootstrapper-packages)<br>
[C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)<br>
[Yerel ve.NET Birlikte Çalışabilirliği](../dotnet/native-and-dotnet-interoperability.md)
