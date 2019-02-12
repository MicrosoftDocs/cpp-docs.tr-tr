---
title: Dış Bağlantı
ms.date: 11/04/2016
helpviewer_keywords:
- linkage [C++], external
- external linkage, about external linkage
- external linkage
ms.assetid: a6f8ea69-b405-4cdd-bf12-ad5462b73183
ms.openlocfilehash: 35b0fda1f501755640123f5181454a5c36b7e986
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56148783"
---
# <a name="external-linkage"></a>Dış Bağlantı

Tanımlayıcının dosya kapsamı düzeyinde ilk bildirimi kullanmıyorsa **statik** depolama sınıfı tanımlayıcısı, nesne dış bağlantısı vardır.

Tanımlayıcının bir işlev bildirimi Hayır varsa *depolama sınıfı tanımlayıcısı*, tam olarak bunu ile bildirilmiş olup olmadıklarına kendi bağlantı belirlenir *depolama sınıfı tanımlayıcısı* `extern`. Bildirimi bir nesne için bir tanımlayıcının dosya kapsamı ve Hayır varsa *depolama sınıfı tanımlayıcısı*, kendi bağlantısı dış değerdir.

Aynı işlevin bir tanımlayıcının dış bağlantısı adıyla belirtir veya başka bir bildirimin aynı ada sahip dış bağlantısı için veri nesnesi gibi yapar. İki bildirimi, aynı çeviri birimi içinde veya farklı bir çeviri birimi olabilir. Nesne veya işlev, nesne veya işlev de genel yaşam süresi varsa, tüm program tarafından paylaşılır.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlantıyı Belirtmek için extern Kullanma](../cpp/using-extern-to-specify-linkage.md)
