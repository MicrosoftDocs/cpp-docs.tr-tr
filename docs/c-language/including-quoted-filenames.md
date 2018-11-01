---
title: Tırnak İşaretli Dosya Adlarını Dahil Etme
ms.date: 11/04/2016
ms.assetid: 789a047e-ea38-4c99-b71d-a2ad9c81daee
ms.openlocfilehash: 11beaa3a91f476348c57b12ab3febad7cb9c89fc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50656722"
---
# <a name="including-quoted-filenames"></a>Tırnak İşaretli Dosya Adlarını Dahil Etme

**ANSI 3.8.2** dahil edilebilecek kaynak dosyalarını tırnak işaretli ad desteği

Dahil edilecek dosya için, çift tırnak (" ") işareti içine alarak belirsiz olmayan, tam bir yol belirtimi belirtirseniz, önişlemci yalnızca bu yol belirtimini arar ve standart dizinleri yoksayar.

Olarak belirtilen dosyaları eklemek için [#include](../preprocessor/hash-include-directive-c-cpp.md) "path-spec", dizin arama ana dosyanın dizinlerle başlar ve daha üst dosyaların dizinleriyle devam eder. Bu nedenle arama, işlenmekte olan kaynak dosyayı içeren dizine göre başlar. Dosya adı köşeli ayraçlar içine alınan iki üst dosya yok ve dosyayı bulunamadı, arama gibi devam eder.

## <a name="see-also"></a>Ayrıca Bkz.

[Ön işleme Yönergeleri](../c-language/preprocessing-directives.md)