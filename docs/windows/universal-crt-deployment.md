---
title: Evrensel CRT dağıtımı
ms.date: 05/11/2018
helpviewer_keywords:
- deploying the CRT [C++]
- application CRT deployment [C++]
ms.openlocfilehash: 1f6e685cca65c4b31ac2e6147341c4b5a3fe8228
ms.sourcegitcommit: 6cf0c67acce633b07ff31b56cebd5de3218fd733
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/24/2019
ms.locfileid: "67344454"
---
# <a name="universal-crt-deployment"></a>Evrensel CRT dağıtımı

Visual Studio 2013 ile Visual Studio NET'ten her önemli bir C++ Derleyici ve araçların sürümü, Microsoft C çalışma zamanı (CRT) Kitaplığı'nın yeni bir tek başına sürüm eklemiştir. Bu tek başına sürümlerini CRT bağımsız gelen ve çeşitli derece, birbirleri ile uyumsuz. Örneğin, Visual Studio 2012 tarafından kullanılan CRT kitaplığı sürüm 11, adlandırılmış msvcr110.dll, ve Visual Studio 2013'ün tarafından kullanılan CRT sürüm 12 adlandırılmış msvcr120.dll şeklindeydi. Visual Studio 2015'te başlayarak, durum artık değildir. Visual Studio 2015 ve Visual Studio'nun tüm sonraki sürümler, bir evrensel CRT kullanın.

Evrensel CRT, Windows 10 işletim sisteminin bir parçası olarak dahil bir Microsoft Windows işletim sistemi bileşenidir. Windows Update'i kullanarak eski işletim sistemleri, Windows 8.1 ile Windows Vista için kullanılabilir. Evrensel CRT yerel dağıtımını, bazı kısıtlamalar ile desteklenir.

## <a name="central-deployment"></a>Merkezi dağıtım

Evrensel CRT merkezi olarak yüklemek için tercih edilen yöntem, Microsoft Windows Update kullanmaktır. Evrensel CRT tüm önerilen güncelleştirmesi Microsoft Windows işletim sistemleri, böylece göre varsayılan, normal güncelleştirme işleminin bir parçası yüklemek çoğu makineleri desteklenir. Evrensel CRT ilk sürümdü [KB2999226](https://support.microsoft.com/kb/2999226). İçinde bir sonraki güncelleştirme ile çeşitli hata düzeltmeleri yapıldı [KB3118401](https://support.microsoft.com/kb/3118401), ve daha fazla hata düzeltmeleri ve yeni özelliklerle ek güncelleştirmeler yapıldı. Daha yeni güncelleştirmeler için arama [support.microsoft.com](https://support.microsoft.com) Evrensel C çalışma zamanı veya evrensel CRT.

Tüm Microsoft Windows bilgisayarlarda Windows Update kullanarak düzenli olarak güncelleştirmeleri yüklemek ve bazıları tüm önerilen güncelleştirmeleri yüklenmez. Visual Studio 2015 kullanılarak oluşturulmuş ve üzeri uygulamaların kullanımını desteklemek üzere C++ araç takımları bu makinelerde vardır Evrensel CRT yeniden dağıtılabilir dosyaları çevrimdışı dağıtım için kullanılabilir. Yeniden dağıtılabilir dosyaları, yukarıdaki KB bağlantılardan birini yüklenebilir. Makine için geçerli hizmet paketi güncelleştirildiğini Evrensel CRT yeniden dağıtılabilir gerektirir. Bu nedenle, örneğin, Windows 7 için yeniden dağıtılabilir yalnızca Windows 7 SP1 değil Windows 7 RTM yüklenir.

Evrensel CRT temel bir bağımlılığı olduğundan C++ kitaplıkları, görsel C++ yeniden dağıtılabilir (VCRedist) yüklü bir hesabınız yoksa makinelerde ilk Evrensel CRT (sürüm 10.0.10240) sürümü yükler. Bu sürüm karşılamak üzere yeterli C++ kitaplık bağımlılıkları. Uygulamanızı Evrensel CRT daha yeni bir sürümüne bağlıdır, makinenizi tam olarak güncel duruma getirmek için Windows Update'i kullanın veya bu sürümünü açıkça yüklemeniz gerekir. Olası birden çok gerekli önlemek için VCRedist yükleme yeniden önce Windows Update veya bir MSU aracılığıyla Evrensel C çalışma zamanı yüklemek en iyisidir.

Tüm işletim sistemleri, Windows Update aracılığıyla en son Evrensel C çalışma zamanı için uygundur. Windows 10'da merkezi olarak dağıtılan sürümü işletim sistemi sürümü ile eşleşir. Ayrıca, Evrensel C çalışma zamanı güncelleştirmek için işletim sistemini güncelleştirmeniz gerekir. Windows 8.1 ile Windows Vista için en son kullanılabilir Evrensel C çalışma zamanı şu anda diğer düzeltmeler (sürüm 10.0.14393) ile Windows 10 Yıldönümü Güncelleştirmesi'nde bulunan sürüm dayanır.

## <a name="local-deployment"></a>Yerel dağıtım

Evrensel CRT yerel dağıtımını desteklenir, ancak performans ve güvenlik nedenleriyle önerilmez. DLL'leri yerel dağıtımı için Windows SDK'da Windows Setleri parçası olarak dahil edilir\\10\\Redist\\ucrt\\bilgisayar mimarisi DLL'leri alt. DLL'leri gerekli ucrtbase.dll ve bir dizi API adlı DLL'leri APISet ileticisi-ms-win -\*.dll. Her işletim sisteminde gerekli DLL'lerin kümesini değiştirir. Yerel olarak dağıttığınızda tüm DLL'leri dahil önemle tavsiye edilir.

Yerel dağıtımda dikkat edilmesi gereken iki kısıtlama vardır:

- Bir uygulama bir yerel kopyasını Evrensel CRT içerse bile Windows 10'da evrensel CRT Sistem dizinindeki her zaman kullanılır. Temel işletim sisteminin bir bileşeni Windows 10 Evrensel CRT olduğundan yerel kopyayı daha yeni sürümü, olsa bile geçerlidir.

- Yürütülebilir ana uygulama dizininin dışında bir dizinde yer alıyorsa önce Windows 8, Windows sürümlerinde, Evrensel CRT yerel olarak bir eklenti ile paketlenemiyor. DLL'leri APISet iletici başarıyla ucrtbase.dll bu durumda çözümleyemedi. Bazı önerilen alternatif çözümler içerir:

  - Evrensel CRT kitaplıklarla statik bağlantılar oluşturabilir,
  - Evrensel CRT merkezi olarak dağıtmak veya
  - Evrensel CRT dosyaları, uygulama ile aynı dizine koyun.

## <a name="deployment-on-microsoft-windows-xp"></a>Microsoft Windows XP üzerinde dağıtım

Visual Studio 2015 ve Visual Studio 2017 Microsoft Windows XP kullanmak için yazılım geliştirmeyi desteklemek devam edin. Bu geliştirme desteği için evrensel CRT sürümünü Microsoft Windows XP üzerinde çalışır. Merkezi dağıtımı Microsoft Windows XP üzerine Evrensel CRT diğer işletim sistemlerinden farklı olarak, bu nedenle Microsoft Windows XP işletim sistemi temel veya genişletilmiş destek artık değil.

Zaman görsel C++ Windows XP'de redistributable yüklendi, doğrudan Evrensel CRT ve tüm bağımlılıklarını sistem dizinine yükler. Yükleme veya herhangi bir Windows güncelleştirme bağlı değil. Yeniden dağıtılabilir birleştirme modülleri, Microsoft_VC*sürüm*_CRT_\*.msm dosyaları aynı yapın.

Windows XP Evrensel CRT yerel dağıtımı gibi diğer desteklenen işletim sistemlerinde aynıdır.

## <a name="see-also"></a>Ayrıca bkz.

- [Visual C++ üzerinde Dağıtım](deployment-in-visual-cpp.md)
