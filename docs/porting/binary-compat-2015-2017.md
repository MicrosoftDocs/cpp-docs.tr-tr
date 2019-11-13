---
title: C++Visual Studio 2015, 2017 ve 2019 arasında ikili uyumluluk
description: Visual Studio 2015, 2017 ve 2019 C++ içindeki derlenmiş dosyalar arasında ikili uyumluluğun nasıl çalıştığını açıklar. Her üç sürüm C++ Için bir Microsoft Visual yeniden dağıtılabilir paketi çalışmaktadır.
ms.date: 11/11/2019
helpviewer_keywords:
- binary compatibility, Visual C++
ms.assetid: 591580f6-3181-4bbe-8ac3-f4fbaca949e6
ms.openlocfilehash: 118ad0a32d5dc8c344967f9a67f2d5b05aa806c0
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73965562"
---
# <a name="c-binary-compatibility-between-visual-studio-2015-2017-and-2019"></a>C++Visual Studio 2015, 2017 ve 2019 arasında ikili uyumluluk

Visual Studio 2013 ve C++ önceki sürümlerde Microsoft (MSVC) derleyicisi araç kümeleri, sürümler arasında ikili uyumluluğu garanti etmez. Farklı sürümlere göre oluşturulan nesne dosyalarını, statik kitaplıkları, dinamik kitaplıkları ve yürütülebilir dosyaları bağlayamazsınız. Absıs, nesne biçimleri ve çalışma zamanı kitaplıkları uyumsuzdur.

Visual Studio 2015, 2017 ve 2019 içinde bu davranışı değiştirdik. Bu derleyici sürümlerinden herhangi biri tarafından derlenen çalışma zamanı kitaplıkları ve uygulamalar ikili uyumludur. Bu, üç sürüm için C++ 14 olan araç takımı ana numarasına yansıtılır. (Araç takımı sürümü Visual Studio 2015 için v140, 2017 için v141 ve 2019 için v142). Visual Studio 2015 tarafından oluşturulan üçüncü taraf kitaplıklarınızın olduğunu varsayalım. Bunları, Visual Studio 2017 veya 2019 tarafından oluşturulan bir uygulamada kullanmaya devam edebilirsiniz. Eşleşen bir araç kümesiyle yeniden derlemenize gerek yoktur. Microsoft Visual C++ yeniden dağıtılabilir paketi 'Nin (yeniden dağıtılabilir) en son sürümü, hepsi için geçerlidir.

Bu kural için bir özel durum oluştu: `/GL` derleyici anahtarı kullanılarak derlenen statik kitaplıklar veya nesne dosyaları sürümler arasında ikili uyumlu *değildir* .

Uygulamanızın kullandığı yeniden dağıtılabilir, önemli bir ikili uyumluluk kısıtlamasına sahiptir. Araç takımının desteklenen farklı sürümleriyle oluşturulmuş ikili dosyaları karıştırabilmeniz için geçerlidir. Yeniden dağıtılabilir sürüm, en az bir uygulama bileşeni tarafından kullanılan en son araç kümesi kadar yeni olmalıdır.

## <a name="upgrade-the-microsoft-visual-c-redistributable-from-visual-studio-2015-or-2017-to-visual-studio-2019"></a>Visual Studio 2015 veya C++ 2017 ' den Visual 2019 Studio 'Ya Microsoft Visual yeniden dağıtılabilir 'i yükseltme

Visual Studio 2015, 2017 ve C++ 2019 Için Microsoft Visual yeniden dağıtılabilir ana sürüm numarasını aynı şekilde tutduk. Bu, aynı anda yalnızca bir yeniden dağıtılabilir örnek yüklenebileceği anlamına gelir. Daha yeni bir sürüm zaten yüklü olan eski sürümlerinin üzerine yazar. Örneğin, bir uygulama yeniden dağıtılabilir Visual Studio 2015 ' den yüklenebilir. Daha sonra, başka bir uygulama yeniden dağıtılabilir Visual Studio 2019 ' den yüklenir. 2019 sürümü eski sürümün üzerine yazar, ancak ikili uyumlu olduklarından, önceki uygulama hala sorunsuz bir şekilde çalışıyor. Yeniden dağıtılabilir en son sürümünün tüm en yeni özellikleri, güvenlik güncelleştirmelerini ve hata düzeltmelerini içerdiğinden emin veriyoruz. Bu nedenle, her zaman kullanılabilir en son sürüme yükseltmenizi öneririz.

Benzer şekilde, daha yeni bir sürüm zaten yüklüyse daha eski bir yeniden dağıtılabilir yükleyemezsiniz. Denerseniz, yükleyici bir hata bildirir. 2015 veya 2017 yeniden dağıtılabilir sürümünü zaten 2019 sürümüne sahip bir makineye yüklerseniz aşağıdakine benzer bir hata görürsünüz:

```Output
0x80070666 - Another version of this product is already installed. Installation of this version cannot continue. To configure or remove the existing version of this product, use Add/Remove Programs on the Control Panel.
```

Bu hata tasarıma göre yapılır. En yeni sürümü yüklü tutmanız önerilir. Yükleyicinizin bu hatadan sessizce kurtulbileceğinden emin olun.

## <a name="see-also"></a>Ayrıca bkz.

[Görsel C++ değişiklik geçmişi](../porting/visual-cpp-change-history-2003-2015.md)\
[Desteklenen en son C++ yeniden dağıtılabilir karşıdan yüklemeler](https://support.microsoft.com/help/2977003/the-latest-supported-visual-c-downloads)
