---
description: 'Daha fazla bilgi edinin: dağıtım kavramları'
title: Dağıtım Kavramları
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Installer [C++]
- dependencies [C++], application deployment and
- application deployment [C++], about application deployment
- deploying applications [C++], about deploying applications
- libraries [C++], application deployment issues
ms.assetid: ebd7f246-ab54-40e8-87fa-dac02c0047b3
ms.openlocfilehash: 441e067a541f375029cdb55321a8ad75d1f03c67
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329426"
---
# <a name="deployment-concepts"></a>Dağıtım Kavramları

Bu bölümde, C++ uygulamalarını dağıtmaya yönelik başlıca noktalar açıklanmaktadır.

## <a name="windows-installer-deployment-in-c"></a>C++ ' da Windows Installer dağıtımı

Visual Studio C++ projeleri genellikle dağıtım için geleneksel Windows Installer kurulumunu kullanır. Windows Installer dağıtımı hazırlamak için, uygulamanızı bir setup.exe dosyasına paketleyip bu dosyayı bir yükleyici paketiyle (. msi) birlikte dağıtırsınız. Ardından kullanıcılar setup.exe çalıştırıp uygulamanızı yükler.

Çözümünüze bir kurulum projesi ekleyerek uygulamanızı paketleyin; oluşturulduğunda, kullanıcılara dağıttığınız kurulum ve Yükleyici paket dosyalarını oluşturur. Daha fazla bilgi için bkz. [dağıtım yöntemi seçme](choosing-a-deployment-method.md).

## <a name="library-dependencies"></a>Kitaplık bağımlılıkları

Bir C/C++ uygulaması, Visual C++ kitaplıkları tarafından sunulan işlevsellik kullanılarak derlenirse, çalışma zamanında bu kitaplıkların varlığına bağımlı olur. Uygulamanın çalışması için, gerekli Visual C++ kitaplıklarına statik veya dinamik olarak bağlanması gerekir. Bir uygulama bir Visual C++ kitaplığına dinamik olarak bağlanıyorsa, yüklenebilmesi için o kitaplığın mevcut olması gerekir. Öte yandan, uygulama bir Visual C++ kitaplığına statik olarak bağlanıyorsa, ilgili DLL 'Lerin kullanıcının bilgisayarında mevcut olması gerekmez. Ancak statik bağlama, uygulama dosyalarının boyutunu artırma ve bakımın daha zor hale getirilmesi gibi bazı negatif etkilere sahiptir. Daha fazla bilgi için bkz. [DLL 'leri kullanmanın avantajları](../build/dlls-in-visual-cpp.md#advantages-of-using-dlls).

## <a name="packaging-and-redistributing"></a>Paketleme ve yeniden dağıtma

Visual C++ kitaplıklar dll olarak paketlenmiştir ve C/C++ uygulamaları için gerekli tüm kitaplıklar geliştirici bilgisayarına Visual Studio tarafından yüklenir. Bununla birlikte, uygulamanızı kullanıcılarınıza dağıttığınızda, uygulamanızın çalıştırılabilmesi için Visual Studio 'Yu yüklemeleri gerekli değildir. Uygulamanızın doğru şekilde çalışması için gereken Visual C++ parçalarını yeniden dağıtmanız önemlidir.

Paketleme ve yeniden dağıtma hakkında daha fazla bilgi için aşağıdaki konulara bakın:

- [Hangi dll 'lerin yeniden dağıtılacağını belirleme](determining-which-dlls-to-redistribute.md).

- [Dağıtım yöntemi seçme](choosing-a-deployment-method.md).

- [Evrensel CRT dağıtımı](universal-crt-deployment.md).

Dağıtım örnekleri ve sorun giderme hakkında öneriler için bkz.:

- [Dağıtım örnekleri](deployment-examples.md).

- [C/C++ yalıtılmış uygulamaları ve yan yana derlemeler Ile Ilgili sorunları giderme](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Masaüstü uygulamaları dağıtma](deploying-native-desktop-applications-visual-cpp.md)
- [Visual C++ Uygulaması Bağımlılıklarını Anlama](understanding-the-dependencies-of-a-visual-cpp-application.md)
