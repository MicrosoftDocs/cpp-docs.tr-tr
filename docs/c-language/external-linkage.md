---
title: "Dış bağlantı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- linkage [C++], external
- external linkage, about external linkage
- external linkage
ms.assetid: a6f8ea69-b405-4cdd-bf12-ad5462b73183
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: aef61c580306cc40ef1a89c6a389c7fbaf64a5f9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="external-linkage"></a>Dış Bağlantı
İlk bildirim dosyası kapsam düzeyinde bir tanımlayıcı için kullanmıyorsa **statik** depolama sınıfı tanımlayıcısı, nesne dış bağlantı vardır.  
  
 Bir işlev için bir tanımlayıcı bildirimi Hayır varsa *depolama sınıfı tanımlayıcısı*, tam olarak bunu ile bildirilen gibi kendi bağlantı belirlenir *depolama sınıfı tanımlayıcısı* `extern`. Bir nesne için bir tanımlayıcı bildirimi dosya kapsamı ve no olup olmadığını *depolama sınıfı tanımlayıcısı*, kendi bağlantı dış.  
  
 Dış bağlantı bir tanımlayıcının adıyla aynı işlevi atar veya veri nesnesi olarak aynı ada sahip dış bağlantı için herhangi bir bildirim yapar. İki bildirimler aynı çeviri birimine veya farklı çeviri birimleri olabilir. Nesne veya işlevi de genel yaşam süresi varsa, nesne veya işlev tüm program tarafından paylaşılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlantıyı Belirtmek için extern Kullanma](../cpp/using-extern-to-specify-linkage.md)