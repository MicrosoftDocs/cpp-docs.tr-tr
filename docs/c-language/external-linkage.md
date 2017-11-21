---
title: "Dış bağlantı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- linkage [C++], external
- external linkage, about external linkage
- external linkage
ms.assetid: a6f8ea69-b405-4cdd-bf12-ad5462b73183
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c4a1981d2dd22f9ed8928b1d1daf71612b057e71
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="external-linkage"></a>Dış Bağlantı
İlk bildirim dosyası kapsam düzeyinde bir tanımlayıcı için kullanmıyorsa **statik** depolama sınıfı tanımlayıcısı, nesne dış bağlantı vardır.  
  
 Bir işlev için bir tanımlayıcı bildirimi Hayır varsa *depolama sınıfı tanımlayıcısı*, tam olarak bunu ile bildirilen gibi kendi bağlantı belirlenir *depolama sınıfı tanımlayıcısı* `extern`. Bir nesne için bir tanımlayıcı bildirimi dosya kapsamı ve no olup olmadığını *depolama sınıfı tanımlayıcısı*, kendi bağlantı dış.  
  
 Dış bağlantı bir tanımlayıcının adıyla aynı işlevi atar veya veri nesnesi olarak aynı ada sahip dış bağlantı için herhangi bir bildirim yapar. İki bildirimler aynı çeviri birimine veya farklı çeviri birimleri olabilir. Nesne veya işlevi de genel yaşam süresi varsa, nesne veya işlev tüm program tarafından paylaşılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlantıyı belirtmek için extern kullanma](../cpp/using-extern-to-specify-linkage.md)