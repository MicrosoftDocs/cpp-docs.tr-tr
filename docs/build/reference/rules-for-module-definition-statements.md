---
title: "Modül tanımlama deyimleri kuralları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- .def
dev_langs:
- C++
helpviewer_keywords:
- module definition files, statement syntax
- module definition files
ms.assetid: f65cd3a7-65d7-4d06-939f-a8b1ecd50f2d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 40eb4875b195871aff8d274667e005d63424a110
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="rules-for-module-definition-statements"></a>Modül Tanımlama Deyimleri Kuralları
Aşağıdaki sözdizimi kurallarına .def dosyası tüm deyimlerinde uygulanır. Her deyimiyle belirli deyimleri için geçerli bir diğer kurallar açıklanmaktadır.  
  
-   Deyimler, öznitelik anahtar sözcükleri ve kullanıcı tarafından belirtilen tanımlayıcıları büyük/küçük harfe duyarlıdır.  
  
-   Uzun dosya adları boşluk veya noktalı virgül (;) içeren tırnak işaretleri (") içine alınmalıdır.  
  
-   Bir veya daha fazla boşluk, sekme veya yeni satır karakterlerini deyimi anahtar sözcüğü kendi bağımsız değişkenlerden ayırmak ve deyimleri birbirinden ayırmak için kullanın. İki nokta üst üste (:) veya sıfır veya daha fazla boşluk, sekme veya yeni satır karakterlerini tarafından bir bağımsız değişken atayan eşittir (=) çevrelenmiş.  
  
-   A **adı** veya **Kitaplığı** deyimi, kullandıysanız, önce gelmelidir diğer deyimler.  
  
-   **Bölümleri** ve **dışarı** deyimleri .def dosyasında birden çok kez görüntülenebilir. Her deyimi bir veya daha fazla boşluk, sekme veya yeni satır karakterlerini tarafından ayrılmalıdır birden çok belirtimleri alabilir. Deyim anahtar sözcüğü ilk belirtimi önce bir kez görünmesi gerekir ve her ek belirtimi önce yinelenebilir.  
  
-   Birçok deyimleri eşdeğer bağlantı komut satırı seçeneği sunulur. Daha fazla ayrıntı için karşılık gelen bağlantı seçeneği açıklamasına bakın.  
  
-   .Def dosyası açıklamaları noktalı virgül (;) belirtilen her yorum satırın başındaki. Bir yorum bir satır bir deyimiyle paylaşamazsınız, ancak çok satırlı deyiminde belirtimleri arasında yer alabilir. (**Bölümleri** ve **dışarı** çok satırlı deyimleri.)  
  
-   Belirtilen temel 10 ya da onaltılık sayısal bağımsız değişkenler.  
  
-   Dize bağımsız değişkeni eşleşmesi durumunda bir [ayrılmış sözcük](../../build/reference/reserved-words.md), çift tırnak işaretleri (") içine alınması gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Modül-Tanımlama (.Def) Dosyaları](../../build/reference/module-definition-dot-def-files.md)  