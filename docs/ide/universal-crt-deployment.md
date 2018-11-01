---
title: Evrensel CRT dağıtım
ms.date: 05/11/2018
helpviewer_keywords:
- deploying the CRT [C++]
- application CRT deployment [C++]
ms.openlocfilehash: 90f859eb0e9134c997e7eecad118cfb8ec00b782
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50657700"
---
# <a name="universal-crt-deployment"></a>Evrensel CRT dağıtım

Visual Studio 2013 ile Visual Studio NET'ten her önemli bir C++ Derleyici ve araçların sürümü, Microsoft C çalışma zamanı (CRT) Kitaplığı'nın yeni bir tek başına sürüm eklemiştir. Bu tek başına sürümlerini CRT bağımsız gelen ve çeşitli derece, birbirleri ile uyumsuz. Örneğin, Visual Studio 2012 tarafından kullanılan CRT kitaplığı sürüm 11, adlandırılmış msvcr110.dll, ve Visual Studio 2013'ün tarafından kullanılan CRT sürüm 12 adlandırılmış msvcr120.dll şeklindeydi. Visual Studio 2015'te itibaren artık durum budur. Visual Studio 2015 ve Visual Studio'nun tüm sonraki sürümler, bir evrensel CRT kullanın.

Evrensel CRT Microsoft Windows işletim sisteminin bir bileşeni var. Windows 10 işletim sisteminin parçası olarak dahil edilmiştir ve Windows Update'i kullanarak eski işletim sistemleri, Windows 8.1 ile Windows Vista için kullanılabilir. Ayrıca, Evrensel CRT yerel dağıtımını, bazı kısıtlamalar ile desteklenir.

## <a name="central-deployment"></a>Merkezi dağıtım

Evrensel CRT merkezi olarak yüklemek için tercih edilen yöntem, Microsoft Windows Update kullanmaktır. Evrensel CRT tüm önerilen güncelleştirmesi Microsoft Windows işletim sistemleri, böylece göre varsayılan, normal güncelleştirme işleminin bir parçası yüklemek çoğu makineleri desteklenir. Evrensel CRT ilk sürümdü [KB2999226](https://support.microsoft.com/kb/2999226); bir sonraki güncelleştirme ile çeşitli hata düzeltmeleri yapıldı [KB3118401](https://support.microsoft.com/kb/3118401), ve daha fazla hata düzeltmeleri ve yeni özelliklerle ek güncelleştirmeler yapıldı. Daha yeni güncelleştirmeler için arama [support.microsoft.com](https://support.microsoft.com) Evrensel C çalışma zamanı veya evrensel CRT.

Tüm Microsoft Windows bilgisayarlarda Windows Update kullanarak düzenli olarak güncelleştirmeleri yüklemek ve bazıları tüm önerilen güncelleştirmeleri yüklenmez. Visual Studio 2015 ve sonraki C++ araç takımları, bu makinelerde kullanılarak oluşturulan uygulamaların kullanımını desteklemek için evrensel CRT yeniden dağıtılabilir paketlerini çevrimdışı dağıtım için kullanılabilen vardır. Bu yeniden dağıtılabilir dosyaları, yukarıdaki KB bağlantılardan birini yüklenebilir. Evrensel CRT yeniden dağıtılabilir dosyaları, makine için geçerli hizmet paketi güncelleştirildi gerektiğini lütfen unutmayın. Bu nedenle, örneğin, Windows 7 için yeniden dağıtılabilir yalnızca Windows 7 SP1 değil Windows 7 RTM yüklenir.

Evrensel CRT temel bir bağımlılık olan C++ kitaplıklarının olduğundan, Visual C++ yeniden dağıtılabilir (VCRedist) bir sürüm zaten yüklü, C++ Kitaplık karşılamak yeterli olmayan makinelere Evrensel CRT temel sürümünü yükler. bağımlılıkları. Uygulamanızı daha yeni bir evrensel CRT sürümüne bağlı ise, açıkça daha yeni bir sürümü yüklemeniz gerekir. Önce yüklenmesi gereken olası çok önlemek için VCRedist yeniden yüklemek en iyisidir.

## <a name="local-deployment"></a>Yerel dağıtım

Evrensel CRT yerel dağıtımını desteklenir, ancak performans ve güvenlik nedenleriyle önerilmez.  DLL'leri yerel dağıtımı için Windows SDK'da Windows Setleri parçası olarak dahil edilir\\10\\Redist\\ucrt\\bilgisayar mimarisi DLL'leri alt. DLL'leri gerekli ucrtbase.dll ve bir dizi API adlı DLL'leri APISet ileticisi-ms-win -\*.dll. Her işletim sisteminde gerekli DLL'lerin kümesi, yerel olarak dağıttığınızda tüm DLL'leri dahil önemle tavsiye edilir şekilde değişir.

Yerel dağıtımda dikkat edilmesi gereken iki kısıtlama vardır:

- Bir uygulama bir yerel kopyasını Evrensel CRT içerse bile Windows 10'da evrensel CRT Sistem dizinindeki her zaman kullanılır. Yeni Evrensel CRT yerel kopyasını olsa bile bu geçerlidir. Temel işletim sisteminin bir bileşeni Windows 10 Evrensel CRT olduğundan budur.

- Windows 8 önce Windows sürümlerinde, Evrensel CRT yerel olarak ile uygulamanızın temel yürütülebilir dosyasını içeren dizin dışında'bir dizinde bulunan bir eklenti paketlenemiyor. DLL'leri APISet iletici başarıyla ucrtbase.dll bu durumda çözümleyemedi. Bazı önerilen alternatif çözümler içerir:

  - Evrensel CRT kitaplıklarla statik bağlantılar oluşturabilir,
  - Evrensel CRT merkezi olarak dağıtmak veya
  - Evrensel CRT dosyaları, uygulama ile aynı dizine koyun.

## <a name="deployment-on-microsoft-windows-xp"></a>Microsoft Windows XP üzerinde dağıtım

Visual Studio 2015 ve Visual Studio 2017 Microsoft Windows XP kullanmak için yazılım geliştirmeyi desteklemek devam edin. Bunu desteklemek için evrensel CRT sürümünü Microsoft Windows XP üzerinde çalışır. Merkezi dağıtımı Microsoft Windows XP üzerine Evrensel CRT diğer işletim sistemlerinden farklı olarak, bu nedenle Microsoft Windows XP işletim sistemi temel veya genişletilmiş destek artık değil.

Visual C++ yeniden dağıtılabilir Windows XP'de yüklü olduğunda, doğrudan Evrensel CRT ve tüm bağımlılıklarını sistem dizinine yüklemeden veya herhangi bir Windows güncelleştirme bağlı olarak yükler. Yeniden dağıtılabilir birleştirme modülleri, Microsoft_VC*sürüm*_CRT_\*.msm dosyaları aynı yapın.

Windows XP Evrensel CRT yerel dağıtımı gibi diğer desteklenen işletim sistemlerinde aynıdır.

## <a name="see-also"></a>Ayrıca bkz.

- [Visual C++ üzerinde Dağıtım](deployment-in-visual-cpp.md)
