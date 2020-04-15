---
title: Hata Ayıklama Özellikleri (Linux C++)| Microsoft Dokümanlar
ms.date: 06/07/2019
ms.assetid: 0c1c0fcc-a49b-451c-a5cb-ce9711fac064
ms.openlocfilehash: bebee7a2b3bcfd880a538acae35c9616b3b1bd46
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "79446185"
---
# <a name="c-debugging-properties-linux-c"></a>C++ Hata Ayıklama Özellikleri (Linux C++)

::: moniker range="vs-2015"

Linux desteği Visual Studio 2017 ve sonrası sürümlerinde kullanılabilir.

::: moniker-end

::: moniker range=">=vs-2017"

| Özellik | Açıklama | Seçenekler |
|--|--|--|
| Uzaktan hata ayıklama makinesi | **Visual Studio 2019 sürüm 16.1**: Makinenin programı hata ayıklama sını belirtir. [Genel](general-linux.md) sayfada belirtilen uzaktan yapı makinesinden farklı olabilir. **Araçlar** > **Seçenekleri** > Platform**Bağlantı Yöneticisi****Çapraz** > kullanarak bir hedef makine bağlantısı ekleyebilir veya düzenleme yapabilirsiniz. |
| Ön Başlatma Komutu | Hata ayıklama başlamadan önce kabukta çalışan ve hata ayıklama ortamını etkilemek için kullanılabilen bir komut. |
| Program | Hata ayıklamak için programa uzak sistemde tam yol. Boş veya değişmeden bırakılırsa, geçerli proje çıktısına varsayılan olarak. |
| Program Bağımsız Değişkenleri | Programa geçmek için komut satırı bağımsız değişkenleri debugged ediliyor. |
| Çalışma Rehberi | Uzaktan uygulama nın çalışma dizini. Varsayılan olarak, kullanıcı ev dizini. |
| Ek Hata Ayıklama Komutları | Hata `gdb` ayıklama başlamadan önce çalışması için ek komutlar. |
| Debugger Bağlantı Noktası Numarası | Uzak hata ayıklama ile hata ayıklama iletişimi için bağlantı noktası numarası. Bağlantı noktası yerel olarak kullanılmamalıdır. Bu değer pozitif olmalı ve 1 ile 65535 arasında olmalıdır. Sağlanmazsa, ücretsiz bağlantı noktası numarası kullanılır. |
| Uzaktan Hata Ayıklama Bağlantı Noktası Numarası | Uzaktan hata ayıklama sunucusunun `gdbserver` uzak sistemde dinlediği bağlantı noktası numarası. Bağlantı noktası uzak sistemde kullanılmamalıdır. Bu değer pozitif olmalı ve 1 ile 65535 arasında olmalıdır. Sağlanmazsa, 4444'ten başlayan ücretsiz bağlantı noktası numarası kullanılır. |
| Hata Ayıklama Modu | Hata ayıklamanın `gdb`. *gdb modunda,* hata ayıkıcı `gdb` uzak sistemde kabuk üzerinde sürücüler. *gdbserver modunda,* `gdb` yerel olarak çalışır `gdbserver` ve uzaktan çalışmaya bağlanır. | **gdbserver**<br/>**Gdb** |
| Ek Sembol Arama Yolları | Hata ayıklama sembolleri (solib-search-path) için ek arama yolu. |
| Hata Ayıklama Alt İşlemleri | Alt işlemlerin hata ayıklanmasını etkinleştirip etkinleştirmeyeceğini belirtir. |
| Python Pretty Printing etkinleştirin | İfade değerlerinin güzel bir şekilde yazdırılmasını etkinleştirin. Sadece gdb hata ayıklama modunda desteklenir. |
| Görselleştirme Dosyası | Varsayılan yerel görselleştirme dosyası (.natvis) SLT türleri için görselleştirme yönergeleri içeren. Geçerli çözüme ait diğer .natvis dosyaları otomatik olarak yüklenir. |
| Ek Kaynaklar Dosya Yolu Haritası | Hata ayıklamanın Windows kaynak dosya adlarını Linux kaynak dosya adlarıyla eşlemek için kullanması gereken ek yol eşdeğerlikleri. Biçimi "\<windows-path>\<= linux-path>;...". Windows yolu altında bulunan bir kaynak dosya adı, Linux yolu altında aynı göreli konumda bulunurmuş gibi başvurulanır. Yerel projede bulunan dosyalar ek eşleme gerektirmez. |

::: moniker-end
