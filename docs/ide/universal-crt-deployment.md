---
title: Evrensel CRT dağıtım | Microsoft Docs
ms.custom: ''
ms.date: 05/11/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- deploying the CRT [C++]
- application CRT deployment [C++]
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 20006118d4bf27c379b78b84dc8807a4fd6c5e6c
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34256326"
---
# <a name="universal-crt-deployment"></a>Evrensel CRT dağıtım

Visual Studio 2013 üzerinden Visual Studio .NET her ana sürümü C++ derleyicisi ve araçları Microsoft C çalışma zamanı (CRT) kitaplığı yeni bir tek başına sürümü eklemiştir. CRT bu tek başına sürümlerini bağımsız başlangıç ve bitiş çeşitli derece, birbirleri ile uyumsuz. Örneğin, Visual Studio 2012 tarafından kullanılan CRT kitaplık sürüm 11, adlandırılmış msvcr110.dll, ve Visual Studio 2013 tarafından kullanılan CRT sürüm 12 adlandırılmış msvcr120.dll olmuştur. Visual Studio 2015'te itibaren artık böyledir. Visual Studio 2015 ve Visual Studio tüm sonraki sürümlerinde bir evrensel CRT kullanın.

Evrensel CRT bir Microsoft Windows işletim sistemi bileşenidir. Windows 10 işletim sisteminin parçası olarak dahil edilir ve Windows Update'i kullanarak eski işletim sistemleri, Windows 8.1 ile Windows Vista için kullanılabilir. Ayrıca, Evrensel CRT yerel dağıtımını, bazı kısıtlamalar ile desteklenir.

## <a name="central-deployment"></a>Merkezi dağıtım

Evrensel CRT merkezi olarak yüklemek için tercih edilen yöntem, Microsoft Windows Update kullanmaktır. Evrensel CRT önerilen güncelleştirme tüm Microsoft Windows işletim sistemleri, bu nedenle göre varsayılan, normal güncelleştirme işleminin bir parçası olarak yüklemek çoğu makineler desteklenen ' dir. Evrensel CRT ilk sürümdü [KB2999226](https://support.microsoft.com/en-us/kb/2999226); bir sonraki güncelleştirme ile çeşitli hata düzeltmeleri yapıldı [KB3118401](https://support.microsoft.com/en-us/kb/3118401), ve daha fazla hata düzeltmeleri ve yeni özelliklerle ek güncelleştirmeler olmuştur. Daha yeni güncelleştirmeler için arama [support.microsoft.com](https://support.microsoft.com) Evrensel C çalışma zamanı veya evrensel CRT için.

Tüm Microsoft Windows bilgisayarları düzenli olarak Windows Update'i kullanarak güncelleştirmeleri yüklemek ve bazıları tüm önerilen güncelleştirmeleri yüklemek değil. Visual Studio 2015 ve sonraki C++ toolsets bu makinelerdeki kullanılarak oluşturulan uygulamaların kullanımını desteklemek için evrensel CRT yeniden dağıtılabilir öğeleri çevrimdışı dağıtım için kullanılabilir yok. Bu yeniden dağıtılabilir öğeleri yukarıdaki KB bağlantılardan birini indirilebilir. Evrensel CRT yeniden dağıtılabilir öğeleri makine geçerli hizmet paketi güncelleştirildi gerektiğini unutmayın. Bu nedenle, örneğin, Windows 7 için yeniden dağıtılabilir yalnızca Windows 7 SP1 değil Windows 7 RTM yüklenir.

Visual C++ yeniden dağıtılabilir (VCRedist) Evrensel CRT C++ kitaplıkları'nın temel bir bağımlılığı olduğundan, Evrensel CRT temel sürümünü bir sürümü zaten yüklü, C++ Kitaplık karşılamak yeterli olmayan makinelerde yükler. bağımlılıkları. Uygulamanızı Evrensel CRT daha yeni bir sürümüne bağlıdır, bu daha yeni sürümünü açıkça yüklemeniz gerekir. Olası birden çok gerekli önlemek için VCRedist yükleme yeniden açmadan önce bu yüklemesi en iyisidir.

## <a name="local-deployment"></a>Yerel dağıtım

Evrensel CRT yerel dağıtımını desteklenir, ancak performans ve güvenlik nedenleriyle önerilmez.  Yerel dağıtım DLL'leri Windows SDK'da Windows Setleri parçası olarak dahil edilen\\10\\Redist\\ucrt\\bilgisayar mimarisi DLL'leri alt. DLL'leri gerekli dahil ucrtbase.dll ve APISet iletici DLL'leri API adlı bir dizi-ms-win -\*.dll. Her işletim sisteminde gerekli DLL'leri kümesini yerel olarak dağıttığınızda tüm DLL'ler eklenmesi önerilen şekilde değişir.

Dikkat edilmesi gereken yerel dağıtım iki sınırlamalar vardır:

- Bir uygulama Evrensel CRT uygulama yerel kopyasını içerse bile üzerinde Windows 10, Evrensel CRT Sistem dizinindeki her zaman kullanılır. Evrensel CRT yerel kopyasını yeni olsa bile bu geçerlidir. Evrensel CRT çekirdek işletim sisteminin bir bileşeni Windows 10 olmasıdır.

- Windows 8'den önceki Windows sürümlerinde, Evrensel CRT uygulamanız için ana yürütülebilir içeren dizinin dışında bir dizinde bulunan bir eklenti ile yerel olarak paketlenmesi olamaz. DLL'leri APISet iletici ucrtbase.dll başarıyla bu durumda çözümleyemez. Bazı önerilen alternatif çözümleri şunlardır:

  - Statik olarak Evrensel CRT bağlantı
  - Evrensel CRT merkezi olarak dağıtmak veya
  - Evrensel CRT dosyaları uygulama aynı dizine koyun.

## <a name="deployment-on-microsoft-windows-xp"></a>Microsoft Windows XP üzerinde dağıtım

Visual Studio 2015 ve Visual Studio 2017 Microsoft Windows XP üzerinde kullanım için yazılım geliştirme desteği devam edin. Bunu desteklemek için evrensel CRT sürümünü Microsoft Windows XP üzerinde çalışır. Microsoft Windows XP üzerine Evrensel CRT merkezi dağıtımını diğer işletim sistemlerinden farklıdır şekilde Microsoft Windows XP işletim sistemi artık temel veya genişletilmiş destek değil.

Visual C++ yeniden dağıtılabilir Windows XP üzerinde yüklü olduğunda doğrudan Evrensel CRT ve tüm bağımlılıkları sistem dizinine yüklemeden veya herhangi bir Windows güncelleştirme bağlı olarak yükler. Yeniden dağıtılabilir birleştirme modülleri, Microsoft_VC*sürüm*_CRT_\*.msm dosyaları aynı yapın.

Windows XP Evrensel CRT yerel dağıtımı gibi diğer desteklenen işletim sistemlerinde aynıdır.

## <a name="see-also"></a>Ayrıca bkz.

- [Visual C++ üzerinde Dağıtım](deployment-in-visual-cpp.md)
