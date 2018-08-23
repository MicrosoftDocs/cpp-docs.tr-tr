---
title: Özellikleri (Linux C++) hata ayıklayıcı | Microsoft Docs
ms.custom: ''
ms.date: 9/26/2017
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: Linux
ms.topic: conceptual
ms.assetid: 0c1c0fcc-a49b-451c-a5cb-ce9711fac064
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: df57a884186fe33d91de78647cc225f3a63a6f9f
ms.sourcegitcommit: e9ce38decc9f986edab5543de3464b11ebccb123
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/13/2018
ms.locfileid: "42464475"
---
# <a name="c-debugging-properties-linux-c"></a>C++ hata ayıklama özellikleri (Linux C++)

Özellik | Açıklama | Seçenekleri
--- | ---| ---
Başlatma öncesi komut | Hata ayıklama başlatılmadan ve hata ayıklayıcı önce kabukta çalıştırılan bir komut çalışıyor ve hata ayıklama ortamını etkilemek için kullanılabilir.
Program | Uzak sistemde ayıklanacak programın tam yolu. Bu, uzak sistemdeki bir yoldur. Geçerli proje çıkışı için varsayılan olarak, boş ya da bunu değişmeden.
Program bağımsız değişkenleri | Ayıklanan programa geçirilecek komut satırı bağımsız değişkenleri.
Çalışma dizini | Uzak uygulamanın çalışma dizini. Varsayılan olarak, kullanıcının giriş dizinidir.
Ek hata ayıklayıcı komutları | Hata ayıklayıcının ayıklamaya başlamadan önce çalıştırması ek gdb komutları.
Hata ayıklayıcı bağlantı noktası numarası | Uzaktan hata ayıklayıcı ile hata ayıklayıcı iletişimi için bağlantı noktası numarası. Bağlantı noktası, yerel olarak kullanımda olmamalıdır. Bu değer 1 ile 65535 arasında pozitif olmalıdır. Bir ücretsiz bağlantı noktası numarası sağlanmazsa kullanılacaktır.
Uzaktan hata ayıklayıcı bağlantı noktası numarası | Uzaktan hata ayıklayıcı sunucusunun (gdbserver) uzak sistemde dinlediği bağlantı noktası numarası. Bağlantı noktası uzak sistemde kullanımda olmamalıdır. Bu değer 1 ile 65535 arasında pozitif olmalıdır. 4444'ten bir ücretsiz bağlantı noktası numarası sağlanmazsa kullanılır.
Hata ayıklama modu | Hata ayıklayıcının gdb ile nasıl arabirimleri belirtir. Gdb modunda hata ayıklayıcının gdb shell uzak sistemde sürücüler. Gdbserver modunda, gdb yerel olarak çalışır ve uzakta çalışan gdbserver'a bağlanır. | **gdbserver**<br>**GDB**<br>
Ek sembol arama yolları | (Solib-search-path) hata ayıklama sembolleri için ek arama yolu.
Alt işlemlerde hata ayıklama | Alt işlemlerde hata ayıklamanın etkinleştirilip etkinleştirilmeyeceğini belirtir.
Etkinleştirme Python düzgün yazdırma | Düzgün ifade değerlerini yazdırma etkinleştirin. Yalnızca gdb hata ayıklama modunda desteklenir.
Görselleştirme dosyası | SLT türleri için görselleştirme yönergelerini içeren varsayılan yerel görselleştirme dosyası (.natvis). Geçerli çözüme ait diğer .natvis dosyaları otomatik olarak yüklenir.
Ek kaynaklar dosya yolu eşlemesi | Windows eşleştirmek için kullanılacak hata ayıklayıcı için ek yol denklikleri dosya adlarını Linux kaynak dosya adlarına kaynağı. Biçim "\<windows-path > =\<linux-path >;...". Windows yolu altında bulunan bir kaynak dosya adı başvurulan gibi olan Linux yolu altında aynı göreli konumda bulunamadı. Yerel projede bulunan dosyalar ek eşleme gerekmez.
