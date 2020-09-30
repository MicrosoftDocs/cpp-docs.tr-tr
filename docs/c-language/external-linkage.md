---
title: Dış Bağlantı
ms.date: 11/04/2016
helpviewer_keywords:
- linkage [C++], external
- external linkage, about external linkage
- external linkage
ms.assetid: a6f8ea69-b405-4cdd-bf12-ad5462b73183
ms.openlocfilehash: d8a7655b7504aa8458bda8db24ff3f919b5b09c1
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509914"
---
# <a name="external-linkage"></a>Dış Bağlantı

Bir tanımlayıcı için dosya kapsam düzeyindeki ilk bildirim **`static`** depolama sınıfı belirticisini kullanmıyorsa, nesnenin dış bağlantısı vardır.

Bir işlevin tanımlayıcısının bildiriminde hiçbir *depolama sınıfı Belirleyicisi*yoksa, bağlantısı tam olarak *depolama sınıfı belirticisiyle* bildirildiği gibi belirlenir **`extern`** . Bir nesne için tanımlayıcı bildiriminde dosya kapsamı varsa ve *depolama sınıfı Belirleyicisi*yoksa, bağlantısı harici olur.

Dış bağlantıya sahip bir tanımlayıcının adı aynı işlevi veya veri nesnesini, dış bağlantısıyla aynı ada sahip başka bir bildirime sahip olacak şekilde atar. İki bildirim aynı çeviri biriminde veya farklı çeviri birimlerinde olabilir. Nesne veya işlevin genel ömrü de varsa, nesne veya işlev tüm program tarafından paylaşılır.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlantıyı Belirtmek için extern Kullanma](../cpp/extern-cpp.md)
