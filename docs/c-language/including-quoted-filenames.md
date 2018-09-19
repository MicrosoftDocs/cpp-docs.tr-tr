---
title: Alıntılanan dosya adlarını dahil olmak üzere | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 789a047e-ea38-4c99-b71d-a2ad9c81daee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d3e865df95d92dcad6b414da11677b5212e9a9f3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46109944"
---
# <a name="including-quoted-filenames"></a>Tırnak İşaretli Dosya Adlarını Dahil Etme

**ANSI 3.8.2** dahil edilebilecek kaynak dosyalarını tırnak işaretli ad desteği

Dahil edilecek dosya için, çift tırnak (" ") işareti içine alarak belirsiz olmayan, tam bir yol belirtimi belirtirseniz, önişlemci yalnızca bu yol belirtimini arar ve standart dizinleri yoksayar.

Olarak belirtilen dosyaları eklemek için [#include](../preprocessor/hash-include-directive-c-cpp.md) "path-spec", dizin arama ana dosyanın dizinlerle başlar ve daha üst dosyaların dizinleriyle devam eder. Bu nedenle arama, işlenmekte olan kaynak dosyayı içeren dizine göre başlar. Dosya adı köşeli ayraçlar içine alınan iki üst dosya yok ve dosyayı bulunamadı, arama gibi devam eder.

## <a name="see-also"></a>Ayrıca Bkz.

[Ön işleme Yönergeleri](../c-language/preprocessing-directives.md)