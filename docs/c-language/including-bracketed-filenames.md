---
title: Köşeli parantez içindeki dosya adlarını dahil etme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 6a4e5411-c35e-48b8-90ef-b37ac324ed94
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 37b4d0e6ccf0c0c01671082d2596528632fba6cb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46100870"
---
# <a name="including-bracketed-filenames"></a>Köşeli Parantez İçindeki Dosya Adlarını Dahil Etme

**ANSI 3.8.2** dahil edilebilecek kaynak dosyalarını bulma yöntemi

Köşeli ayraçlar içine alınan dosya belirtimleri için, önişlemci ana dosyaların dizinlerinde arama yapmaz. "Üst" dosya içeren dosyadır [#include](../preprocessor/hash-include-directive-c-cpp.md) da yönergesi. Bunun yerine, derleyici komut satırında /I öğesinden sonra belirtilen dizinlerde dosyayı arayarak başlar. /I seçeneği mevcut değil veya başarısız olursa önişlemci açılı ayraç içindeki içerik dosyalarını bulmak için Include ortam değişkeni kullanır. INCLUDE ortam değişkeni, noktalı virgülle ayırarak birden fazla yol içerebilir (**;**). /I seçeneği veya INCLUDE ortam değişkeni içinde bir parçası olarak birden fazla dizin görünüyorsa önişlemci bunları göründükleri sırayla arar.

## <a name="see-also"></a>Ayrıca Bkz.

[Ön işleme Yönergeleri](../c-language/preprocessing-directives.md)