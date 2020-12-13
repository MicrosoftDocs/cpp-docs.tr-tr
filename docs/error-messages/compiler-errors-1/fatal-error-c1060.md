---
description: 'Daha fazla bilgi edinin: önemli hata C1060'
title: Önemli hata C1060
ms.date: 11/04/2016
f1_keywords:
- C1060
helpviewer_keywords:
- C1060
ms.assetid: feaf305c-c84c-4160-b974-50e283412849
ms.openlocfilehash: 149fd4108aabf603e844c6906e072a9c64578d5c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330727"
---
# <a name="fatal-error-c1060"></a>Önemli hata C1060

Derleyicinin yığın alanı kalmadı

İşletim sistemi veya çalışma zamanı kitaplığı bir bellek isteğini dolduramaz.

### <a name="to-fix-this-error-try-the-following-possible-solutions"></a>Bu hatayı onarmak için aşağıdaki olası çözümleri deneyin

1. Derleyici Ayrıca [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md) ve [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md)hatalarını da kullanıyorsa, bellek ayırma sınırını düşürmek için [/ZD](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) derleyici seçeneğini kullanın. Kalan bellek ayırmayı düşürürseniz, uygulamanız için daha fazla yığın alanı kullanılabilir.

   [/Zı](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) seçeneği zaten ayarlandıysa, kaldırmayı deneyin. Seçeneğinde belirtilen bellek ayırma sınırı çok yüksek olduğu için yığın alanı tükeniyor olabilir. [/ZD](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) seçeneğini kaldırırsanız, derleyici varsayılan sınırı kullanır.

1. 64 bitlik bir platformda derlerken, 64 bit derleyici araç takımını kullanın. Bilgi için, bkz. [nasıl yapılır: 64 bit Visual C++ araç takımını komut satırında etkinleştirme](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md).

1. 32 bit Windows üzerinde [/3gb](https://support.microsoft.com/help/833721/available-switch-options-for-the-windows-xp-and-the-windows-server-200) boot.ini anahtarını kullanmayı deneyin.

1. Windows takas dosyasının boyutunu artırın.

1. Çalışan diğer programları kapatın.

1. Gereksiz ekleme dosyalarını silin.

1. Örneğin, büyük bir dizi bildirmek yerine, dinamik olarak bellek ayırarak gereksiz genel değişkenleri kaldırın.

1. Kullanılmayan bildirimleri ortadan kaldırın.

1. Geçerli dosyayı daha küçük dosyalara bölün.
