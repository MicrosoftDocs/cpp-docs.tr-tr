---
title: Evrensel CRT dağıtımı
description: Uygulamanız için Evrensel CRT kitaplığı 'nın nasıl, ne zaman ve nereye dağıtılacağını öğrenin.
ms.date: 10/23/2020
helpviewer_keywords:
- deploying the CRT [C++]
- application CRT deployment [C++]
ms.openlocfilehash: 50ab23f3b0276b058685e9c9ef6634caf5a96186
ms.sourcegitcommit: bf54b407169900bb668c85a67b31dbc0f069fe65
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2020
ms.locfileid: "92497213"
---
# <a name="universal-crt-deployment"></a>Evrensel CRT dağıtımı

Visual Studio .NET Visual Studio 2013 aracılığıyla, C++ derleyicisinin ve araçların her ana sürümü, Microsoft C Runtime (CRT) kitaplığının yeni ve tek başına bir sürümünü içeriyordu. CRT 'nın bu tek başına sürümleri, birbirinden bağımsız olarak ve çeşitli derecelerde birbirleriyle uyumsuzdur. Örneğin, Visual Studio 2012 tarafından kullanılan CRT kitaplığı sürüm 11, msvcr110.dll adı ve Visual Studio 2013 tarafından kullanılan CRT, msvcr120.dll adlı sürüm 12 idi. Visual Studio 2015 ' den başlayarak artık böyle bir durum değildir. Visual Studio 2015 ve sonraki Visual Studio sürümleri tek bir Evrensel CRT kullanır.

Universal CRT (UCRT), bir Microsoft Windows işletim sistemi bileşenidir. Windows 10 ve Windows Server 2016 veya üzeri sürümlerde işletim sisteminin bir parçası olarak dahil edilmiştir. UıCRT, hala genişletilmiş destek içinde olan eski işletim sistemlerinde Windows Update kullanılarak kullanılabilir. Evrensel CRT 'nin yerel dağıtımı, bazı kısıtlamalarla desteklenir.

## <a name="central-deployment"></a>Merkezi dağıtım

Evrensel CRT 'yi merkezi olarak yüklemek için tercih edilen yöntem, Microsoft Windows Update kullanmaktır. Evrensel CRT, tüm desteklenen Microsoft Windows işletim sistemleri için önerilen bir güncelleştirmedir, bu nedenle varsayılan olarak çoğu makine bunu normal güncelleştirme sürecinin bir parçası olarak yükler. Universal CRT 'nin ilk sürümü [KB2999226](https://support.microsoft.com/kb/2999226)idi. [KB3118401](https://support.microsoft.com/kb/3118401)' de çeşitli hata düzeltmeleri içeren daha sonraki bir güncelleştirme yapılmıştır ve daha fazla hata düzeltmesi ve yeni özelliklerle ilgili ek güncelleştirmeler yapılmıştır. Daha son güncelleştirmeler için, [support.Microsoft.com](https://support.microsoft.com) Universal C Runtime veya Universal CRT için arama yapın.

Tüm Microsoft Windows bilgisayarları Windows Update kullanarak güncelleştirmeleri düzenli olarak yüklemez ve bazıları önerilen tüm güncelleştirmeleri yükleyemeyebilir. Bu makinelerde Visual Studio 2015 ve üzeri C++ araç kümeleri kullanılarak oluşturulan uygulamaların kullanımını desteklemek için çevrimdışı dağıtım için kullanılabilen Evrensel CRT yeniden dağıtılabilir dosyalar bulunur. Bu yeniden dağıtılabilir dosyalar, yukarıdaki KB bağlantılarından birinden indirilebilir. Evrensel CRT yeniden dağıtılabilir, makinenin geçerli hizmet paketine güncelleştirilmesini gerektirir. Bu nedenle, örneğin, Windows 7 için yeniden dağıtılabilir Windows 7 RTM 'ye değil yalnızca Windows 7 SP1 'e yüklenir.

Evrensel CRT, C++ kitaplıklarının temel bir bağımlılığı olduğundan, yeniden dağıtılabilir Visual C++ (VCRedist), önceden yüklenmiş bir makineye sahip olmayan makinelere Evrensel CRT (sürüm 10.0.10240) öğesinin ilk sürümünü yüklenir. Bu sürüm, C++ Kitaplığı bağımlılıklarını karşılamak için yeterlidir. Uygulamanız Universal CRT 'nin daha yeni bir sürümüne bağımlıysa, makinenizi tamamen güncel hale getirmek veya bu sürümü açıkça yüklemek için Windows Update kullanmanız gerekir. Birden çok zorunlu yeniden başlatmaların oluşmasını önlemek için, VCRedist 'i yüklemeden önce Windows Update veya MSU aracılığıyla Universal C çalışma zamanı 'nı yüklemeniz en iyisidir.

Tüm işletim sistemleri, Windows Update aracılığıyla en son Evrensel C çalışma zamanına uygun değildir. Windows 10 ' da, merkezi olarak dağıtılan sürüm işletim sisteminin sürümüyle eşleşir. Evrensel C çalışma zamanını daha fazla güncelleştirmek için işletim sistemini güncelleştirmeniz gerekir. Windows Vista Windows 8.1 aracılığıyla, kullanılabilir en son Evrensel C çalışma zamanı, ek düzeltmeler (sürüm 10.0.14393) ile Windows 10 yıldönümü güncelleştirmesi 'nde yer alan sürümü temel alır.

## <a name="local-deployment"></a>Yerel dağıtım

Evrensel CRT 'nin yerel dağıtımı desteklenir, ancak hem performans hem de güvenlik nedenleriyle önerilmez. Yerel dağıtım için dll 'Ler, \\ \\ bilgisayar mimarisine göre Windows Kits 10 Redist \\ UCRT \\ dll alt dizininde Windows SDK bir parçası olarak dahil edilir. Gerekli dll 'Ler ucrtbase.dll ve API-MS-Win-. dll adlı bir APISet iletici dll kümesi içerir \* . Her işletim sisteminde gereken dll 'Ler kümesi farklılık gösterir. Yerel olarak dağıtırken tüm dll 'Leri eklemeniz önemle tavsiye edilir.

Yerel dağıtımda şunları göz önünde bulundurulması için iki kısıtlama vardır:

- Windows 10 ' da, bir uygulama Evrensel CRT 'nın uygulama yerel kopyasını içerse bile, Sistem dizinindeki Evrensel CRT her zaman kullanılır. Evrensel CRT, Windows 10 ' da bir çekirdek işletim sistemi bileşeni olduğundan, yerel kopya daha yeni olduğunda bile bu doğrudur.

- Windows 8 ' den önceki Windows sürümlerinde Evrensel CRT, ana uygulama yürütülebilir dosyasının dizininden başka bir dizinde bulunuyorsa bir eklenti ile yerel olarak paketlenemez. APISet iletici dll 'Leri bu durumda ucrtbase.dll başarıyla çözümlenemiyor. Bazı önerilen alternatif çözümler şunlardır:

  - Evrensel CRT 'yi statik olarak bağlayın,
  - Evrensel CRT 'yi merkezi olarak dağıtma veya
  - Evrensel CRT dosyalarını uygulamayla aynı dizine yerleştirin.

## <a name="deployment-on-microsoft-windows-xp"></a>Microsoft Windows XP 'de dağıtım

Visual Studio 2015 ve Visual Studio 2017, Microsoft Windows XP 'de kullanım için yazılım geliştirmeyi desteklemeye devam eder. Bu geliştirmeyi desteklemek için Universal CRT 'nin bir sürümü Microsoft Windows XP 'de çalışır. Microsoft Windows XP işletim sistemi artık temel veya genişletilmiş destek değildir, bu nedenle Universal CRT 'nin Microsoft Windows XP 'de merkezi dağıtımı diğer işletim sistemlerinden farklıdır.

Yeniden dağıtılabilir Visual C++ Windows XP 'ye yüklendiğinde, Evrensel CRT 'yı ve tüm bağımlılıklarını sistem dizinine doğrudan kurar. Hiçbir Windows Update yüklemez veya buna bağlı değildir. Yeniden dağıtılabilir birleştirme modülleri olan Microsoft_VC*Version*_CRT_ \* . msm dosyaları aynı şekilde yapılır.

Windows XP 'de Evrensel CRT 'nin yerel dağıtımı, desteklenen diğer işletim sistemleriyle aynıdır.

## <a name="see-also"></a>Ayrıca bkz.

- [Visual C++ üzerinde Dağıtım](deployment-in-visual-cpp.md)
