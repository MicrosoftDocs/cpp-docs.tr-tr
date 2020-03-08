---
title: Genel Özellikler (Linux C++ Projesi)
description: Visual Studio 'da, Genel Özellikler sayfasında ayarlayabileceğiniz Linux proje özelliklerini açıklar.
ms.date: 01/14/2020
ms.assetid: 56c800a9-3df9-4196-87b2-81adb00e4767
ms.openlocfilehash: d6a69d9fd3091c885ebd708cbc4598533d2922b4
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78883986"
---
# <a name="general-properties-linux-c"></a>Genel Özellikler (Linux C++)

::: moniker range="vs-2015"

Linux desteği, Visual Studio 2017 ve üzeri sürümlerde kullanılabilir.

::: moniker-end

::: moniker range=">=vs-2017"

Özellik | Açıklama | Yapabileceği
--- | ---| ---
Çıkış dizini | Çıkış dosyası dizinine göreli bir yol belirtir. Ortam değişkenlerini içerebilir.
Ara Dizin | Ara dosya dizinine göreli bir yol belirtir. Ortam değişkenlerini içerebilir.
Hedef Adı | Bu projenin oluşturduğu dosya adını belirtir.
Hedef uzantısı | Bu projenin oluşturduğu dosya uzantısını belirtir (örneğin, `.a`).
Temizlemede Silinecek Uzantılar | Ara dizindeki, temizleme veya yeniden oluşturma sırasında Silinecek dosyalar için noktalı virgülle ayrılmış joker karakter belirtimi.
Derleme günlüğü dosyası | Derleme günlüğü etkinken yazılacak olan derleme günlüğü dosyasını belirtir.
Platform araç takımı | Geçerli yapılandırmayı oluşturmak için kullanılan araç takımını belirtir. Ayarlanmamışsa, varsayılan araç kümesi kullanılır.
Uzak derleme makinesi | Uzaktan derleme, dağıtma ve hata ayıklama için kullanılacak hedef makineyi veya cihazı görüntüler. **Platformlar arası** > **bağlantı yöneticisi** > **Araçlar** > **seçeneklerini** kullanarak bir hedef makine bağlantısı ekleyebilir veya düzenleyebilirsiniz. **Visual Studio 2019 sürüm 16,1** [Hata ayıklama sayfasında hata](debugging-linux.md) ayıklama için farklı bir makine belirtebilirsiniz.
Uzak derleme kök dizini | Uzak makine veya cihazdaki bir dizinin yolunu belirtir.
Uzak derleme proje dizini | Proje için uzak makine veya cihazdaki bir dizinin yolunu belirtir.
Uzak dağıtım dizini | **Visual Studio 2019 sürüm 16,1** Projeyi dağıtmak için uzak makinedeki veya cihazdaki dizin yolunu belirtir.
Uzak kopya ekleme dizinleri | **Visual Studio 2019 sürüm 16,5**  Linux hedefinden yinelemeli olarak kopyalanacak dizinlerin listesi. Bu özellik, IntelliSense için uzak üst bilgi kopyasını etkiler, ancak derlemeyi etkiler. **IntelliSense derleyici Varsayılanları kullandığında** , false olarak ayarlandığında kullanılabilir. IntelliSense ve Build için kullanılacak ek ekleme dizinleriniC++ belirtmek için C/Genel sekmesi altındaki **Ek ekleme dizinlerini** kullanın.
Uzak kopya dışlama dizinleri | **Visual Studio 2019 sürüm 16,5** Linux hedefinden *kopyalayamayan* dizinlerin listesi. Genellikle, bu özellik içerme dizinlerinin alt dizinlerini kaldırmak için kullanılır.
IntelliSense derleyici varsayılanlarını kullanır | **Visual Studio 2019 sürüm 16,5** Varsayılan içerme konumları listesinde bu proje tarafından başvurulan derleyicinin sorgulanıp sorgulanmayacağı. Bu konumlar, kopyalanacak uzak dizinler listesine otomatik olarak eklenir. Derleyici GCC benzeri parametreleri desteklemiyorsa bu özelliği false olarak ayarlayın. Hem GCC hem de Clang derleyicileri, içerme dizinleri için sorguları destekler (örneğin, `g++ -x c++ -E -v -std=c++11`).
Yapılandırma türü | Bu yapılandırmanın oluşturduğu çıkışın türünü belirtir. | **Dinamik kitaplık (. so)**<br/>**Statik kitaplık (. a)**<br/>**Uygulama (. out)**<br/>**Dosyasının**
STL kullanımı | Bu yapılandırma C++ için hangi standart kitaplığın kullanılacağını belirtir. | **Paylaşılan GNU standart C++ kitaplığı**<br/>**Statik GNU standart C++ kitaplığı (-static)**

::: moniker-end
