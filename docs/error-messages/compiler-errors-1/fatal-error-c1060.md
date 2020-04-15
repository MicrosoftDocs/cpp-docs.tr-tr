---
title: Önemli Hata C1060
ms.date: 11/04/2016
f1_keywords:
- C1060
helpviewer_keywords:
- C1060
ms.assetid: feaf305c-c84c-4160-b974-50e283412849
ms.openlocfilehash: 83135b77ceb75b4c2b05211260d1aed8fac6777f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320288"
---
# <a name="fatal-error-c1060"></a>Önemli Hata C1060

derleyici yığın alanı dışında

İşletim sistemi veya çalışma zamanı kitaplığı bellek isteğini dolduramaz.

### <a name="to-fix-this-error-try-the-following-possible-solutions"></a>Bu hatayı düzeltmek için aşağıdaki olası çözümleri deneyin

1. Derleyici [c1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md) ve [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md)hataları da varsa, bellek ayırma sınırını düşürmek için [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) derleyicisi seçeneğini kullanın. Kalan bellek ayırmayı düşürürseniz, uygulamanız için daha fazla yığın alanı kullanılabilir.

   [/ZM](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) seçeneği zaten ayarlanmışsa, kaldırmayı deneyin. Seçenekte belirtilen bellek ayırma sınırı çok yüksek olduğundan yığın alanı tükenmiş olabilir. [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) seçeneğini kaldırırsanız derleyici varsayılan bir sınır kullanır.

1. 64 bit platformda derleme yapıyorsunuz, 64 bit derleyici araç kümesini kullanın. Bilgi için [bkz: Komut Satırında 64 Bit Görsel C++ Araç Kümesini etkinleştirin.](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md)

1. 32 bit Windows'da [/3GB](https://support.microsoft.com/help/833721/available-switch-options-for-the-windows-xp-and-the-windows-server-200) boot.ini anahtarını kullanmayı deneyin.

1. Windows takas dosyasının boyutunu artırın.

1. Diğer çalışan programları kapatın.

1. Gereksiz ekleme dosyalarını silin.

1. Örneğin, büyük bir dizi bildirmek yerine belleği dinamik olarak ayırarak gereksiz genel değişkenleri ortadan kaldırın.

1. Kullanılmayan bildirimleri ortadan kaldırın.

1. Geçerli dosyayı daha küçük dosyalara bölün.
