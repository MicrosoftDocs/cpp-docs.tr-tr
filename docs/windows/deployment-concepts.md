---
title: Dağıtım Kavramları
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Installer [C++]
- dependencies [C++], application deployment and
- application deployment [C++], about application deployment
- deploying applications [C++], about deploying applications
- libraries [C++], application deployment issues
ms.assetid: ebd7f246-ab54-40e8-87fa-dac02c0047b3
ms.openlocfilehash: ac3565b4ec465ec60672d2238fbe81b71613a6c1
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65449029"
---
# <a name="deployment-concepts"></a>Dağıtım Kavramları

Bu bölüm, C++ uygulamaları dağıtmak için ana hususlar anlatılmaktadır.

## <a name="windows-installer-deployment-in-c"></a>C++'ta Windows Installer dağıtımı

Visual Studio C++ projeleri dağıtımı için genellikle geleneksel Windows Installer Kurulumu'nu kullanın. Bir Windows Installer dağıtımı hazırlama için setup.exe dosyasını uygulamanızda paketini ve bir yükleyici paketi (.msi) ile birlikte bu dosyayı dağıtma. Kullanıcılar daha sonra uygulamanızı yüklemek için Setup.exe'yi çalıştırın.

Çözümünüze bir kurulum projesi ekleyerek, uygulamanızı paketlemek; yapılandırıldığında, Kurulum ve yükleyici, kullanıcılara dağıttığınız paket dosyaları oluşturur. Daha fazla bilgi için [dağıtım yöntemi seçme](choosing-a-deployment-method.md).

## <a name="library-dependencies"></a>Kitaplık bağımlılıkları

Visual C++ kitaplıkları tarafından sağlanan işlevsellik kullanarak C/C++ uygulamasına yapılandırıldığında, çalışma zamanında bu kitaplıkları varlığını bağımlı olur. Uygulamayı çalıştırmak için sırada bu, statik veya dinamik olarak, gerekli Visual C++ kitaplıklarına bağlamanız gerekir. Bunu yüklenebilmesi için bir uygulama dinamik olarak bağlantılar için Visual C++ Kitaplık, ardından bu kitaplığın çalıştığında mevcut olması gerekir. Uygulama için bir Visual C++ Kitaplık statik olarak bağlanıyorsa, öte yandan, ardından bunu ilgili DLL'lerin kullanıcının bilgisayarında mevcut olması gerekmez. Statik bağlama, ancak uygulama dosyalarının boyutunu artırma ve Bakım potansiyel olarak daha zor hale getirme gibi bazı olumsuz etkileri vardır. Daha fazla bilgi için [DLL'leri kullanmanın yararları](../build/dlls-in-visual-cpp.md#advantages-of-using-dlls).

## <a name="packaging-and-redistributing"></a>Paketleme ve dağıtma

Visual C++ kitaplıkları dll paketlenir ve C/C++ uygulamaları için gerekli tüm kitaplıkların geliştiricinin bilgisayarında Visual Studio tarafından yüklenir. Ancak, kullanıcılarınızın uygulamanızı dağıtırken, uygulamanızı çalıştırmak için Visual Studio'yu yüklemek için gereksinim için çoğu zaman uygun değildir. Yalnızca uygulamanızın düzgün çalışması için gereken Visual C++ bölümlerini yeniden dağıtmak önemlidir.

Paketleme ve dağıtma hakkında daha fazla bilgi için aşağıdaki konulara bakın:

- [Hangi DLL'lerin yeniden dağıtılacağını belirleme](determining-which-dlls-to-redistribute.md).

- [Dağıtım yöntemi seçme](choosing-a-deployment-method.md).

- [Evrensel CRT dağıtım](universal-crt-deployment.md).

Dağıtım örnekleri ve sorun giderme hakkında öneriler için bkz:

- [Dağıtım örnekleri](deployment-examples.md).

- [Sorun giderme C/C++ yalıtılmış uygulamalar ve yan yana derlemeler](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Masaüstü uygulamalarını dağıtma](deploying-native-desktop-applications-visual-cpp.md)
- [Visual C++ Uygulaması Bağımlılıklarını Anlama](understanding-the-dependencies-of-a-visual-cpp-application.md)
