---
title: Dış Bağlantı
ms.date: 11/04/2016
helpviewer_keywords:
- linkage [C++], external
- external linkage, about external linkage
- external linkage
ms.assetid: a6f8ea69-b405-4cdd-bf12-ad5462b73183
ms.openlocfilehash: 05fd4bd07aca995a938c7744dfd506d2a71b8774
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217096"
---
# <a name="external-linkage"></a>Dış Bağlantı

Bir tanımlayıcı için dosya kapsam düzeyindeki ilk bildirim **`static`** depolama sınıfı belirticisini kullanmıyorsa, nesnenin dış bağlantısı vardır.

Bir işlevin tanımlayıcısının bildiriminde hiçbir *depolama sınıfı Belirleyicisi*yoksa, bağlantısı tam olarak *depolama sınıfı belirticisiyle* bildirildiği gibi belirlenir **`extern`** . Bir nesne için tanımlayıcı bildiriminde dosya kapsamı varsa ve *depolama sınıfı Belirleyicisi*yoksa, bağlantısı harici olur.

Dış bağlantıya sahip bir tanımlayıcının adı aynı işlevi veya veri nesnesini, dış bağlantısıyla aynı ada sahip başka bir bildirime sahip olacak şekilde atar. İki bildirim aynı çeviri biriminde veya farklı çeviri birimlerinde olabilir. Nesne veya işlevin genel ömrü de varsa, nesne veya işlev tüm program tarafından paylaşılır.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlantıyı Belirtmek için extern Kullanma](../cpp/using-extern-to-specify-linkage.md)
