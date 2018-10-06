---
title: Önemli hata C1060 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1060
dev_langs:
- C++
helpviewer_keywords:
- C1060
ms.assetid: feaf305c-c84c-4160-b974-50e283412849
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1961784efc61c3c31f87c76cd2bdfe00fe954c5d
ms.sourcegitcommit: a738519aa491a493a8f213971354356c0e6a5f3a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2018
ms.locfileid: "48820710"
---
# <a name="fatal-error-c1060"></a>Önemli hata C1060

Derleyicinin yığın alanı yetersiz olduğu

İşletim sistemi ya da çalışma zamanı kitaplığı, bellek isteği doldurun olamaz.

### <a name="to-fix-this-error-try-the-following-possible-solutions"></a>Bu hatayı düzeltmek için aşağıdaki olası çözümleri deneyin

1. Derleyici hataları yayımlıyorsa [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md) ve [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md), kullanın [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) daha düşük bellek ayırma sınırı derleyici seçeneği. Daha fazla yığın alanı, kalan bellek ayırma düşürürseniz, uygulamanız için kullanılabilir.

     Varsa [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) seçeneği zaten ayarlanmışsa, bu kaldırmayı deneyin. Seçeneğinde belirtilen bellek ayırma sınırını çok yüksek olduğu için yığın alanı tüketilebilir. Kaldırırsanız derleyici varsayılan bir sınırı kullanır [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) seçeneği.

1. 64-bit bir platform üzerinde derleme yapıyorsanız, 64 bit derleyici araç setini kullanın. Bilgi için [nasıl yapılır: bir 64 Bit Visual C++ araç takımını komut satırında etkinleştirme](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md).

1. 32 bit Windows üzerinde kullanmayı deneyin [3 GB](https://support.microsoft.com/help/833721/available-switch-options-for-the-windows-xp-and-the-windows-server-200) boot.ini anahtarı.

1. Windows takas dosyası boyutunu artırın.

1. Diğer çalışan programları kapatın.

1. Gereksiz ekleme dosyalarını silin.

1. Gereksiz genel değişkenleri, örneğin, büyük bir diziyi bildirmek yerine dinamik bellek ayırma tarafından da ortadan kaldırır.

1. Kullanılmayan bildirimleri ortadan kaldırın.

9. Geçerli dosyayı daha küçük dosyalara bölün.