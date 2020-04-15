---
title: Visual C++ üzerinde Dağıtım
ms.date: 05/11/2018
helpviewer_keywords:
- deploying applications [C++]
- application deployment [C++]
ms.assetid: d4b4ffc0-d2bd-4e4a-84a6-62f1c26f6a09
ms.openlocfilehash: 5c4b75a65fcfb34a4988b176ffcb5b2afcb7ea13
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377373"
---
# <a name="deployment-in-visual-c"></a>Visual C++ üzerinde Dağıtım

Uygulamanızın geliştirme bilgisayarınız dışındaki bir bilgisayara yüklenmesi *dağıtım*olarak bilinir. Görsel C++ uygulamasını başka bir bilgisayara dağıttığınızda, hem uygulamayı hem de bağlı olduğu kitaplık dosyalarını yüklemeniz gerekir. Visual Studio, Visual C++ kitaplıklarını uygulamanızla birlikte dağıtmanın üç yolunu sağlar: *merkezi dağıtım,* *yerel dağıtım*ve *statik bağlama.* Merkezi dağıtım, kitaplık dosyalarını Windows Update hizmetinin bunları otomatik olarak güncelleştirebileceği Windows dizininin altına koyar. Yerel dağıtım, kitaplık dosyalarını uygulamanızla aynı dizine koyar. Yerel olarak dağıtılan tüm kitaplıkları güncelleştirmek için kendiniz yeniden dağıtmanız gerekir. Statik bağlantı kitaplık kodunu uygulamanıza bağlar. Statik bağlantı kullandığınızda kitaplıklara yapılan güncelleştirmelerden yararlanmak için uygulamanızı yeniden derlemeniz ve yeniden dağıtmanız gerekir.

Visual Studio 2015'te, Microsoft C Runtime kitaplığı sürüme özgü yerel kitaplık bileşenlerine ve artık Windows'un bir parçası olan yeni bir Universal C Runtime kitaplığı olarak yeniden dizine dönüştürüldü. Evrensel CRT dağıtımı yla ilgili ayrıntılar için [Evrensel CRT dağıtımına](universal-crt-deployment.md)bakın.

## <a name="central-deployment"></a>Merkezi Dağıtım

Merkezi dağıtımda, kitaplık DLL dosyaları Windows\System32 dizinine veya x64 sistemlerindeki 32 bit kitaplık dosyaları için Windows\SysWow64 dizinine yüklenir. Microsoft, merkezi olarak dağıtılan kitaplıklarını otomatik olarak güncelleştirir. Yerel olarak dağıtılan veya statik olarak bağlı Olan Visual C++ kitaplıkları için güncelleştirmeleri sağlamanız gerekir.

Visual C++ kitaplıklarını merkezi olarak dağıtmak için dosyaların yüklenmesi için aşağıdaki iki kaynaktan birini kullanabilirsiniz:

- Tüm Visual C++ yeniden dağıtılabilir kitaplıkları sıkıştırılmış biçimde içeren tek başına komut satırı yürütülebilir dosyalar olan *yeniden dağıtılabilir paket* dosyaları veya

- Belirli kitaplıkları dağıtmak için kullanabileceğiniz ve uygulamanızın Windows Installer (.msi) dosyasına eklediğiniz *yeniden dağıtılabilir birleştirme modülleri* (.msm dosyaları).

Yeniden dağıtılabilir paket dosyası, belirli bir sistem mimarisi için tüm Visual C++ kitaplıklarını yükler. Örneğin, uygulamanız x64 için oluşturulmuşsa, uygulamanızın kullandığı tüm Visual C++ kitaplıklarını yüklemek için vcredist_x64.exe yeniden dağıtılabilir paketini kullanabilirsiniz. Uygulamanızı yüklemeden önce yeniden dağıtılabilir paketi ön koşul olarak çalıştıracak şekilde uygulama yükleyicinizi programlayabilirsiniz.

Birleştirme modülü, belirli bir Visual C++ kitaplığı için kurulum mantığının Windows Installer uygulama kurulum dosyasına eklenmesini sağlar. Uygulamanızın gerektirdiği kadar çok veya birkaç birleştirme modülü ekleyebilirsiniz. Dağıtım ikililerinizin boyutunu en aza indirmeniz gerektiğinde birleştirme modüllerini kullanın.

Yeniden dağıtılabilir bir paket veya birleştirme modülleri kullanarak merkezi dağıtım, Windows Update'in Visual C++ kitaplıklarını otomatik olarak güncelleştirmesini sağladığından, statik kitaplıklar yerine uygulamanızdaki kitaplık DL'lerini kullanmanızı ve yerel dağıtım yerine merkezi dağıtım kullanmanızı öneririz.

## <a name="local-deployment"></a>Yerel Dağıtım

Yerel dağıtımda, kitaplık dosyaları yürütülebilir dosyayla birlikte uygulama klasörünüze yüklenir. Her sürümün dosya adı sürüm numarasını içerdiğinden, Visual C++ yeniden dağıtılabilir kitaplıklarının farklı sürümleri aynı klasöre yüklenebilir. Örneğin, C++ çalışma zamanı kitaplığı sürüm 12 msvcp120.dll ve sürüm 14 msvcp140.dll olduğunu.

Kitaplık, *nokta kitaplıkları*olarak bilinen birden çok ek DL'ye yayılabilir. Örneğin, Visual Studio 2017 sürüm 15.6'da yayımlanan standart kitaplıktaki bazı işlevler, MSVCP140.dll'nin ABI uyumluluğunu korumak için msvcp140_1.dll'ye eklendi. Visual Studio 2017 sürüm 15.6 (araç seti 14.13) veya Visual Studio 2017'den sonraki bir araç setini kullanıyorsanız, bu nokta kitaplıklarını ve ana kitaplığı yerel olarak dağıtmanız gerekebilir. Bu ayrı nokta kitaplıkları, ABI değiştiğinde temel kitaplığın bir sonraki ana sürümüne kaydedilir.

Microsoft yerel olarak dağıtılan Visual C++ kitaplıklarını otomatik olarak güncelleştiremediğinden, bu kitaplıkların yerel olarak dağıtılmasını önermiyoruz. Yeniden dağıtılabilir kitaplıkların yerel dağıtımını kullanmaya karar verirseniz, yerel olarak dağıtılan kitaplıkları otomatik olarak güncelleştirmeyle ilgili kendi yönteminizi uygulamanızı öneririz.

## <a name="static-linking"></a>Statik Bağlama

Visual Studio, dinamik olarak birbirine bağlı kitaplıklara ek olarak, kütüphanelerinin çoğunu statik kitaplıklar olarak sağlar. Statik kitaplığı uygulamanıza statik olarak bağlayabilirsiniz, diğer bir süre önce kitaplık nesne kodunu doğrudan uygulamaya bağlayabilirsiniz. Bu, Visual C++ kitaplık dosyalarını ayrı olarak dağıtmanız gerekmeden DLL bağımlılığı olmayan tek bir ikili oluşturur. Ancak, statik olarak bağlı kitaplıklar yerinde güncelleştirilemediği için bu yaklaşımı önermiyoruz. Statik bağlama kullanır ve bağlı bir kitaplığı güncelleştirmek isterseniz, uygulamanızı yeniden derlemeniz ve yeniden dağıtmanız gerekir.

## <a name="troubleshooting-deployment-issues"></a>Sorun giderme dağıtım sorunları

Visual C++ kitaplıklarının yük sırası sisteme bağlıdır. Yükleyici sorunlarını tanılamak için depends.exe veya where.exe kullanın. Daha fazla bilgi için Dinamik [Bağlantı Kitaplığı Arama Sırası (Windows)](/windows/win32/Dlls/dynamic-link-library-search-order)'ye bakın.

## <a name="see-also"></a>Ayrıca bkz.

- [Masaüstü Uygulamalarını Dağıtma](deploying-native-desktop-applications-visual-cpp.md)
- [Evrensel CRT dağıtımı](universal-crt-deployment.md)
