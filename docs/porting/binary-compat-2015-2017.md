---
title: C++Visual Studio 2015 ile Visual Studio 2019 arasında ikili uyumluluk
description: Visual Studio 2015, 2017 ve 2019 C++ içindeki derlenmiş dosyalar arasında ikili uyumluluğun nasıl çalıştığını açıklar. Her üç sürüm C++ Için bir Microsoft Visual yeniden dağıtılabilir paketi çalışmaktadır.
ms.date: 11/07/2019
helpviewer_keywords:
- binary compatibility, Visual C++
ms.assetid: 591580f6-3181-4bbe-8ac3-f4fbaca949e6
ms.openlocfilehash: e41c34abe25deefe100f525044faeac0b0c3054a
ms.sourcegitcommit: eb254b4462a58d219376ff501bf768bd1adc07ae
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/11/2019
ms.locfileid: "73912885"
---
# <a name="c-binary-compatibility-between-visual-studio-2015-and-visual-studio-2019"></a>C++Visual Studio 2015 ile Visual Studio 2019 arasında ikili uyumluluk

Microsoft Visual Studio 2013 ve önceki sürümlerde, nesne dosyaları (OBJs), statik kitaplıklar (LIBs), dinamik bağlantı kitaplıkları (dll 'Ler) ve derleyici araç takımının farklı sürümleri kullanılarak oluşturulan yürütülebilir dosyalar arasında ikili uyumluluk garanti edilmez ve çalışma zamanı kitaplıkları.

Visual Studio 2015 ve üzeri sürümlerde, C++ araç takımı ana numarası 14 ' dir (visual Studio 2015 için v140, visual Studio 2017 için V141 ve visual Studio 2019 için v142). Bu numaralandırma, hem çalışma zamanı kitaplıklarının hem de derleyicinin bu sürümlerinden biriyle derlenen uygulamaların ikili uyumlu olduğunu yansıtır. Bu nedenle, Visual Studio 2015 ile oluşturulmuş bir üçüncü taraf kitaplığınız varsa, Visual Studio 2017 veya Visual Studio 2019 ile oluşturulmuş bir uygulamadan kullanmak için yeniden derlemenize gerek yoktur.

Bu kuralın tek istisnası, `/GL` derleyici anahtarıyla derlenen statik kitaplıkların veya nesne dosyalarının ikili uyumlu *olmadığı* durumdur.

Microsoft C++ (MSVC) araç takımının desteklenen farklı sürümleriyle oluşturulan ikili dosyaları karıştıradığınızda, uygulamanızın üzerinde çalıştığı C++ görsel yeniden dağıtılabilir paket, uygulamanızı oluşturmak için kullanılan araç takımı sürümlerinden veya kullandığı herhangi bir kitaplıklara daha eski olamaz.

## <a name="upgrade-the-microsoft-visual-c-redistributable-from-visual-studio-2015-or-2017-to-visual-studio-2019"></a>Visual Studio 2015 veya C++ 2017 ' den Visual 2019 Studio 'Ya Microsoft Visual yeniden dağıtılabilir 'i yükseltme

İkili uyumluluğu korunduğu ve ana sürümü (14) Visual Studio 2015, 2017 ve 2019 için Microsoft Visual C++ Redistributable ile aynı tutulduğundan, yalnızca bir Visual C++ yeniden dağıtılabilir sürümü bunlardan herhangi bir anda yüklenebilir. Daha yeni bir sürüm zaten yüklü olan eski bir sürümün üzerine yazar. Visual Studio 2015 veya 2017 C++ ' den Visual Studio Redistributable ve daha sonra visual Studio 2019 ' yi yüklerseniz, 2019 sürümü eski sürümün üzerine yazar. En son sürümün en yeni özelliklerin ve hata düzeltmelerinin (güvenlik düzeltmeleri dahil) bulunduğundan emin olduğumuz için, her zaman kullanılabilir en son sürüme yükseltmenizi öneririz.

Benzer şekilde, daha yeni bir sürümün zaten yüklü olduğu bir makineye Visual C++ yeniden dağıtılabilir 'in daha eski bir sürümünü yüklemenize izin vermedik. 2019 sürümü zaten C++ olan bir makinede visual Studio 2015 veya 2017 ' den Visual yeniden dağıtılabilir yükleme, yükleme hatasını tetikler. Hata şuna benzer:

```Output
0x80070666 - Another version of this product is already installed. Installation of this version cannot continue. To configure or remove the existing version of this product, use Add/Remove Programs on the Control Panel.
```

Bu hata tasarıma göre yapılır. En yeni sürümün yüklü tutulması önerilir.

## <a name="see-also"></a>Ayrıca bkz.

* [Görsel C++ değişiklik geçmişi](../porting/visual-cpp-change-history-2003-2015.md)
* [Desteklenen en son C++ yeniden dağıtılabilir karşıdan yüklemeler](https://support.microsoft.com/en-us/help/2977003/the-latest-supported-visual-c-downloads) 
