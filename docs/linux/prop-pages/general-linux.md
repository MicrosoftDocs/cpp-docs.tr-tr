---
title: Genel Özellikler (Linux C++ projesi) | Microsoft Docs
ms.date: 06/07/2019
ms.assetid: 56c800a9-3df9-4196-87b2-81adb00e4767
ms.openlocfilehash: ce3683f11d80c253195b751b5eed364fbc04b68a
ms.sourcegitcommit: 8adabe177d557c74566c13145196c11cef5d10d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/10/2019
ms.locfileid: "66821287"
---
# <a name="general-properties-linux-c"></a>Genel Özellikler (Linux C++)

::: moniker range="vs-2015"

Linux desteği, Visual Studio 2017 ile kullanılabilir ve üzerinde desteklenir.

::: moniker-end

::: moniker range=">=vs-2017"

Özellik | Açıklama | Seçenekleri
--- | ---| ---
Çıkış dizini | Çıkış dosyası dizinine göreli bir yol belirtir; ortam değişkenleri içerebilir.
Ara dizin | Ara dosya dizinine göreli bir yol belirtir; ortam değişkenleri içerebilir.
Hedef Adı | Bu projenin oluşturacağı bir dosya adını belirtir.
Hedef uzantısı | Bu projenin oluşturacağı dosya uzantısını belirtir. (Örnek: .a)
Temizlemede silinecek uzantılar | Joker karakter belirtimi Ara dizindeki, Temizlemede silin veya yeniden dosyalar için noktalı virgülle ayrılmış listesidir.
Derleme günlüğü dosyası | Günlük kaydı ne zaman oluşturulacağını yazılacak derleme günlüğü dosyasını belirtir.
Platform araç takımı | Geçerli yapılandırmayı oluşturmak için kullanılan araç kümesini belirtir. Aksi halde, varsayılan araç kümesi kullanılır
Uzaktan derleme makinesi | Dağıtma ve hata ayıklama hedef makine veya uzak derleme için kullanılacak cihaz. **Visual Studio 2019 sürüm 16.1** hata ayıklama için farklı bir makineye belirtilebilir [hata ayıklama](debugging-linux.md) sayfası.
Uzaktan derleme kök dizini | Uzak makine veya cihazdaki bir dizinin yolunu belirtir.
Uzaktan derleme proje dizini | Uzak makine veya cihaz projesi için bir dizinin yolunu belirtir.
Yapılandırma türü | Bu yapılandırmanın oluşturduğu çıkışın türünü belirtir. | **Dinamik kitaplık (.so)** -dinamik kitaplık (.so)<br>**Statik kitaplık (.a)** -statik kitaplık (.a)<br>**Uygulama (.out)** -uygulama (.out)<br>**Derleme görevleri dosyası** -derleme görevleri dosyası<br>
STL kullanımı | Bu yapılandırma için kullanmak için hangi C++ Standart Kitaplığı belirtir. | **Paylaşılan GNU standart C++ Kitaplığı**<br>**Statik GNU standart C++ Kitaplığı (-static)**<br>

::: moniker-end

