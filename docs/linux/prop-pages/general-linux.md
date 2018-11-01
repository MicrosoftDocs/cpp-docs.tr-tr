---
title: Genel Özellikler (Linux C++ projesi) | Microsoft Docs
ms.date: 9/26/2017
ms.assetid: 56c800a9-3df9-4196-87b2-81adb00e4767
ms.openlocfilehash: bc4eb39d2d735f8f7f782d2827bf2b938c5c2457
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50461340"
---
# <a name="general-properties-linux-c"></a>Genel Özellikler (Linux C++)

Özellik | Açıklama | Seçenekleri
--- | ---| ---
Çıkış dizini | Çıkış dosyası dizinine göreli bir yol belirtir; ortam değişkenleri içerebilir.
Ara dizin | Ara dosya dizinine göreli bir yol belirtir; ortam değişkenleri içerebilir.
Hedef Adı | Bu projenin oluşturacağı bir dosya adını belirtir.
Hedef uzantısı | Bu projenin oluşturacağı dosya uzantısını belirtir. (Örnek: .a)
Temizlemede silinecek uzantılar | Joker karakter belirtimi Ara dizindeki, Temizlemede silin veya yeniden dosyalar için noktalı virgülle ayrılmış listesidir.
Derleme günlüğü dosyası | Günlük kaydı ne zaman oluşturulacağını yazılacak derleme günlüğü dosyasını belirtir.
Platform araç takımı | Geçerli yapılandırmayı oluşturmak için kullanılan araç kümesini belirtir. Aksi halde, varsayılan araç kümesi kullanılır
Uzaktan derleme makinesi | Dağıtma ve hata ayıklama hedef makine veya uzak derleme için kullanılacak cihaz.
Uzaktan derleme kök dizini | Uzak makine veya cihazdaki bir dizinin yolunu belirtir.
Uzaktan derleme proje dizini | Uzak makine veya cihaz projesi için bir dizinin yolunu belirtir.
Yapılandırma türü | Bu yapılandırmanın oluşturduğu çıkışın türünü belirtir. | **Dinamik kitaplık (.so)** -dinamik kitaplık (.so)<br>**Statik kitaplık (.a)** -statik kitaplık (.a)<br>**Uygulama (.out)** -uygulama (.out)<br>**Derleme görevleri dosyası** -derleme görevleri dosyası<br>
STL kullanımı | Bu yapılandırma için kullanmak için hangi C++ Standart Kitaplığı belirtir. | **Paylaşılan GNU standart C++ Kitaplığı**<br>**Statik GNU standart C++ Kitaplığı (-static)**<br>
