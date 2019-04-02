---
title: Visual C++ üzerinde Dağıtım
ms.date: 05/11/2018
helpviewer_keywords:
- deploying applications [C++]
- application deployment [C++]
ms.assetid: d4b4ffc0-d2bd-4e4a-84a6-62f1c26f6a09
ms.openlocfilehash: 8dccf581cff88dc2e8c4a889bed8b47fc140eb7c
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58787681"
---
# <a name="deployment-in-visual-c"></a>Visual C++ üzerinde Dağıtım

Uygulamanızı geliştirme bilgisayarınızın dışında bir bilgisayara yüklenmesini olarak bilinen *dağıtım*. Başka bir bilgisayara Visual C++ uygulamasını dağıttığınızda, hem uygulamayı hem de bağımlı olduğu kitaplık dosyalarını yüklemeniz gerekir. Visual Studio, Visual C++ kitaplıklarını uygulamanızla birlikte dağıtmak için üç yol sağlar: *merkezi dağıtım*, *yerel dağıtım*, ve *statik bağlama*. Merkezi dağıtım, burada Windows Update hizmeti otomatik olarak güncelleştirebilirsiniz, Windows dizini altındaki kitaplık dosyaları yerleştirir. Yerel dağıtım kitaplık dosyalarını uygulamanız ile aynı dizine koyar. Herhangi bir yerel olarak dağıtılan kitaplıkları yeniden dağıtmanız gerekir kendinize bunları güncelleştirin. Statik bağlama kitaplık kodu uygulamanıza bağlar. Yeniden derleyin ve statik bağlama kullandığınızda herhangi bir güncelleştirme kitaplıklara yararlanmak için uygulamanızı yeniden dağıtmanız gerekir.

Visual Studio 2015'te sürüme özgü yerel kitaplığı bileşenlerini ve artık Windows parçası olan yeni bir evrensel C çalışma zamanı kitaplığı, Microsoft C çalışma zamanı kitaplığı yeniden düzenlenmeden. Evrensel CRT dağıtımı hakkında daha fazla bilgi için bkz: [Evrensel CRT dağıtım](universal-crt-deployment.md).

## <a name="central-deployment"></a>Merkezi Dağıtım

Merkezi dağıtımda, kitaplık DLL dosyaları Windows\System32 dizininde veya 32-bit kitaplık dosyalarını x64 yüklü sistemleri, Windows\SysWow64 dizini. Microsoft, merkezi olarak dağıtılan kitaplıklarını otomatik olarak güncelleştirir. Yerel olarak dağıtılan veya statik olarak bağlanan Visual C++ kitaplıkları için güncelleştirmeleri sağlamanız gerekir.

Visual C++ kitaplıklarını merkezi olarak dağıtmak için bu iki kaynak dosyaları için yüklemek için kullanabilirsiniz:

- *Yeniden dağıtılabilir paket* sıkıştırılmış formdaki tüm Visual C++ yeniden dağıtılabilir kitaplıklarını içeren tek başına komut satırı yürütülebilir dosyalar, dosyalar, veya

- *Yeniden dağıtılabilir birleştirme modülleri* (.msm dosyaları), belirli kitaplıkları dağıtmak için kullanabileceğiniz ve uygulamanızın Windows Installer (.msi) dosyasına dahil.

Yeniden dağıtılabilir paket dosyası tüm belirli bir sistem mimarisi için Visual C++ kitaplıklarını yükler. Örneğin, uygulamanız için x64 oluşturulursa, uygulamanızın kullandığı tüm Visual C++ kitaplıklarını yüklemek için vcredist_x64.exe yeniden dağıtılabilir paketi kullanabilirsiniz. Uygulamanızı yüklemeden önce bir önkoşul olarak yeniden dağıtılabilir paketi çalıştırmak için uygulama Yükleyicinizle programlayabilirsiniz.

Bir Windows Installer uygulama kurulum dosyası içinde belirli bir Visual C++ Kitaplığı için Kurulum mantığının eklenmesi bir birleştirme modülü sağlar. Uygulamanızın gerektirdiği sayıda veya az sayıda birleştirme modüllerini içerebilir. Birleştirme modüllerini dağıtım ikili boyutu en aza indirmek, ihtiyacınız olduğunda kullanın.

Statik kitaplıklar yerine uygulamanızdaki dll kitaplığı kullanma ve merkezi kullanın yeniden dağıtılabilir bir paket ya da birleştirme modüllerini kullanarak merkezi dağıtım, Visual C++ kitaplıklarının otomatik olarak güncelleştirmek Windows Update sağladığından, öneririz yerel dağıtım yerine dağıtım.

## <a name="local-deployment"></a>Yerel Dağıtım

Yerel dağıtımda, kitaplık dosyaları yürütülebilir dosya ile birlikte uygulama klasörüne yüklenir. Her sürümün dosya adı, sürüm numarası içerdiği için Visual C++ yeniden dağıtılabilir kitaplıkların farklı sürümleri aynı klasöre yüklenebilir. Örneğin, 12 C++ çalışma zamanı kitaplığı msvcp120.dll ve sürüm 14 msvcp140.dll sürümüdür.

Bir kitaplık olarak bilinen birden çok ek DLL'leri arasında yayılıyor olabilir *nokta kitaplıkları*. Örneğin, Visual Studio 2017 sürüm 15.6 yayımlanan standart Kitaplığı'ndaki bazı işlevler msvcp140.dll ABI uyumluluğu korumak için msvcp140_1.dll eklendi. Visual Studio 2017 sürüm 15.6 (araç takımı 14.13) veya Visual Studio 2017'den sonraki bir araç takımı kullanırsanız, bu nokta kitaplıklar ve bunun yanı sıra ana kitaplık yerel olarak dağıtma gerekebilir. ABI değiştiğinde bu ayrı nokta kitaplıklar ardından temel kitaplığı sonraki ana sürümüne alınır.

Microsoft otomatik olarak kullanılamaz çünkü Visual C++ kitaplıklarının güncelleştirme yerel olarak dağıtılan, şu kitaplıkların yerel dağıtımını önermiyoruz. Yeniden dağıtılabilir kitaplıkların yerel dağıtımını kullanmaya karar verirseniz, yerel olarak dağıtılan kitaplıkları otomatik olarak güncelleştirmeyle ilgili kendi yönteminizi uygulamanızı öneririz.

## <a name="static-linking"></a>Statik Bağlama

Dinamik olarak bağlı kitaplıklarına ek olarak, Visual Studio kitaplıklarını çoğunu statik kitaplıklar sağlar. Statik olarak statik bir kitaplık kullanarak, yani bağlantı, kitaplık nesnesi kodu uygulamaya doğrudan bağlantı. Bu bir DLL bağımlılık olmadan tek bir ikili oluşturur, böylece Visual C++ Kitaplık dosyalarını ayrı ayrı dağıtmanız gerekmez. Statik olarak bağlanan kitaplıklar yerinde güncelleştirilemediğinden ancak, bu yaklaşım önermiyoruz. Statik bağlama kullanır ve bağlı bir kitaplığı güncelleştirmek isterseniz, uygulamanızı yeniden derlemeniz ve yeniden dağıtmanız gerekir.

## <a name="troubleshooting-deployment-issues"></a>Dağıtım sorunlarını giderme

Visual C++ kitaplıklarının yüklenme sırasını sistem bağlıdır. Yükleyici sorunlarını tanılamak için depends.exe veya where.exe kullanın. Daha fazla bilgi için [dinamik bağlantı kitaplığı arama sırası (Windows)](/windows/desktop/Dlls/dynamic-link-library-search-order).

## <a name="see-also"></a>Ayrıca bkz.

- [Masaüstü uygulamalarını dağıtma](deploying-native-desktop-applications-visual-cpp.md)
- [Evrensel CRT dağıtımı](universal-crt-deployment.md)
