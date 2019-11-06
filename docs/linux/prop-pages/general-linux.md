---
title: Genel Özellikler (Linux C++ Projesi) | Microsoft Docs
ms.date: 06/07/2019
ms.assetid: 56c800a9-3df9-4196-87b2-81adb00e4767
ms.openlocfilehash: c17a5e0214e6365d604a80bd4b3891858f0f9186
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626808"
---
# <a name="general-properties-linux-c"></a>Genel Özellikler (Linux C++)

::: moniker range="vs-2015"

Linux desteği, Visual Studio 2017 ve üzeri sürümlerde kullanılabilir.

::: moniker-end

::: moniker range=">=vs-2017"

Özellik | Açıklama | Yapabileceği
--- | ---| ---
Çıkış dizini | Çıkış dosyası dizinine göreli bir yol belirtir; ortam değişkenlerini içerebilir.
Ara Dizin | Ara dosya dizinine göreli bir yol belirtir; ortam değişkenlerini içerebilir.
Hedef Adı | Bu projenin üretecektir bir dosya adı belirtir.
Hedef uzantısı | Bu projenin üretekullanacağı bir dosya uzantısını belirtir. (Örnek:. a)
Temizlemede Silinecek Uzantılar | Ara dizindeki, temizleme veya yeniden oluşturma sırasında Silinecek dosyalar için noktalı virgülle ayrılmış joker karakter belirtimi.
Derleme günlüğü dosyası | Derleme günlüğü etkinken yazılacak olan derleme günlüğü dosyasını belirtir.
Platform araç takımı | Geçerli yapılandırmayı oluşturmak için kullanılan araç takımını belirtir; Ayarlanmamışsa, varsayılan araç kümesi kullanılır
Uzak derleme makinesi | Uzaktan derleme, dağıtma ve hata ayıklama için kullanılacak hedef makine veya cihaz. **Visual Studio 2019 sürüm 16,1** [Hata ayıklama sayfasında,](debugging-linux.md) hata ayıklama için farklı bir makine belirtilebilir.
Uzak derleme kök dizini | Uzak makine veya cihazdaki bir dizinin yolunu belirtir.
Uzak derleme proje dizini | Proje için uzak makine veya cihazdaki bir dizinin yolunu belirtir.
Yapılandırma türü | Bu yapılandırmanın oluşturduğu çıkışın türünü belirtir. | **Dinamik kitaplık (. so)** -dinamik kitaplık (. so)<br>**Statik kitaplık (. a)** -statik kitaplık (. a)<br>**Uygulama (. out)** -uygulama (. out)<br>**Makefile** -makefile<br>
STL kullanımı | Bu yapılandırma C++ için hangi standart kitaplığın kullanılacağını belirtir. | **Paylaşılan GNU standart C++ kitaplığı**<br>**Statik GNU standart C++ kitaplığı (-static)**<br>

::: moniker-end
