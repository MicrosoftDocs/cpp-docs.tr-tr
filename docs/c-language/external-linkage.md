---
description: 'Daha fazla bilgi edinin: dış bağlantı'
title: Dış Bağlantı
ms.date: 11/04/2016
helpviewer_keywords:
- linkage [C++], external
- external linkage, about external linkage
- external linkage
ms.assetid: a6f8ea69-b405-4cdd-bf12-ad5462b73183
ms.openlocfilehash: 6920183c53067462dbaadb8514bf747300eb6a1c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97196288"
---
# <a name="external-linkage"></a>Dış Bağlantı

Bir tanımlayıcı için dosya kapsam düzeyindeki ilk bildirim **`static`** depolama sınıfı belirticisini kullanmıyorsa, nesnenin dış bağlantısı vardır.

Bir işlevin tanımlayıcısının bildiriminde hiçbir *depolama sınıfı Belirleyicisi* yoksa, bağlantısı tam olarak *depolama sınıfı belirticisiyle* bildirildiği gibi belirlenir **`extern`** . Bir nesne için tanımlayıcı bildiriminde dosya kapsamı varsa ve *depolama sınıfı Belirleyicisi* yoksa, bağlantısı harici olur.

Dış bağlantıya sahip bir tanımlayıcının adı aynı işlevi veya veri nesnesini, dış bağlantısıyla aynı ada sahip başka bir bildirime sahip olacak şekilde atar. İki bildirim aynı çeviri biriminde veya farklı çeviri birimlerinde olabilir. Nesne veya işlevin genel ömrü de varsa, nesne veya işlev tüm program tarafından paylaşılır.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlantıyı Belirtmek için extern Kullanma](../cpp/extern-cpp.md)
