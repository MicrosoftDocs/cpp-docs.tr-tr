---
title: "Gerekli ve isteğe bağlı başlık dosyaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.headers
dev_langs: C++
helpviewer_keywords:
- include files, required in run time
- header files, required in run time
ms.assetid: f64d0bf5-e2c3-4b42-97d0-443b3d901d9f
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 45e9d2e6940955b07624b89cafd09b7d89d9cd2c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="required-and-optional-header-files"></a>Gerekli ve İsteğe Bağlı Başlık Dosyaları
Gerekli ve isteğe bağlı bir listesini her çalıştırma yordamı açıklamasını içerir içeren veya üstbilgisi (. H), bu yordamı için dosyaları. Yordamın veya dahili olarak adlı başka bir yordamı tarafından kullanılan bir tanımını işlevi bildirimi almak için eklenmesi gereken üstbilgi dosyaları gerekir. İsteğe bağlı başlık dosyaları önceden tanımlanmış sabitler, tür tanımları veya satır içi makrolar yararlanmak için genellikle eklenmiştir. Aşağıdaki tabloda isteğe bağlı üstbilgi dosya içeriğinin bazı örnekler listelenmiştir:  
  
|Tanım|Örnek|  
|----------------|-------------|  
|Makro tanımı|Bir kitaplık yordamı makro olarak uygulanmışsa makro tanımı üstbilgi dosyasında özgün yordamı için üstbilgi dosyası dışında olabilir. Örneğin, `_toupper` makrosu CTYPE üstbilgi dosyasında tanımlanır. İşlev yüklenirken H `toupper` STDLIB bildirilir. H.|  
|Önceden tanımlanmış sabiti|Birçok kitaplık yordamları üstbilgi dosyalarında tanımlanan sabitleri bakın. Örneğin, `_open` yordamı kullanır sabitleri gibi `_O_CREAT`, FCNTL üstbilgi dosyasında tanımlı. H.|  
|Tür tanımı|Bazı kitaplık yordamları bir yapı döndürür veya bağımsız değişken olarak bir yapı alır. Örneğin, akış giriş/çıkış yordamları türü yapısını kullanmak `FILE`, STDIO tanımlanmış. H.|  
  
 Çalışma Zamanı Kitaplığı üstbilgi dosyaları ANSI/ISO C Standart önerilen stil işlev bildirimleri sağlar. Derleyici türü ilişkili işlevi bildiriminden sonra oluşan her türlü rutin referans denetimi gerçekleştirir. İşlev bildirimleri dışındaki bazı türünde bir değer döndüren yordamları için özellikle önemli `int`, varsayılan değerdir. Kendi uygun belirtmeyin yordamları dönüş değeri kendi bildiriminde göz önünde bulundurulmalı derleyici tarafından döndürülecek bir `int`, hangi beklenmeyen sonuçlara neden olabilir. Bkz: [tür denetlemesi](../c-runtime-library/type-checking-crt.md) daha fazla bilgi için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRT kitaplık özellikleri](../c-runtime-library/crt-library-features.md)