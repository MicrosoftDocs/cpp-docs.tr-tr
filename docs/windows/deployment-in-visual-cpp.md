---
title: Visual C++ üzerinde Dağıtım
ms.date: 05/11/2018
helpviewer_keywords:
- deploying applications [C++]
- application deployment [C++]
ms.assetid: d4b4ffc0-d2bd-4e4a-84a6-62f1c26f6a09
ms.openlocfilehash: 67d5c7b0772eda55d1b653bd73f95ac93e31e644
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514814"
---
# <a name="deployment-in-visual-c"></a>Visual C++ üzerinde Dağıtım

Uygulamanızın geliştirme bilgisayarınızdan farklı bir bilgisayara yüklenmesi *dağıtım*olarak bilinir. Bir görsel C++ uygulamayı başka bir bilgisayara dağıttığınızda, hem uygulamayı hem de bağımlı olduğu kitaplık dosyalarını yüklemelisiniz. Visual C++ Studio, Visual kitaplıklarını uygulamanızla birlikte dağıtmak için üç yol sağlar: *merkezi dağıtım*, *Yerel dağıtım*ve *statik bağlama*. Merkezi dağıtım, kitaplık dosyalarını, Windows Update hizmetinin otomatik olarak güncelleştirebileceği Windows dizinine koyar. Yerel dağıtım, kitaplık dosyalarını uygulamanızla aynı dizine koyar. Onları güncelleştirmek için yerel olarak dağıtılan tüm kitaplıkları kendiniz yeniden dağıtmanız gerekir. Statik bağlama, kitaplık kodunu uygulamanıza bağlar. Statik bağlama kullandığınızda kitaplıklara yönelik güncelleştirmelerden yararlanmak için uygulamanızı yeniden derlemeniz ve yeniden dağıtmanız gerekir.

Visual Studio 2015 ' de, Microsoft C çalışma zamanı kitaplığı sürüme özgü yerel kitaplık bileşenlerine yeniden düzenlenmiş ve artık Windows 'un bir parçası olan yeni bir Universal C çalışma zamanı kitaplığı. Evrensel CRT dağıtımı hakkında daha fazla bilgi için bkz. [UNIVERSAL CRT dağıtımı](universal-crt-deployment.md).

## <a name="central-deployment"></a>Merkezi Dağıtım

Merkezi dağıtımda, kitaplık DLL dosyaları Windows\System32 dizinine veya x64 sistemlerinde 32 bitlik kitaplık dosyaları için Windows\SysWow64 dizininde yüklüdür. Microsoft, merkezi olarak dağıtılan kitaplıklarını otomatik olarak güncelleştirir. Yerel olarak C++ dağıtılan veya statik olarak bağlanan görsel kitaplıklar için güncelleştirmeleri sağlamanız gerekir.

Visual C++ kitaplıklarını merkezi olarak dağıtmak için, bu iki kaynaktan birini yüklemek üzere dosyaları kullanabilirsiniz:

- Sıkıştırılmış biçimdeki tüm Visual C++ yeniden dağıtılabilir kitaplıkları içeren tek başına komut satırı yürütülebilir dosyaları olan *yeniden dağıtılabilir paket* dosyaları veya

- *Yeniden dağıtılabilir birleştirme modülleri* (. msm dosyaları), belirli kitaplıkları dağıtmak için kullanabileceğiniz ve uygulamanızın Windows Installer (. msi) dosyasına dahil ettiğiniz.

Yeniden dağıtılabilir bir paket dosyası, belirli bir sistem C++ mimarisi Için tüm görsel kitaplıkları kurar. Örneğin, uygulamanız x64 için derlenip, uygulamanızın kullandığı tüm görsel C++ kitaplıkları yüklemek için vcredist_x64. exe yeniden dağıtılabilir paketini kullanabilirsiniz. Uygulamanızı yüklemeden önce, uygulama yükleyicinizi yeniden dağıtılabilir paketi bir önkoşul olarak çalıştıracak şekilde programlayabilirsiniz.

Birleştirme modülü, bir Windows Installer uygulama Kurulum dosyasında belirli bir görsel C++ kitaplık için kurulum mantığının eklenmesini sunar. Uygulamanızın gerektirdiği kadar çok sayıda birleştirme modülü ekleyebilirsiniz. Dağıtım ikili dosyalarınız boyutunu en aza indirmenize gerek duyduğunuzda birleştirme modüllerini kullanın.

Yeniden dağıtılabilir bir paket veya birleştirme modülleri kullanılarak merkezi dağıtım, C++ Windows Update otomatik olarak güncelleştirilmesini sağladığından, uygulamanızdaki kitaplık dll 'lerini statik kitaplıklar yerine kullanmanızı ve bunu kullanmanızı öneririz. Yerel dağıtım yerine merkezi dağıtım.

## <a name="local-deployment"></a>Yerel Dağıtım

Yerel dağıtımda, kitaplık dosyaları, çalıştırılabilir dosyayla birlikte uygulama klasörünüze yüklenir. Her sürümün dosya adı C++ sürüm numarasını Içerdiğinden, Visual yeniden dağıtılabilir kitaplıkların farklı sürümleri aynı klasöre yüklenebilir. Örneğin, C++ çalışma zamanı kitaplığının 12. sürümü Msvcp120. dll, sürüm 14 ise msvcp140. dll ' dir.

Bir kitaplık, *nokta kitaplıkları*olarak bilinen birden fazla ek dll 'ye dağılmış olabilir. Örneğin, msvcp140. dll ' nin ABı uyumluluğunu korumak için Visual Studio 2017 sürüm 15,6 ' de yayınlanan standart kitaplıkta bazı işlevler msvcp140_1. dll ' ye eklenmiştir. Visual Studio 2017 sürüm 15,6 (araç takımı 14,13) veya daha sonraki bir araç takımını Visual Studio 2017 ' ten kullanıyorsanız, bu nokta kitaplıklarını ve ana Kitaplığı yerel olarak dağıtmanız gerekebilir. Bu ayrı nokta kitaplıkları, ABı değiştiğinde temel kitaplığın bir sonraki ana sürümüne aktarılır.

Microsoft yerel olarak dağıtılan Visual C++ kitaplıklarını otomatik olarak güncelleştiremediğinden, bu kitaplıkların yerel dağıtımını önermiyoruz. Yeniden dağıtılabilir kitaplıkların yerel dağıtımını kullanmaya karar verirseniz, yerel olarak dağıtılan kitaplıkları otomatik olarak güncelleştirmeyle ilgili kendi yönteminizi uygulamanızı öneririz.

## <a name="static-linking"></a>Statik Bağlama

Visual Studio, dinamik olarak bağlı kitaplıklara ek olarak, kütüphanelerinin çoğunu statik kitaplıklar olarak sağlar. Statik bir kitaplığı uygulamanıza statik olarak bağlayabilirsiniz, diğer bir deyişle, kitaplık nesne kodunu doğrudan uygulamaya bağlayabilirsiniz. Bu, DLL bağımlılığı olmayan tek bir ikili oluşturur, böylece görsel C++ kitaplık dosyalarını ayrı olarak dağıtmanız gerekmez. Ancak, statik olarak bağlı kitaplıklar yerinde güncelleştirilemediğinden bu yaklaşımı önermiyoruz. Statik bağlama kullanır ve bağlı bir kitaplığı güncelleştirmek isterseniz, uygulamanızı yeniden derlemeniz ve yeniden dağıtmanız gerekir.

## <a name="troubleshooting-deployment-issues"></a>Dağıtım sorunlarını giderme

Görsel C++ kitaplıkların yük sıralaması sisteme bağımlıdır. Yükleyici sorunlarını tanılamak için depends.exe veya where.exe kullanın. Daha fazla bilgi için bkz. [dinamik bağlantı kitaplığı arama sırası (Windows)](/windows/win32/Dlls/dynamic-link-library-search-order).

## <a name="see-also"></a>Ayrıca bkz.

- [Masaüstü uygulamaları dağıtma](deploying-native-desktop-applications-visual-cpp.md)
- [Evrensel CRT dağıtımı](universal-crt-deployment.md)
