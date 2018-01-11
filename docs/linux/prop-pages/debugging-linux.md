---
title: "Hata ayıklayıcı özellikleri (Linux C++) | Microsoft Docs"
ms.custom: 
ms.date: 9/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0c1c0fcc-a49b-451c-a5cb-ce9711fac064
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: 11ebb11cca19c98bf9f72b9f99f33d66464cd485
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2018
---
# <a name="c-debugging-properties-linux-c"></a>C++ hata ayıklama özellikleri (Linux C++)

Özellik | Açıklama | Seçenekler
--- | ---| ---
Önceden başlatma komutu | Hata ayıklama başlatır ve hata ayıklayıcısı önce Kabuk çalıştırılan bir komut çalıştırıyor ve hata ayıklama ortamı etkilemek için kullanılır.
Program | Uzak sistemde hata ayıklamak için program tam yolu. Uzak sistem üzerindeki bir yolu budur. Boş sol ya da değiştirmeden geçerli proje çıktısı varsayılan olarak ayarlanır.
Program değişkenleri | Ayıklanacak programın geçirmek için komut satırı bağımsız değişkenleri.
Çalışma dizini | Uzak uygulamanın çalışma dizini. Varsayılan olarak, kullanıcı giriş dizini.
Ek hata ayıklayıcı komutlarını | Hata ayıklama başlatmadan önce çalıştırmak hata ayıklayıcı için ek gdb komutları.
Hata ayıklayıcı bağlantı noktası numarası | Uzaktan hata ayıklayıcı ile hata ayıklayıcı iletişim için bağlantı noktası numarası. Bağlantı noktası, yerel olarak kullanımda olmamalıdır. Bu değer 1 ile 65535 arasında pozitif olmalıdır. Serbest bağlantı noktası numarası sağlanmadı kullanılıp kullanılmayacağını.
Uzaktan hata ayıklayıcı bağlantı noktası numarası | Uzaktan hata ayıklayıcı sunucunun (gdbserver) üzerinde uzak sistemde dinlediği bağlantı noktası numarası. Bağlantı noktası kullanımda olan uzak sistem olmamalıdır. Bu değer 1 ile 65535 arasında pozitif olmalıdır. 4444 başlayarak bir serbest bağlantı noktası numarası sağlanmazsa kullanılır.
Hata ayıklama modu | Hata ayıklayıcı ile gdb arabirimi nasıl belirtir. Hata ayıklayıcı gdb modunda uzak sistemde gdb Kabuk sürücüleri. Gdbserver modunda gdb yerel olarak çalıştığı ve Uzaktan çalıştıran gdbserver bağlanır. | **gdbserver**<br>**GDB**<br>
Ek sembol arama yolları | Hata ayıklama simgeleri (solib arama yolu) için ek arama yolu.
Hata ayıklama alt işlemleri | Alt işlemleri hata ayıklama etkinleştirilip etkinleştirilmeyeceğini belirtir.
Python etkinleştirmek oldukça yazdırma | İfade değerlerini oldukça yazdırma etkinleştirin. Yalnızca hata ayıklama modu gdb içinde desteklenir.
Görselleştirme dosyası | SLT türleri için görselleştirme yönergelerini içeren varsayılan yerel görselleştirme dosyası (.natvis). Geçerli çözüme ait diğer .natvis dosyaları otomatik olarak yüklenir.
Ek kaynaklar dosya yol haritası | Windows eşlemek için kullanılacak hata ayıklayıcı için ek yol eşitliğini Linux kaynak dosya adları için dosya adları kaynağı. Biçim "\<windows yolu > =\<linux yolu >;...". Windows yolu altında bulunan bir kaynak dosya adı başvurulacak gibi olduğu aynı göreli konumda yer alan Linux yolu altında bulundu. Yerel projesinde bulunan dosyaları, ek eşleme gerekmez.
