---
title: Dış bağlantı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- linkage [C++], external
- external linkage, about external linkage
- external linkage
ms.assetid: a6f8ea69-b405-4cdd-bf12-ad5462b73183
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: be268dbc153ad0bb140a2adfcfd8ec6385716c48
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46027569"
---
# <a name="external-linkage"></a>Dış Bağlantı

Tanımlayıcının dosya kapsamı düzeyinde ilk bildirimi kullanmıyorsa **statik** depolama sınıfı tanımlayıcısı, nesne dış bağlantısı vardır.

Tanımlayıcının bir işlev bildirimi Hayır varsa *depolama sınıfı tanımlayıcısı*, tam olarak bunu ile bildirilmiş olup olmadıklarına kendi bağlantı belirlenir *depolama sınıfı tanımlayıcısı* `extern`. Bildirimi bir nesne için bir tanımlayıcının dosya kapsamı ve Hayır varsa *depolama sınıfı tanımlayıcısı*, kendi bağlantısı dış değerdir.

Aynı işlevin bir tanımlayıcının dış bağlantısı adıyla belirtir veya başka bir bildirimin aynı ada sahip dış bağlantısı için veri nesnesi gibi yapar. İki bildirimi, aynı çeviri birimi içinde veya farklı bir çeviri birimi olabilir. Nesne veya işlev, nesne veya işlev de genel yaşam süresi varsa, tüm program tarafından paylaşılır.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlantıyı Belirtmek için extern Kullanma](../cpp/using-extern-to-specify-linkage.md)