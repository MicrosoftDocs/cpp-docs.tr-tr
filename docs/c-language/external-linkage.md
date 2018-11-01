---
title: Dış Bağlantı
ms.date: 11/04/2016
helpviewer_keywords:
- linkage [C++], external
- external linkage, about external linkage
- external linkage
ms.assetid: a6f8ea69-b405-4cdd-bf12-ad5462b73183
ms.openlocfilehash: 87e9e16eb115df8d100450f7f0dc44961886ab20
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466267"
---
# <a name="external-linkage"></a>Dış Bağlantı

Tanımlayıcının dosya kapsamı düzeyinde ilk bildirimi kullanmıyorsa **statik** depolama sınıfı tanımlayıcısı, nesne dış bağlantısı vardır.

Tanımlayıcının bir işlev bildirimi Hayır varsa *depolama sınıfı tanımlayıcısı*, tam olarak bunu ile bildirilmiş olup olmadıklarına kendi bağlantı belirlenir *depolama sınıfı tanımlayıcısı* `extern`. Bildirimi bir nesne için bir tanımlayıcının dosya kapsamı ve Hayır varsa *depolama sınıfı tanımlayıcısı*, kendi bağlantısı dış değerdir.

Aynı işlevin bir tanımlayıcının dış bağlantısı adıyla belirtir veya başka bir bildirimin aynı ada sahip dış bağlantısı için veri nesnesi gibi yapar. İki bildirimi, aynı çeviri birimi içinde veya farklı bir çeviri birimi olabilir. Nesne veya işlev, nesne veya işlev de genel yaşam süresi varsa, tüm program tarafından paylaşılır.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlantıyı Belirtmek için extern Kullanma](../cpp/using-extern-to-specify-linkage.md)