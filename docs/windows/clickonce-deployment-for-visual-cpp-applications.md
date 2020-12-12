---
description: 'Hakkında daha fazla bilgi edinin: Visual C++ uygulamalar için ClickOnce dağıtımı'
title: Visual C++ Uygulamaları için ClickOnce Dağıtımı
ms.date: 11/04/2016
helpviewer_keywords:
- deploying applications [C++], ClickOnce
- application deployment [C++], ClickOnce
- ClickOnce deployment [C++], C++ applications
ms.assetid: 9988c546-0936-452c-932f-9c76daa42157
ms.openlocfilehash: eb888e9236eec16ba82c82c11a23428163679e97
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118218"
---
# <a name="clickonce-deployment-for-visual-c-applications"></a>Visual C++ Uygulamaları için ClickOnce Dağıtımı

Visual Studio, Windows uygulamalarını dağıtmak için iki farklı teknoloji sağlar: ClickOnce dağıtımı veya [Windows Installer](/windows/win32/Msi/windows-installer-portal) dağıtımı.

## <a name="clickonce-deployment-in-c"></a>C++ ' da ClickOnce dağıtımı

Visual C++ geliştirme ortamı, ClickOnce ile Visual Studio C++ projelerinin dağıtımını doğrudan desteklemez, ancak araçları kullanmak için kullanılabilir.

> [!NOTE]
> Visual Studio, Visual C# ve Visual Basic geliştirme ortamlarında ClickOnce 'ı destekler. Visual Studio C++ projeniz bir Visual C# projesinin bağımlılığı ise, Visual C# geliştirme ortamından ClickOnce dağıtımını kullanarak uygulamayı (bağımlılıkları dahil) yayımlayabilirsiniz.

ClickOnce kullanarak bir Visual C++ uygulaması dağıtmak için, önce [Mage.exe (bildirim oluşturma ve düzenleme aracı)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool) veya grafik kullanıcı arabirimi sürümünü kullanarak bir [ClickOnce uygulama bildirimi](/visualstudio/deployment/clickonce-application-manifest) ve [ClickOnce dağıtım bildirimi](/visualstudio/deployment/clickonce-deployment-manifest) oluşturmanız gerekir (bilgi için bkz. [MageUI.exe (bildirim oluşturma ve düzenleme aracı, grafik istemci)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)).

İlk olarak uygulama bildirimi oluşturmak için Mage.exe kullanın; elde edilen dosya. manifest uzantısına sahip olacaktır. Sonra dağıtım bildirimini oluşturmak için Mage.exe kullanırsınız; elde edilen dosyanın uzantısı. Application olacaktır. Ardından bildirimleri imzalayın.

Uygulama bildiriminin hedef işlemciyi (**x86**, **x64** veya **ARM**) belirtmesi gerekir. Bu seçenekler hakkında bilgi için bkz. [64-bit uygulamalar Için önkoşulları dağıtma](/visualstudio/deployment/deploying-prerequisites-for-64-bit-applications) .

Ayrıca, uygulama ve dağıtım bildirimlerinin adı, C++ uygulamasının adından farklı olmalıdır. Bu, Mage.exe tarafından oluşturulan uygulama bildirimi ve C++ uygulamasının bir parçası olan dış bildirim arasındaki çakışmayı önler.

Dağıtımınızın, uygulamanızın bağlı olduğu Visual C++ kitaplıklarını yüklemesi gerekir. Belirli bir uygulamanın bağımlılıklarını öğrenmek için,/BAĞıMLıLAR seçeneğiyle depends.exe veya DUMPBIN yardımcı programını kullanabilirsiniz. Bağımlılıklar hakkında daha fazla bilgi için bkz. [bir Visual C++ uygulamasının bağımlılıklarını anlama](understanding-the-dependencies-of-a-visual-cpp-application.md). VCRedist.exe çalıştırmanız gerekebilir; Bu yardımcı program hedef bilgisayara Visual C++ kitaplıklarını yüklüyor.

Önkoşul bileşenlerini dağıtmak üzere uygulamanız için bir önyükleyici (ön koşul Yükleyicisi) oluşturmanız da gerekebilir; önyükleyici hakkında daha fazla bilgi için bkz. [önyükleyici paketleri oluşturma](/visualstudio/deployment/creating-bootstrapper-packages).

Teknolojinin daha ayrıntılı bir açıklaması için bkz. [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment). ClickOnce dağıtımı hakkında ayrıntılı bir örnek için bkz. [Izlenecek yol: ClickOnce uygulamasını El Ile dağıtma](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application).

## <a name="see-also"></a>Ayrıca bkz.

[Mage.exe (Bildirim Oluşturma ve Düzenleme Aracı)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)<br>
[MageUI.exe (Bildirim Oluşturma ve Düzenleme Aracı, grafik Istemci)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)<br>
[Makecert.exe (sertifika oluşturma aracı)](/windows/win32/SecCrypto/makecert)<br>
[Masaüstü uygulamaları dağıtma](deploying-native-desktop-applications-visual-cpp.md)<br>
[Uygulamaları, Hizmetleri ve Bileşenleri Dağıtma](/visualstudio/deployment/deploying-applications-services-and-components)<br>
[ClickOnce güvenliği ve dağıtımı](/visualstudio/deployment/clickonce-security-and-deployment)<br>
[Önyükleyici Paketleri Oluşturma](/visualstudio/deployment/creating-bootstrapper-packages)<br>
[C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)<br>
[Yerel ve .NET birlikte çalışabilirliği](../dotnet/native-and-dotnet-interoperability.md)
