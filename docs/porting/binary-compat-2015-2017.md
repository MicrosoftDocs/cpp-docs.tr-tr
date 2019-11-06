---
title: C++Visual Studio 2015 ile Visual Studio 2019 arasında ikili uyumluluk
ms.date: 10/17/2019
helpviewer_keywords:
- binary compatibility, Visual C++
ms.assetid: 591580f6-3181-4bbe-8ac3-f4fbaca949e6
ms.openlocfilehash: 761f6187a8b30ecb4214821c7f91d1b26e9c647c
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627015"
---
# <a name="c-binary-compatibility-between-visual-studio-2015-and-visual-studio-2019"></a>C++Visual Studio 2015 ile Visual Studio 2019 arasında ikili uyumluluk

Visual Studio 2013 ve önceki sürümlerde, nesne dosyaları (OBJs), statik kitaplıklar (LIBs), dinamik kitaplıklar (dll 'Ler) ve derleme araç takımı ve çalışma zamanı kitaplıklarının farklı sürümleri kullanılarak oluşturulan yürütülebilir dosyalar arasındaki ikili uyumluluk garanti edilmez. 

Visual Studio 2015 ve üzeri sürümlerde, C++ araç takımı ana numarası 14 ' dir (visual Studio 2015 için v140, visual Studio 2017 için V141 ve visual Studio 2019 için v142). Bu, hem çalışma zamanı kitaplıklarının hem de derleyicinin bu sürümlerinden biriyle derlenen uygulamaların ikili uyumlu olduğunu yansıtır. Yani, Visual Studio 2015 ile oluşturulmuş üçüncü taraf kitaplığınız varsa, Visual Studio 2017 veya Visual Studio 2019 ile oluşturulmuş bir uygulamadan kullanmak için yeniden derlemenize gerek kalmaz.

Bu kuralın tek istisnası, `/GL` derleyici anahtarıyla derlenen statik kitaplıkların veya nesne dosyalarının ikili uyumlu olmadığı durumdur.

MSVC araç takımının desteklenen farklı sürümleriyle oluşturulan ikili dosyaları karıştıradığınızda, uygulamanızın üzerinde çalıştığı C++ görsel yeniden dağıtılabilir, uygulamanızı veya kullandığı kitaplıkları oluşturmak için kullanılan araç takımı sürümlerinden herhangi birini kullanmaktan daha eski olamaz.

## <a name="upgrade-microsoft-visual-c-redistributable-from-visual-studio-2015-or-2017-to-visual-studio-2019"></a>Visual Studio 2015 C++ veya 2017 ' den Visual Studio 'Ya Microsoft Visual Redistributable 'ı yükseltin 2019

İkili uyumluluğu sakladık ve ana sürüm (14) Visual Studio 2015, 2017 ve 2019 için Visual C++ yeniden dağıtılabilir için aynı saklandı, ancak her seferinde yalnızca bir görsel C++ yeniden dağıtılabilir sürümü yüklenebilir. Daha yeni bir sürüm, daha eski bir sürümün üzerine yazar. Visual Studio 2015 veya 2017 C++ ' den Visual yeniden dağıtılabilir ve sonra 2019 ' i yüklerseniz, 2019 sürümü daha eski bir sürümün üzerine yazılır. En son sürüme güvenlik düzeltmeleri de dahil olmak üzere en yeni özelliklerin ve hata düzeltmelerinin sahip olacağı için, her zaman kullanılabilir en son sürüme yükseltmeyi öneririz.

Benzer şekilde, daha yeni bir sürüme sahip olan bir makineye daha C++ eski bir görsel yeniden dağıtılabilir sürümünü yüklemeye izin vermedik. Zaten 2019 olan C++ bir makinede visual Studio 2015 veya 2017 ' den Visual yeniden dağıtılabilir yükleme, yükleme hatasına neden olur. Hata şuna benzer bir şey şöyle görünür:

```
*0x80070666 - Another version of this product is already installed. Installation of this version cannot continue. To configure or remove the existing version of this product, use Add/Remove Programs on the Control Panel.*.
```

Bu hata tasarıma göre yapılır. En yeni birini yüklü tutmanız önerilir.

## <a name="see-also"></a>Ayrıca bkz.

* [Görsel C++ değişiklik geçmişi](../porting/visual-cpp-change-history-2003-2015.md)
* [Desteklenen en son C++ yeniden dağıtılabilir karşıdan yüklemeler](https://support.microsoft.com/en-us/help/2977003/the-latest-supported-visual-c-downloads) 
