---
title: "Ömür | Microsoft Docs"
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
- local variables, lifetime
- variables, automatic
- storage classes, lifetime
- variables, lifetime
- automatic storage class
- automatic storage class, duration
- storage class specifiers, storage duration
- memory allocation, dynamic allocation
- functions [C++], lifetime
- storage duration
- dynamic memory allocation
- memory allocation, dynamic
- lifetime
- global variables, lifetime
ms.assetid: ff0b42cb-3f0f-49a3-a94f-d1d825d8ddfe
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8ce98025001529313260f62e8f45e85add148c77
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="lifetime"></a>Ömür
"Ömrü" olan bir programın yürütülmesini dönemde bulunduğu bir değişken veya işlev içinde. Depolama süresi tanımlayıcının yaşam süresi belirler.  
  
 Bir tanımlayıcı ile bildirilen *depolama sınıfı tanımlayıcısı* **statik** statik depolama süresi vardır. Tanımlayıcılar ("Genel" da denir) statik depolama süresi ile bir program boyunca depolama ve tanımlı bir değer vardır. Depolama ayrılır ve kimliğinin depolanan değer yalnızca bir kez program başlatma önce başlatılır. Tanımlayıcı bildirilen dış veya iç bağlantı de statik depolama süresi vardır (bkz [bağlantı](../c-language/linkage.md)).  
  
 Tanımlayıcı olmadan bildirilen **statik** depolama sınıfı tanımlayıcısı varsa otomatik depolama süresi içinde bir işlev bildirilmiş. Otomatik depolama süresi ile bir tanımlayıcı ("yerel tanımlayıcısı") depolama ve burada tanımlayıcısı tanımlı veya bildirilen yalnızca blok içinde tanımlanmış bir değere sahip. Otomatik tanımlayıcı program girer, blok her zaman yeni depolama ayrılır ve depolama alanı (ve değerini) kaybeder program blok çıktığında. Bağlantısı olmayan bir işlev içinde bildirilen tanımlayıcıları da otomatik depolama süresi vardır.  
  
 Aşağıdaki kuralları bir tanımlayıcı genel (statik) veya yerel (otomatik) ömrü sahip olup olmadığını belirtin:  
  
-   Tüm işlevleri statik ömrü vardır. Bu nedenle, her zaman program yürütülmesi sırasında kalırlar. Tanımlayıcıları bildirilen dış düzeyinde (diğer bir deyişle, tüm dış işlev tanımları aynı düzeyde programında engeller) her zaman genel (statik) yaşam süresi vardır.  
  
-   Yerel değişkene bir başlatıcı varsa, her seferinde onu oluşturulur değişkeni başlatılır (olarak bildirilir sürece **statik**). İşlev parametreleri de yerel ömrü vardır. Bir bloğu içinde bir tanımlayıcı için genel yaşam süresini dahil ederek belirtebilirsiniz **statik** bildiriminden depolama sınıfı tanımlayıcısı. Bir kez bildirilen **statik**, bloğun bir giriş değerinden sonraki değişkeni korur.  
  
 Kaynak program yürütme tanıtıcıya sahip bir genel bulunmasına karşın (örneğin, bir harici olarak bildirilen değişkeni veya ile bildirilen yerel değişken **statik** anahtar sözcüğü), tüm görünür olmayabilir program bölümlerini. Bkz: [kapsam ve görünürlük](../c-language/scope-and-visibility.md) görünürlük ve bakın hakkında bilgi için [depolama sınıfları](../c-language/c-storage-classes.md) bir irdelemesi *depolama sınıfı tanımlayıcısı* nonterminal.  
  
 Bellek ayrılan kullanımı ile özel kitaplık yordamları gibi oluşturduysanız (dinamik) gerektiği gibi `malloc`. Dinamik bellek ayırma kitaplık yordamları kullandığından, dil parçası dikkate alınmaz. Bkz: [malloc](../c-runtime-library/reference/malloc.md) işlevi *çalışma zamanı kitaplığı başvurusu*.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ömür, Kapsam, Görünürlük ve Bağlantı](../c-language/lifetime-scope-visibility-and-linkage.md)