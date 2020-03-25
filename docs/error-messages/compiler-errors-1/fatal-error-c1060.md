---
title: Önemli hata C1060
ms.date: 11/04/2016
f1_keywords:
- C1060
helpviewer_keywords:
- C1060
ms.assetid: feaf305c-c84c-4160-b974-50e283412849
ms.openlocfilehash: f1a7c3ccab716a9281d4520f4c5fce2afff60187
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80204444"
---
# <a name="fatal-error-c1060"></a>Önemli hata C1060

Derleyicinin yığın alanı kalmadı

İşletim sistemi veya çalışma zamanı kitaplığı bir bellek isteğini dolduramaz.

### <a name="to-fix-this-error-try-the-following-possible-solutions"></a>Bu hatayı onarmak için aşağıdaki olası çözümleri deneyin

1. Derleyici Ayrıca [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md) ve [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md)hatalarını da kullanıyorsa, bellek ayırma sınırını düşürmek için [/ZD](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) derleyici seçeneğini kullanın. Kalan bellek ayırmayı düşürürseniz, uygulamanız için daha fazla yığın alanı kullanılabilir.

   [/Zı](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) seçeneği zaten ayarlandıysa, kaldırmayı deneyin. Seçeneğinde belirtilen bellek ayırma sınırı çok yüksek olduğu için yığın alanı tükeniyor olabilir. [/ZD](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) seçeneğini kaldırırsanız, derleyici varsayılan sınırı kullanır.

1. 64 bitlik bir platformda derlerken, 64 bit derleyici araç takımını kullanın. Bilgi için bkz. [nasıl yapılır: 64 bitlik görsel C++ araç takımını komut satırında etkinleştirme](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md).

1. 32 bit Windows üzerinde [/3GB](https://support.microsoft.com/help/833721/available-switch-options-for-the-windows-xp-and-the-windows-server-200) Boot. ini anahtarını kullanmayı deneyin.

1. Windows takas dosyasının boyutunu artırın.

1. Çalışan diğer programları kapatın.

1. Gereksiz ekleme dosyalarını silin.

1. Örneğin, büyük bir dizi bildirmek yerine, dinamik olarak bellek ayırarak gereksiz genel değişkenleri kaldırın.

1. Kullanılmayan bildirimleri ortadan kaldırın.

9. Geçerli dosyayı daha küçük dosyalara bölün.
