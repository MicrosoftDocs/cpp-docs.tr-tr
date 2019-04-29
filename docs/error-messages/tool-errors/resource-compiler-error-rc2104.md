---
title: Kaynak Derleyicisi Hatası RC2104
ms.date: 11/04/2016
f1_keywords:
- RC2104
helpviewer_keywords:
- RC2104
ms.assetid: 792a3bd8-cb4c-4817-b288-4ce37082b582
ms.openlocfilehash: 6ac1786e795c0c8ed57af2d341f43b8ba39229c4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62346567"
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