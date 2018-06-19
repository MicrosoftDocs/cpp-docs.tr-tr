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
ms.openlocfilehash: 43301686d5bdb964cf08e8123ff4c55475228567
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32383208"
---
# <a name="external-linkage"></a>Dış Bağlantı
İlk bildirim dosyası kapsam düzeyinde bir tanımlayıcı için kullanmıyorsa **statik** depolama sınıfı tanımlayıcısı, nesne dış bağlantı vardır.  
  
 Bir işlev için bir tanımlayıcı bildirimi Hayır varsa *depolama sınıfı tanımlayıcısı*, tam olarak bunu ile bildirilen gibi kendi bağlantı belirlenir *depolama sınıfı tanımlayıcısı* `extern`. Bir nesne için bir tanımlayıcı bildirimi dosya kapsamı ve no olup olmadığını *depolama sınıfı tanımlayıcısı*, kendi bağlantı dış.  
  
 Dış bağlantı bir tanımlayıcının adıyla aynı işlevi atar veya veri nesnesi olarak aynı ada sahip dış bağlantı için herhangi bir bildirim yapar. İki bildirimler aynı çeviri birimine veya farklı çeviri birimleri olabilir. Nesne veya işlevi de genel yaşam süresi varsa, nesne veya işlev tüm program tarafından paylaşılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlantıyı Belirtmek için extern Kullanma](../cpp/using-extern-to-specify-linkage.md)