---
description: 'Aşağıdakiler hakkında daha fazla bilgi edinin: alıntı dosya adları dahil'
title: Tırnak İşaretli Dosya Adlarını Dahil Etme
ms.date: 11/04/2016
ms.assetid: 789a047e-ea38-4c99-b71d-a2ad9c81daee
ms.openlocfilehash: b07d8dc04106a330644c30bffd1e8f36fc81fb6d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137637"
---
# <a name="including-quoted-filenames"></a>Tırnak İşaretli Dosya Adlarını Dahil Etme

**ANSI 3.8.2 &** Dahil edilebilecek kaynak dosyalar için tırnak içine alınmış adlara yönelik destek

Dahil edilecek dosya için, çift tırnak (" ") işareti içine alarak belirsiz olmayan, tam bir yol belirtimi belirtirseniz, önişlemci yalnızca bu yol belirtimini arar ve standart dizinleri yoksayar.

[#İnclude](../preprocessor/hash-include-directive-c-cpp.md) "path-spec" olarak belirtilen içerme dosyaları için Dizin arama, üst dosyanın dizinleriyle başlar ve ardından herhangi bir alt üst dosyanın dizinlerine ilerler. Bu nedenle arama, işlenmekte olan kaynak dosyayı içeren dizine göre başlar. Herhangi bir üst öğe dosyası yoksa ve dosya bulunmazsa, dosya adı açılı ayraçlar içine alınmış gibi devam eder.

## <a name="see-also"></a>Ayrıca bkz.

[Ön işleme yönergeleri](../c-language/preprocessing-directives.md)
