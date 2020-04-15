---
title: Genel özellikler (Linux C++ Project)
description: Visual Studio'da Genel özellikler sayfasında ayarlayabileceğiniz Linux proje özelliklerini açıklar.
ms.date: 01/14/2020
ms.assetid: 56c800a9-3df9-4196-87b2-81adb00e4767
ms.openlocfilehash: 832f10ca2c95e40ff7ece23462105fa49014aa5d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "79446169"
---
# <a name="general-properties-linux-c"></a>Genel özellikler (Linux C++)

::: moniker range="vs-2015"

Linux desteği Visual Studio 2017 ve sonrası sürümlerinde kullanılabilir.

::: moniker-end

::: moniker range=">=vs-2017"

| Özellik | Açıklama | Seçenekler |
|--|--|--|
| Çıktı Dizini | Çıktı dosyası dizinine göreli bir yol belirtir. Çevre değişkenlerini içerebilir. |
| Orta Dizini | Ara dosya dizinine göreli bir yol belirtir. Çevre değişkenlerini içerebilir. |
| Hedef Adı | Bu projenin oluşturduğu dosya adını belirtir. |
| Hedef Uzantısı | Bu projenin oluşturduğu dosya uzantısını `.a`(örneğin,) belirtir. |
| Temizle'de Silinecek Uzantılar | Yarı-kolon-delimited joker karakter belirtimi için hangi dosyalar için ara dizini temiz veya yeniden silmek için. |
| Günlük Dosyası Oluştur | Yapı günlüğü etkinleştirildiğinde yazılması gereken yapı günlüğü dosyasını belirtir. |
| Platform Araç Seti | Geçerli yapılandırmayı oluşturmak için kullanılan araç kümesini belirtir. Ayaredilmezse, varsayılan araç kümesi kullanılır. |
| Uzaktan Yapı Makinesi | Uzaktan oluşturma, dağıtma ve hata ayıklama için kullanılacak hedef makineyi veya aygıtı görüntüler. **Araçlar** > **Seçenekleri** > Platform**Bağlantı Yöneticisi****Çapraz** > kullanarak bir hedef makine bağlantısı ekleyebilir veya düzenleme yapabilirsiniz.<br /> **Visual Studio 2019 sürüm 16.1** [Hata ayıklama](debugging-linux.md) sayfasında hata ayıklama için farklı bir makine belirtebilirsiniz. |
| Uzaktan Yapı Kök Dizini | Uzak makine veya aygıttaki bir dizin için bir yol belirtir. |
| Uzaktan Yapı Proje Dizini | Proje için uzak makine veya aygıtta bir dizin için bir yol belirtir. |
| Uzaktan Dağıtım Dizini | **Visual Studio 2019 sürüm 16.1** Projeyi dağıtmak için uzak makineveya aygıttaki dizin yolunu belirtir. |
| Uzaktan Kopya Ekle Dizinleri | **Visual Studio 2019 sürüm 16.5**  Linux hedefinden özyinelemeli olarak kopyalanması gereken dizinlerin listesi. Bu özellik, IntelliSense için uzak üstbilgi kopyasını etkiler, ancak yapı yı etkilemez. **IntelliSense Derleyici Varsayılanları** false olarak ayarlandığında kullanılabilir. Hem IntelliSense hem de yapı için kullanılacak ek dahil dizinleri belirtmek için C/C++ Genel sekmesinin altındaki **Ek Dahil Dizinleri'ni** kullanın. |
| Uzaktan Kopya Hariç Dizinler | **Visual Studio 2019 sürüm 16.5** Linux hedefinden *kopyalanmaması* gereken dizinlerin listesi. Genellikle, bu özellik dahil dizinleri alt dizinleri kaldırmak için kullanılır. |
| IntelliSense Derleyici Varsayılanlarını Kullanır | **Visual Studio 2019 sürüm 16.5** Bu proje tarafından başvurulan derleyicinin varsayılan konumlar listesi için sorgulanıp sorgulanmaması. Bu konumlar otomatik olarak kopyalanması gereken uzak dizinler listesine eklenir. Derleyici gcc benzeri parametreleri desteklemiyorsa bu özelliği yalnızca false olarak ayarlayın. Hem gcc hem de clang derleyicileri dahil dizinleri (örneğin, `g++ -x c++ -E -v -std=c++11`) için sorguları destekler. |
| Yapılandırma Türü | Bu yapılandırmanın oluşturduğu çıktı türünü belirtir. | **Dinamik Kütüphane (.so)**<br/><br/>**Statik kitaplık (.a)**<br/><br/>**Uygulama (.out)**<br/><br/>**Makefile** |
| STL kullanımı | Bu yapılandırma için hangi C++ Standart Kitaplığı'nın kullanılacağını belirtir. | **Paylaşılan GNU Standart C++ Kitaplığı**<br/><br/>**Statik GNU Standart C++ Kitaplığı (-statik)** |

::: moniker-end
