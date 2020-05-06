---
title: Tırnak İşaretli Dosya Adlarını Dahil Etme
ms.date: 11/04/2016
ms.assetid: 789a047e-ea38-4c99-b71d-a2ad9c81daee
ms.openlocfilehash: 4083519d6f6b9b4d037b0c2998737f3a5062c6cf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62232962"
---
# <a name="including-quoted-filenames"></a>Tırnak İşaretli Dosya Adlarını Dahil Etme

**ANSI 3.8.2 &** Dahil edilebilecek kaynak dosyalar için tırnak içine alınmış adlara yönelik destek

Dahil edilecek dosya için, çift tırnak (" ") işareti içine alarak belirsiz olmayan, tam bir yol belirtimi belirtirseniz, önişlemci yalnızca bu yol belirtimini arar ve standart dizinleri yoksayar.

[#İnclude](../preprocessor/hash-include-directive-c-cpp.md) "path-spec" olarak belirtilen içerme dosyaları için Dizin arama, üst dosyanın dizinleriyle başlar ve ardından herhangi bir alt üst dosyanın dizinlerine ilerler. Bu nedenle arama, işlenmekte olan kaynak dosyayı içeren dizine göre başlar. Herhangi bir üst öğe dosyası yoksa ve dosya bulunmazsa, dosya adı açılı ayraçlar içine alınmış gibi devam eder.

## <a name="see-also"></a>Ayrıca bkz.

[Ön işleme Yönergeleri](../c-language/preprocessing-directives.md)
