---
title: C++ ikili uyumluluğu 2015-2019
description: Visual Studio 2015, 2017 ve 2019 içindeki derlenmiş C++ dosyaları arasında ikili uyumluluğun nasıl çalıştığını açıklar. Bir Microsoft Visual C++ yeniden dağıtılabilir paket, üç sürüm için de kullanılabilir.
ms.date: 02/17/2021
helpviewer_keywords:
- binary compatibility, Visual C++
ms.openlocfilehash: a91e339e70843087adc12238edac91332c1a4453
ms.sourcegitcommit: c0c9cdae79f19655e809a4979227c51bb19cff63
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2021
ms.locfileid: "102236582"
---
# <a name="c-binary-compatibility-between-visual-studio-2015-2017-and-2019"></a>Visual Studio 2015, 2017 ve 2019 arasındaki C++ ikili uyumluluğu

Visual Studio 2013 ve önceki sürümlerde Microsoft C++ (MSVC) derleyicisi araç kümeleri, önemli sürümler arasında ikili uyumluluğu garanti etmez. Bu araç kümelerinin farklı sürümleri tarafından oluşturulan nesne dosyalarını, statik kitaplıkları, dinamik kitaplıkları ve yürütülebilir dosyaları bağlayamazsınız. Absıs, nesne biçimleri ve çalışma zamanı kitaplıkları uyumsuzdur.

Visual Studio 2015, 2017 ve 2019 içinde bu davranışı değiştirdik. Bu derleyici sürümlerinden herhangi biri tarafından derlenen çalışma zamanı kitaplıkları ve uygulamalar ikili uyumludur. Bu, üç sürüm için 14 ile başlayan C++ araç takımı ana numarasına yansıtılır. (Araç takımı sürümü Visual Studio 2015 için v140, 2017 için v141 ve 2019 için v142). Visual Studio 2015 tarafından oluşturulan üçüncü taraf kitaplıklarınızın olduğunu varsayalım. Bunları, Visual Studio 2017 veya 2019 tarafından oluşturulan bir uygulamada kullanmaya devam edebilirsiniz. Eşleşen bir araç kümesiyle yeniden derlemenize gerek yoktur. Microsoft Visual C++ yeniden dağıtılabilir paketin en son sürümü (yeniden dağıtılabilir) bunların hepsi için geçerlidir.

## <a name="restrictions-on-binary-compatibility"></a><a name="restrictions"></a> İkili uyumlulukta kısıtlamalar

V140, v141 ve v142 araç takımları ve küçük numaralanmış sürüm güncelleştirmeleri arasında ikili uyumlulukta üç önemli kısıtlama vardır:

- V140, v141 ve v142 Toolsets 'in farklı sürümleri tarafından oluşturulan ikilileri karıştırabilirsiniz. Ancak, en az bir araç takımını uygulamanızdaki en son ikiliye kadar en yakın şekilde bağlamanız gerekir. Örnek: herhangi bir 2017 araç takımı (v141, 15,0 ile 15,9) kullanılarak derlenen bir uygulamayı, bir sürüm 16,2 veya daha sonraki araç takımı kullanılarak bağlanmışsa, Visual Studio 2019 Version 16,2 (v142) kullanılarak derlenen bir statik kitaplığa bağlayabilirsiniz. Bir sürüm 16,2 kitaplığını, bir 16,4 veya sonraki araç takımını kullandığınız sürece bir sürüm 16,4 uygulamasına bağlayabilirsiniz.

- Uygulamanızın kullandığı yeniden dağıtılabilir, benzer bir ikili uyumluluk kısıtlamasına sahiptir. Araç takımının desteklenen farklı sürümleri tarafından oluşturulan ikili dosyaları karıştıradığınızda, yeniden dağıtılabilir sürüm en azından herhangi bir uygulama bileşeni tarafından kullanılan en son araç kümesi kadar yeni olmalıdır.

- [ `/GL` (Tüm program iyileştirmesi)](../build/reference/gl-whole-program-optimization.md) derleyici anahtarı kullanılarak derlenen statik kitaplıklar veya nesne dosyaları [ `/LTCG` (bağlantı zamanı kod üretimi)](../build/reference/ltcg-link-time-code-generation.md) , ikincil sürüm güncelleştirmeleri dahil olmak üzere sürümler arasında ikili uyumlu *değildir* . Ve kullanılarak derlenen tüm nesne dosyaları ve **`/GL`** Kitaplıklar **`/LTCG`** , derleme ve nihai bağlantı için tam olarak aynı araç takımını kullanmalıdır. Örneğin, **`/GL`** Visual studio 2019 sürüm 16,7 araç takımı 'nda kullanılarak oluşturulan kod, **`/GL`** visual Studio 2019 sürüm 16,8 araç takımı 'nda kullanılarak oluşturulan koda bağlanamaz. Derleyici [önemli hata C1047](../error-messages/compiler-errors-1/fatal-error-c1047.md)yayar.

## <a name="upgrade-the-microsoft-visual-c-redistributable-from-visual-studio-2015-or-2017-to-visual-studio-2019"></a>Yeniden dağıtılabilir Microsoft Visual C++ Visual Studio 2015 veya 2017 ' den Visual Studio 2019 ' ye yükseltin

Microsoft Visual C++ yeniden dağıtılabilir ana sürüm numarasını Visual Studio 2015, 2017 ve 2019 için aynı şekilde tutduk. Bu, aynı anda yalnızca bir yeniden dağıtılabilir örnek yüklenebileceği anlamına gelir. Daha yeni bir sürüm zaten yüklü olan eski sürümlerinin üzerine yazar. Örneğin, bir uygulama yeniden dağıtılabilir Visual Studio 2015 ' den yüklenebilir. Daha sonra, başka bir uygulama yeniden dağıtılabilir Visual Studio 2019 ' den yüklenir. 2019 sürümü eski sürümün üzerine yazar, ancak ikili uyumlu olduklarından, önceki uygulama hala sorunsuz bir şekilde çalışıyor. Yeniden dağıtılabilir en son sürümünün tüm en yeni özellikleri, güvenlik güncelleştirmelerini ve hata düzeltmelerini içerdiğinden emin veriyoruz. Bu nedenle, her zaman kullanılabilir en son sürüme yükseltmenizi öneririz.

Benzer şekilde, daha yeni bir sürüm zaten yüklüyse daha eski bir yeniden dağıtılabilir yükleyemezsiniz. Denerseniz, yükleyici bir hata bildirir. 2015 veya 2017 yeniden dağıtılabilir sürümünü zaten 2019 sürümüne sahip bir makineye yüklerseniz aşağıdakine benzer bir hata görürsünüz:

```Output
0x80070666 - Another version of this product is already installed. Installation of this version cannot continue. To configure or remove the existing version of this product, use Add/Remove Programs on the Control Panel.
```

Bu hata tasarıma göre yapılır. En yeni sürümü yüklü tutmanız önerilir. Yükleyicinizin bu hatadan sessizce kurtulbileceğinden emin olun.

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++ değişiklik geçmişi](../porting/visual-cpp-change-history-2003-2015.md)\
[Desteklenen en son Visual C++ yeniden dağıtılabilir İndirmeleri](https://support.microsoft.com/help/2977003/the-latest-supported-visual-c-downloads)
