---
title: Visual C++ üzerinde dağıtım | Microsoft Docs
ms.custom: ''
ms.date: 05/11/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- deploying applications [C++]
- application deployment [C++]
ms.assetid: d4b4ffc0-d2bd-4e4a-84a6-62f1c26f6a09
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5b9dfdcdce618df3f2bfec64892f62aec20b6db9
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="deployment-in-visual-c"></a>Visual C++ üzerinde Dağıtım

Uygulamanızı geliştirme bilgisayarınızın dışında bir bilgisayarda yüklenmesi olarak bilinir *dağıtım*. Başka bir bilgisayara Visual C++ uygulamasını dağıttığınızda, uygulama ve bağımlı tüm kitaplık dosyalarını yüklemeniz gerekir. Visual Studio uygulamanızı birlikte Visual C++ kitaplıkları dağıtmak için üç yöntem sağlar: *merkezi dağıtım*, *yerel dağıtım*, ve *statik bağlama*. Merkezi dağıtım burada Windows Update hizmeti bunları otomatik olarak güncelleştirebilir kitaplık dosyaları Windows dizinindeki koyar. Yerel dağıtım kitaplık dosyaları uygulamanız ile aynı dizinde koyar. Yerel olarak dağıtılan tüm kitaplıkları yeniden dağıtmanız gerekir kendinize bunları güncelleştirin. Statik bağlama kitaplık kodu uygulamanıza bağlar. Yeniden derleyin ve statik bağlama kullandığınızda herhangi bir güncelleştirme kitaplıklara yararlanmak için uygulamanızı dağıtmanız gerekir.

Visual Studio 2015'te Microsoft C çalışma zamanı kitaplığı sürüme özgü yerel kitaplığı bileşenlerini ve şimdi Windows'un parçası olan yeni bir evrensel C çalışma zamanı kitaplığı bulunanad. Evrensel CRT dağıtımı hakkında daha fazla bilgi için bkz: [Evrensel CRT dağıtım](universal-crt-deployment.md).

## <a name="central-deployment"></a>Merkezi Dağıtım

Merkezi dağıtımında kitaplığı DLL dosyaları Windows\System32 dizininde veya x64 32 bit kitaplık dosyaları için yüklü sistemleri, Windows\SysWow64 dizini. Microsoft, merkezi olarak dağıtılan kitaplıklarını otomatik olarak güncelleştirir. Yerel olarak dağıtılan veya statik olarak bağlantılı Visual C++ kitaplıkları için güncelleştirmeleri sağlamanız gerekir.

Visual C++ kitaplıkları merkezi olarak dağıtmak için bu iki kaynak dosyaları için yüklemek için kullanabilirsiniz:

- *Yeniden dağıtılabilir paketi* sıkıştırılmış biçimde tüm Visual C++ yeniden dağıtılabilir kitaplıkları içeren tek başına komut satırı yürütülebilir dosyalar, dosyaların veya

- *Yeniden dağıtılabilir birleştirme modülleri* (.msm dosyaları), belirli kitaplıkları dağıtmak için kullanabileceğiniz ve uygulamanızın Windows Installer (.msi) dosyasına dahil.

Yeniden dağıtılabilir paket dosyası tüm belirli sistem mimarisi için Visual C++ kitaplıkları yükler. Örneğin, uygulamanız için x64 oluşturulursa, uygulamanızın kullandığı tüm Visual C++ kitaplıkları yüklemek için vcredist_x64.exe yeniden dağıtılabilir paketi kullanabilirsiniz. Uygulamanızı yüklemeden önce bir önkoşul olarak yeniden dağıtılabilir paketini çalıştırmak için uygulama yükleyicisi programlama yapabilirsiniz.

Bir birleştirme modülü eklenmesi, bir Windows Installer Uygulama Kurulumu dosyası içinde belirli bir Visual C++ Kitaplık için kurulum mantığı sağlar. Uygulamanızın gerektirdiği gibi kadar veya olabildiğince az sayıda birleştirme modülleri içerebilir. Birleştirme modüllerini dağıtımı ikili dosyaları boyutunu en aza indirmek gerektiğinde kullanın.

Statik kitaplıklar yerine, uygulamanızda DLL'leri kitaplığını kullanma ve merkezi kullanmak yeniden dağıtılabilir paketi ya da birleştirme modüllerini kullanarak merkezi dağıtım Visual C++ kitaplıkları otomatik olarak güncelleştirmek Windows Update sağladığından, öneririz yerel dağıtım yerine dağıtım.

## <a name="local-deployment"></a>Yerel Dağıtım

Yerel bir dağıtımda, kitaplık dosyaları, uygulama klasöründe yürütülebilir dosyası ile birlikte yüklenir. Her sürümün dosya adı, sürüm numarası içerdiği için Visual C++ yeniden dağıtılabilir kitaplıkları farklı sürümlerini aynı klasörde yüklenebilir. Örneğin, 12, C++ çalışma zamanı kitaplığı msvcp120.dll ve sürüm 14 msvcp140.dll sürümüdür.

Bir kitaplık olarak bilinen birden çok ek DLL'leri üzerinden yayılan *nokta kitaplıkları*. Örneğin, bazı işlevler Visual Studio 2017 sürüm 15,6 yayımlanan standart Kitaplığı'nda msvcp140_1.dll preverve için msvcp140.dll ABI uyumluluğunu eklendi. Visual Studio 2017 sürüm 15,6 (14.13 araç takımı) ya da Visual Studio 2017'den sonraki bir araç takımı kullanırsanız, bu nokta kitaplıklar ve bunun yanı sıra ana kitaplığı yerel olarak dağıtmak gerekebilir. ABI değiştirdiğinde bu ayrı nokta kitaplıklar ardından sonraki ana sürümüne yönelik temel kitaplık alınır.

Microsoft otomatik olarak yapılamıyor çünkü Visual C++ kitaplıkları güncelleştirme yerel olarak dağıtılan, bu kitaplıklar, yerel dağıtım önermiyoruz. Yeniden dağıtılabilir kitaplıkların yerel dağıtımını kullanmaya karar verirseniz, yerel olarak dağıtılan kitaplıkları otomatik olarak güncelleştirmeyle ilgili kendi yönteminizi uygulamanızı öneririz.

## <a name="static-linking"></a>Statik Bağlama

Dinamik olarak bağlı kitaplıkları yanı sıra, Visual Studio statik kitaplıklar başlatılamadığından çoğunu sağlar. Statik olarak statik kitaplık uygulamanıza, yani bağlayın, doğrudan uygulamaya kitaplığı nesne kodu bağlayın. Bu DLL bağımlılık olmadan tek bir ikili oluşturur, böylece Visual C++ Kitaplık dosyalarını ayrı olarak dağıtmanız gerekmez. Statik olarak bağlantılı kitaplıkları yerinde güncelleştirilemediğinden ancak, bu yaklaşım önermiyoruz. Statik bağlama kullanır ve bağlı bir kitaplığı güncelleştirmek isterseniz, uygulamanızı yeniden derlemeniz ve yeniden dağıtmanız gerekir.

## <a name="troubleshooting-deployment-issues"></a>Dağıtım sorunlarını giderme

Visual C++ kitaplıkları yüklenme sırasını sistem bağımlıdır. Yükleyici sorunlarını tanılamak için depends.exe veya where.exe kullanın. Daha fazla bilgi için bkz: [dinamik bağlantı kitaplığı arama sırası (Windows)](http://msdn.microsoft.com/library/windows/desktop/ms682586.aspx).

## <a name="see-also"></a>Ayrıca bkz.

- [Masaüstü uygulamaları dağıtma](../ide/deploying-native-desktop-applications-visual-cpp.md)
- [Evrensel CRT dağıtım](universal-crt-deployment.md)
