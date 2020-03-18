---
title: Hata ayıklayıcı özellikleri ( C++Linux) | Microsoft Docs
ms.date: 06/07/2019
ms.assetid: 0c1c0fcc-a49b-451c-a5cb-ce9711fac064
ms.openlocfilehash: bebee7a2b3bcfd880a538acae35c9616b3b1bd46
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446185"
---
# <a name="c-debugging-properties-linux-c"></a>C++Hata ayıklama özellikleri ( C++Linux)

::: moniker range="vs-2015"

Linux desteği, Visual Studio 2017 ve üzeri sürümlerde kullanılabilir.

::: moniker-end

::: moniker range=">=vs-2017"

| Özellik | Açıklama | Yapabileceği |
|--|--|--|
| Uzaktan hata ayıklama makinesi | **Visual Studio 2019 sürüm 16,1**: programın hata ayıklaması için makineyi belirtir. , [Genel](general-linux.md) sayfasında belirtilen uzak derleme makinesinden farklı olabilir. **Platformlar arası** > **bağlantı yöneticisi** > **Araçlar** > **seçeneklerini** kullanarak bir hedef makine bağlantısı ekleyebilir veya düzenleyebilirsiniz. |
| Başlatma öncesi komutu | Hata ayıklayıcı başlamadan önce kabukta çalıştırılan ve hata ayıklama ortamını etkilemek için kullanılabilen bir komut. |
| Program | Hata ayıklaması yapılacak programa uzak sistemdeki tam yol. Boş veya değiştirilmemiş bir şekilde bırakılırsa, varsayılan olarak geçerli proje çıktısı olur. |
| Program bağımsız değişkenleri | Hata ayıklamakta olan programa geçirilecek komut satırı bağımsız değişkenleri. |
| Çalışma Dizini | Uzak uygulamanın çalışma dizini. Varsayılan olarak, Kullanıcı giriş dizinidir. |
| Ek hata ayıklayıcı komutları | Hata ayıklayıcının hata ayıklamaya başlamadan önce çalıştırılacağı ek `gdb` komutları. |
| Hata ayıklayıcı bağlantı noktası numarası | Hata ayıklayıcı iletişim için uzaktan hata ayıklayıcı bağlantı noktası numarası. Bağlantı noktası yerel olarak kullanımda olmamalıdır. Bu değer pozitif ve 1 ile 65535 arasında olmalıdır. Sağlanmazsa, ücretsiz bir bağlantı noktası numarası kullanılır. |
| Uzaktan hata ayıklayıcı bağlantı noktası numarası | Uzaktan hata ayıklayıcı sunucusunun `gdbserver` uzak sistemde dinlediği bağlantı noktası numarası. Bağlantı noktası, uzak sistemde kullanımda olmamalıdır. Bu değer pozitif ve 1 ile 65535 arasında olmalıdır. Sağlanmazsa, 4444 'den başlayan ücretsiz bir bağlantı noktası numarası kullanılır. |
| Hata ayıklama modu | Hata ayıklayıcının `gdb`ile nasıl arabirim oluşturulacağını belirtir. *Gdb modunda*, hata ayıklayıcı sürücüleri uzak sistemdeki kabuğun üzerinde `gdb`. *Gdbserver modunda*, `gdb` yerel olarak çalışır ve uzaktan çalışan `gdbserver` bağlanır. | **gdbserver**<br/>**GDB** |
| Ek sembol arama yolları | Hata ayıklama sembolleri için ek arama yolu (solib-Search-Path). |
| Alt Işlemlerde hata ayıkla | Alt işlemlerde hata ayıklamanın etkinleştirilip etkinleştirilmeyeceğini belirtir. |
| Python 'un düzgün yazdırılmasını etkinleştir | İfade değerlerini düzgün şekilde yazdırmayı etkinleştirin. Yalnızca gdb hata ayıklama modunda desteklenir. |
| Görselleştirme dosyası | SLT türleri için görselleştirme yönergeleri içeren varsayılan yerel görselleştirme dosyası (. natvis). Geçerli çözüme ait olan diğer. natvis dosyaları otomatik olarak yüklenir. |
| Ek kaynaklar dosya yolu eşlemesi | Hata ayıklayıcının Windows kaynak dosya adlarını Linux kaynak dosya adlarıyla eşlemek için kullanacağı ek yol denklikleri. Biçim, "\<Windows-Path > =\<Linux-Path >;..." biçimindedir. Windows yolu altında bulunan bir kaynak dosya adına, Linux yolu altındaki aynı göreli konumda bulunan gibi başvurulur. Yerel projede bulunan dosyalar için ek eşleme gerekmez. |

::: moniker-end
