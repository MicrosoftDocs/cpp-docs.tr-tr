---
title: Kaynak Derleyicisi Hatası RC2104
ms.date: 11/04/2016
f1_keywords:
- RC2104
helpviewer_keywords:
- RC2104
ms.assetid: 792a3bd8-cb4c-4817-b288-4ce37082b582
ms.openlocfilehash: d4a06f88e4a73da6b711d108a1f79c14fae0907c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80191645"
---
# <a name="resource-compiler-error-rc2104"></a>Kaynak Derleyicisi Hatası RC2104

tanımsız anahtar sözcük veya anahtar adı: anahtar

Belirtilen anahtar sözcük veya anahtar adı tanımlı değil.

Bu hata genellikle kaynak tanımındaki bir yazım hatası veya eklenen üst bilgi dosyasında oluşur. Ayrıca, eksik bir üst bilgi dosyası olabilir.

Sorunu düzeltemedi, tanımlanmış anahtar sözcüğü veya anahtar adını içermesi gereken başlık dosyasını bulun ve kaynak dosyanıza dahil olduğunu ve anahtar sözcüğünün ya da anahtar adının doğru yazıldığından emin olun. Projeniz önceden derlenmiş bir üstbilgiyle oluşturulmuşsa ve daha sonra kaldırırsanız, kaynak dosyasında gerekli tüm üstbilgileri hala içerdiğinden emin olun.

Kaynak dosyanızdaki tanımlı anahtar sözcükleri ve anahtar adlarını doğrulamak için, Visual Studio 'da **kaynak görünümü** penceresini açın — menü çubuğunda **görüntüle**, **kaynak görünümü**— öğesini seçin ve ardından. rc dosyasının kısayol menüsünü açın ve **kaynak sembolleri** ' yi seçerek tanımlı simgelerin listesini görüntüleyin. Dahil edilen üst bilgileri değiştirmek için. rc dosyasının kısayol menüsünü açın ve **kaynak içerme**' yi seçin.

Bu iletiyle karşılaşırsanız:

```
undefined keyword or key name: MFT_STRING
```

\MCL\MFC\Include\AfxRes.h dosyasını açın ve bu ekleme yönergesini ekleyin:

```
#include <winresrc.h>
```
