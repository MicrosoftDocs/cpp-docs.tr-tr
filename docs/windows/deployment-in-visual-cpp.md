---
description: 'Hakkında daha fazla bilgi edinin Visual C++: dağıtım'
title: Visual C++ üzerinde Dağıtım
ms.date: 05/11/2018
helpviewer_keywords:
- deploying applications [C++]
- application deployment [C++]
ms.assetid: d4b4ffc0-d2bd-4e4a-84a6-62f1c26f6a09
ms.openlocfilehash: 2510350fa45a6f249d61040f374878ce20e68f67
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327094"
---
# <a name="deployment-in-visual-c"></a>Visual C++ üzerinde Dağıtım

Uygulamanızın geliştirme bilgisayarınızdan farklı bir bilgisayara yüklenmesi *dağıtım* olarak bilinir. Bir Visual C++ uygulamasını başka bir bilgisayara dağıttığınızda, hem uygulamayı hem de bağımlı olduğu kitaplık dosyalarını yüklemelisiniz. Visual Studio, Visual C++ kitaplıklarını uygulamanızla birlikte dağıtmak için üç yol sağlar: *merkezi dağıtım*, *Yerel dağıtım* ve *statik bağlama*. Merkezi dağıtım, kitaplık dosyalarını, Windows Update hizmetinin otomatik olarak güncelleştirebileceği Windows dizinine koyar. Yerel dağıtım, kitaplık dosyalarını uygulamanızla aynı dizine koyar. Onları güncelleştirmek için yerel olarak dağıtılan tüm kitaplıkları kendiniz yeniden dağıtmanız gerekir. Statik bağlama, kitaplık kodunu uygulamanıza bağlar. Statik bağlama kullandığınızda kitaplıklara yönelik güncelleştirmelerden yararlanmak için uygulamanızı yeniden derlemeniz ve yeniden dağıtmanız gerekir.

Visual Studio 2015 ' de, Microsoft C çalışma zamanı kitaplığı sürüme özgü yerel kitaplık bileşenlerine yeniden düzenlenmiş ve artık Windows 'un bir parçası olan yeni bir Universal C çalışma zamanı kitaplığı. Evrensel CRT dağıtımı hakkında daha fazla bilgi için bkz. [UNIVERSAL CRT dağıtımı](universal-crt-deployment.md).

## <a name="central-deployment"></a>Merkezi Dağıtım

Merkezi dağıtımda, kitaplık DLL dosyaları Windows\System32 dizinine veya x64 sistemlerinde 32 bitlik kitaplık dosyaları için Windows\SysWow64 dizininde yüklüdür. Microsoft, merkezi olarak dağıtılan kitaplıklarını otomatik olarak güncelleştirir. Yerel olarak dağıtılan veya statik olarak bağlanmış Visual C++ kitaplıklar için güncelleştirmeleri sağlamanız gerekir.

Visual C++ kitaplıklarını merkezi olarak dağıtmak için, bu iki kaynaktan birini yüklemek üzere dosyaları kullanabilirsiniz:

- Sıkıştırılmış biçimdeki tüm Visual C++ yeniden dağıtılabilir kitaplıkları içeren tek başına komut satırı yürütülebilir dosyaları olan *yeniden dağıtılabilir paket* dosyaları veya

- Belirli kitaplıkları dağıtmak için kullanabileceğiniz ve uygulamanızın Windows Installer (. msi) dosyasına dahil ettiğiniz *yeniden dağıtılabilir birleştirme modülleri* (. msm dosyaları).

Yeniden dağıtılabilir bir paket dosyası, belirli bir sistem mimarisine yönelik tüm Visual C++ kitaplıklarını yüklüyor. Örneğin, uygulamanız x64 için derlenip, uygulamanızın kullandığı tüm Visual C++ kitaplıklarını yüklemek için vcredist_x64.exe yeniden dağıtılabilir paketi kullanabilirsiniz. Uygulamanızı yüklemeden önce, uygulama yükleyicinizi yeniden dağıtılabilir paketi bir önkoşul olarak çalıştıracak şekilde programlayabilirsiniz.

Birleştirme modülü, bir Windows Installer uygulama Kurulum dosyasında belirli bir Visual C++ kitaplığı için kurulum mantığının eklenmesini sunar. Uygulamanızın gerektirdiği kadar çok sayıda birleştirme modülü ekleyebilirsiniz. Dağıtım ikili dosyalarınız boyutunu en aza indirmenize gerek duyduğunuzda birleştirme modüllerini kullanın.

Yeniden dağıtılabilir bir paket veya birleştirme modülleri kullanılarak merkezi dağıtım Windows Update Visual C++ kitaplıklarını otomatik olarak güncelleştirebilmesini sağladığından, uygulamanızdaki kitaplık dll 'Lerini statik kitaplıklar yerine kullanmanız ve yerel dağıtım yerine merkezi dağıtım kullanmanız önerilir.

## <a name="local-deployment"></a>Yerel Dağıtım

Yerel dağıtımda, kitaplık dosyaları, çalıştırılabilir dosyayla birlikte uygulama klasörünüze yüklenir. Her sürümün dosya adı sürüm numarasını içerdiğinden, Visual C++ yeniden dağıtılabilir kitaplıkların farklı sürümleri aynı klasöre yüklenebilir. Örneğin, C++ çalışma zamanı kitaplığının 12. sürümü msvcp120.dll ve sürüm 14 msvcp140.dll.

Bir kitaplık, *nokta kitaplıkları* olarak bilinen birden fazla ek dll 'ye dağılmış olabilir. Örneğin, msvcp140.dll uyumluluğunu korumak için Visual Studio 2017 sürüm 15,6 ' de yayınlanan standart kitaplıkta bazı işlevler msvcp140_1.dll eklenmiştir. Visual Studio 2017 sürüm 15,6 (araç takımı 14,13) veya daha sonraki bir araç takımını Visual Studio 2017 ' ten kullanıyorsanız, bu nokta kitaplıklarını ve ana Kitaplığı yerel olarak dağıtmanız gerekebilir. Bu ayrı nokta kitaplıkları, ABı değiştiğinde temel kitaplığın bir sonraki ana sürümüne aktarılır.

Microsoft yerel olarak dağıtılan Visual C++ kitaplıklarını otomatik olarak güncelleştiremediğinden, bu kitaplıkların yerel dağıtımını önermiyoruz. Yeniden dağıtılabilir kitaplıkların yerel dağıtımını kullanmaya karar verirseniz, yerel olarak dağıtılan kitaplıkları otomatik olarak güncelleştirmeyle ilgili kendi yönteminizi uygulamanızı öneririz.

## <a name="static-linking"></a>Statik Bağlama

Visual Studio, dinamik olarak bağlı kitaplıklara ek olarak, kütüphanelerinin çoğunu statik kitaplıklar olarak sağlar. Statik bir kitaplığı uygulamanıza statik olarak bağlayabilirsiniz, diğer bir deyişle, kitaplık nesne kodunu doğrudan uygulamaya bağlayabilirsiniz. Bu, DLL bağımlılığı olmayan tek bir ikili oluşturur, böylece Visual C++ Kitaplığı dosyalarını ayrı olarak dağıtmanız gerekmez. Ancak, statik olarak bağlı kitaplıklar yerinde güncelleştirilemediğinden bu yaklaşımı önermiyoruz. Statik bağlama kullanır ve bağlı bir kitaplığı güncelleştirmek isterseniz, uygulamanızı yeniden derlemeniz ve yeniden dağıtmanız gerekir.

## <a name="troubleshooting-deployment-issues"></a>Dağıtım sorunlarını giderme

Visual C++ kitaplıklarının yük sıralaması sisteme bağımlıdır. Yükleyici sorunlarını tanılamak için depends.exe veya where.exe kullanın. Daha fazla bilgi için bkz. [dinamik bağlantı kitaplığı arama sırası (Windows)](/windows/win32/Dlls/dynamic-link-library-search-order).

## <a name="see-also"></a>Ayrıca bkz.

- [Masaüstü uygulamaları dağıtma](deploying-native-desktop-applications-visual-cpp.md)
- [Evrensel CRT dağıtımı](universal-crt-deployment.md)
