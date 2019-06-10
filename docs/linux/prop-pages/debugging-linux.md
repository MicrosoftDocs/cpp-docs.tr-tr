---
title: Özellikleri (Linux C++) hata ayıklayıcı | Microsoft Docs
ms.date: 06/07/2019
ms.assetid: 0c1c0fcc-a49b-451c-a5cb-ce9711fac064
ms.openlocfilehash: d76e398d648db7c5cf65e4ca2bb1665aef4359ad
ms.sourcegitcommit: 8adabe177d557c74566c13145196c11cef5d10d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/10/2019
ms.locfileid: "66821405"
---
# <a name="c-debugging-properties-linux-c"></a>C++ hata ayıklama özellikleri (Linux C++)

::: moniker range="vs-2015"

Linux desteği, Visual Studio 2017 ile kullanılabilir ve üzerinde desteklenir.

::: moniker-end

::: moniker range=">=vs-2017"

Özellik | Açıklama | Seçenekleri
--- | ---| ---
Uzaktan hata ayıklama makinesi | **Visual Studio 2019 sürüm 16.1**: Programda hata ayıklamak için makineyi belirtir. Belirtilen uzak derleme makinesi değerinden farklı olabilir [genel](general-linux.md) sayfası.
Başlatma öncesi komut | Hata ayıklayıcı önce kabukta çalıştırılan bir komut başlatır ve hata ayıklama ortamını etkilemek için kullanılabilir.
Program | Uzak sistemde ayıklanacak programın tam yolu. Boş veya değişmemiş bırakılırsa, geçerli proje çıkışı için varsayılan olarak.
Program bağımsız değişkenleri | Ayıklanan programa geçirilecek komut satırı bağımsız değişkenleri.
Çalışma dizini | Uzak uygulamanın çalışma dizini. Varsayılan olarak, kullanıcının giriş dizinidir.
Ek hata ayıklayıcı komutları | Ek `gdb` ayıklamaya başlamadan önce çalıştırılacak hata ayıklayıcı komutları.
Hata ayıklayıcı bağlantı noktası numarası | Uzaktan hata ayıklayıcı ile hata ayıklayıcı iletişimi için bağlantı noktası numarası. Bağlantı noktası, yerel olarak kullanımda olmamalıdır. Bu değer, pozitif ve 1 ile 65535 arasında olmalıdır. Sağlanmazsa, bir serbest bağlantı noktası numarası kullanılır.
Uzaktan hata ayıklayıcı bağlantı noktası numarası | Üzerinde uzaktan hata ayıklayıcı sunucu bağlantı noktası numarası `gdbserver` uzak sistemde dinliyor. Bağlantı noktası uzak sistemde kullanımda olmamalıdır. Bu değer, pozitif ve 1 ile 65535 arasında olmalıdır. Sağlanmazsa, 4444'ten bir ücretsiz bağlantı noktası numarası kullanılır.
Hata ayıklama modu | Hata ayıklayıcı ile arabirimi nasıl belirtir `gdb`. İçinde *gdb modunda*, hata ayıklayıcı sürücüleri `gdb` Kabuğu uzak sistemde üzerinden. İçinde *gdbserver modunda*, `gdb` yerel olarak çalışır ve bağlandığı `gdbserver` uzaktan çalıştırmak. | **gdbserver**<br/>**gdb**
Ek sembol arama yolları | (Solib-search-path) hata ayıklama sembolleri için ek arama yolu.
Alt işlemlerde hata ayıklama | Alt işlemlerde hata ayıklamanın etkinleştirilip etkinleştirilmeyeceğini belirtir.
Etkinleştirme Python düzgün yazdırma | Düzgün ifade değerlerini yazdırma etkinleştirin. Yalnızca gdb hata ayıklama modunda desteklenir.
Görselleştirme dosyası | SLT türleri için görselleştirme yönergelerini içeren varsayılan yerel görselleştirme dosyası (.natvis). Geçerli çözüme ait diğer .natvis dosyaları otomatik olarak yüklenir.
Ek kaynaklar dosya yolu eşlemesi | Windows eşleştirmek için kullanılacak hata ayıklayıcı için ek yol denklikleri dosya adlarını Linux kaynak dosya adlarına kaynağı. Biçim "\<windows-path > =\<linux-path >;...". Windows yolu altında bulunan bir kaynak dosya adına Linux yolu altında aynı göreli konumda gibi bulunursa başvuruluyor. Yerel projede bulunan dosyalar ek eşleme gerekmez.

::: moniker-end
