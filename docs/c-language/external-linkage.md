---
title: Dış Bağlantı
ms.date: 11/04/2016
helpviewer_keywords:
- linkage [C++], external
- external linkage, about external linkage
- external linkage
ms.assetid: a6f8ea69-b405-4cdd-bf12-ad5462b73183
ms.openlocfilehash: 35b0fda1f501755640123f5181454a5c36b7e986
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62233747"
---
# <a name="external-linkage"></a>Dış Bağlantı

Bir tanımlayıcı için dosya kapsam düzeyindeki ilk bildirim **statik** depolama sınıfı belirticisini kullanmıyorsa, nesnenin dış bağlantısı vardır.

Bir işlevin tanımlayıcısının bildiriminde hiçbir *depolama sınıfı Belirleyicisi*yoksa, bağlantısı tam olarak *depolama sınıfı belirticisiyle* `extern`bildirildiği gibi belirlenir. Bir nesne için tanımlayıcı bildiriminde dosya kapsamı varsa ve *depolama sınıfı Belirleyicisi*yoksa, bağlantısı harici olur.

Dış bağlantıya sahip bir tanımlayıcının adı aynı işlevi veya veri nesnesini, dış bağlantısıyla aynı ada sahip başka bir bildirime sahip olacak şekilde atar. İki bildirim aynı çeviri biriminde veya farklı çeviri birimlerinde olabilir. Nesne veya işlevin genel ömrü de varsa, nesne veya işlev tüm program tarafından paylaşılır.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlantıyı Belirtmek için extern Kullanma](../cpp/using-extern-to-specify-linkage.md)
