---
title: Hata ayıklayıcı özellikleri (Linux C++) | Microsoft Docs
ms.date: 06/07/2019
ms.assetid: 0c1c0fcc-a49b-451c-a5cb-ce9711fac064
ms.openlocfilehash: 2b55a0db001c98be72ac88c17c62b21e98ec4888
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924518"
---
# <a name="c-debugging-properties-linux-c"></a>C++ hata ayıklama özellikleri (Linux C++)

::: moniker range="msvc-140"

Linux desteği, Visual Studio 2017 ve üzeri sürümlerde kullanılabilir.

::: moniker-end

::: moniker range=">=msvc-150"

| Özellik | Açıklama | Seçenekler |
|--|--|--|
| Uzaktan hata ayıklama makinesi | **Visual Studio 2019 sürüm 16,1** : programın hata ayıklaması için makineyi belirtir. , [Genel](general-linux.md) sayfasında belirtilen uzak derleme makinesinden farklı olabilir. **Araç**  >  **seçenekleri**  >  **platformlar arası**  >  **Bağlantı Yöneticisi** ' ni kullanarak bir hedef makine bağlantısı ekleyebilir veya düzenleyebilirsiniz. |
| Başlatma öncesi komutu | Hata ayıklayıcı başlamadan önce kabukta çalıştırılan ve hata ayıklama ortamını etkilemek için kullanılabilen bir komut. |
| Program | Hata ayıklaması yapılacak programa uzak sistemdeki tam yol. Boş veya değiştirilmemiş bir şekilde bırakılırsa, varsayılan olarak geçerli proje çıktısı olur. |
| Program bağımsız değişkenleri | Hata ayıklamakta olan programa geçirilecek komut satırı bağımsız değişkenleri. |
| Çalışma dizini | Uzak uygulamanın çalışma dizini. Varsayılan olarak, Kullanıcı giriş dizinidir. |
| Ek hata ayıklayıcı komutları | Hata `gdb` ayıklayıcının hata ayıklamaya başlamadan önce çalıştırması için ek komutlar. |
| Hata ayıklayıcı bağlantı noktası numarası | Hata ayıklayıcı iletişim için uzaktan hata ayıklayıcı bağlantı noktası numarası. Bağlantı noktası yerel olarak kullanımda olmamalıdır. Bu değer pozitif ve 1 ile 65535 arasında olmalıdır. Sağlanmazsa, ücretsiz bir bağlantı noktası numarası kullanılır. |
| Uzaktan hata ayıklayıcı bağlantı noktası numarası | Uzaktan hata ayıklayıcı sunucusunun `gdbserver` uzak sistemde dinlediği bağlantı noktası numarası. Bağlantı noktası, uzak sistemde kullanımda olmamalıdır. Bu değer pozitif ve 1 ile 65535 arasında olmalıdır. Sağlanmazsa, 4444 'den başlayan ücretsiz bir bağlantı noktası numarası kullanılır. |
| Hata ayıklama modu | Hata ayıklayıcının ile nasıl arabirimlerin olduğunu belirtir `gdb` . *Gdb modunda* , hata ayıklayıcı `gdb` uzak sistemdeki kabuğa göre sürücüler. *Gdbserver modunda* `gdb` yerel olarak çalışır ve `gdbserver` Uzaktan çalışmaya bağlanır. | **gdbserver**<br/>**GDB** |
| Ek sembol arama yolları | Hata ayıklama sembolleri için ek arama yolu (solib-Search-Path). |
| Alt Işlemlerde hata ayıkla | Alt işlemlerde hata ayıklamanın etkinleştirilip etkinleştirilmeyeceğini belirtir. |
| Python 'un düzgün yazdırılmasını etkinleştir | İfade değerlerini düzgün şekilde yazdırmayı etkinleştirin. Yalnızca gdb hata ayıklama modunda desteklenir. |
| Görselleştirme dosyası | SLT türleri için görselleştirme yönergeleri içeren varsayılan yerel görselleştirme dosyası (. natvis). Geçerli çözüme ait olan diğer. natvis dosyaları otomatik olarak yüklenir. |
| Ek kaynaklar dosya yolu eşlemesi | Hata ayıklayıcının Windows kaynak dosya adlarını Linux kaynak dosya adlarıyla eşlemek için kullanacağı ek yol denklikleri. Biçim " \<windows-path> = \<linux-path> ;..." biçimindedir. Windows yolu altında bulunan bir kaynak dosya adına, Linux yolu altındaki aynı göreli konumda bulunan gibi başvurulur. Yerel projede bulunan dosyalar için ek eşleme gerekmez. |

::: moniker-end
