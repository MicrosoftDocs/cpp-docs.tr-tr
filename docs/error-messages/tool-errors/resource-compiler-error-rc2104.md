---
title: Kaynak Derleyicisi hatası RC2104 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC2104
dev_langs:
- C++
helpviewer_keywords:
- RC2104
ms.assetid: 792a3bd8-cb4c-4817-b288-4ce37082b582
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bd602dcde34aa7cc08486188ab5fb5925eca0eb2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46081097"
---
# <a name="resource-compiler-error-rc2104"></a>Kaynak Derleyicisi Hatası RC2104

tanımlanmamış anahtar veya anahtar adı: anahtar

Belirtilen anahtar veya anahtar adı tanımlı değil.

Bu hata genellikle kaynak tanımı'ndaki veya dahil edilen üstbilgi dosyasında bir yazım yanlışı kaynaklanır. Eksik bir üstbilgi dosyası tarafından da kaynaklanabilir.

Bu sorunu düzeltmek için kaynak dosyasına dahil edilir ve anahtar veya anahtar adının doğru yazıldığından emin olun ve tanımlanmış bir anahtar veya anahtar adını içeren üstbilgi dosyasını bulun. Önceden derlenmiş üstbilgiyle projeniz oluşturuldu ve daha sonra kaldırmak, emin olun, kaynak dosyası hala gerekli üst bilgileri içerir.

Visual Studio'da, kaynak dosyanızdaki anahtar adlarını ve tanımlı anahtar sözcükler doğrulamak için açık **kaynak görünümü** penceresi — menü çubuğunda, **görünümü**, **kaynak görünümü**— ve Ardından, bir .rc dosyası için kısayol menüsünü açın ve seçin **kaynak sembolleri** tanımlanmış sembol listesini görüntülemek için. Dahil edilen üst bilgileri değiştirmek için bir .rc dosyası için kısayol menüsünü açın ve seçin **kaynak içerikleri**.

Bu iletisiyle karşılaşırsanız:

```
undefined keyword or key name: MFT_STRING
```

\MCL\MFC\Include\AfxRes.h açın ve bunu ekleyin yönergesi:

```
#include <winresrc.h>
```