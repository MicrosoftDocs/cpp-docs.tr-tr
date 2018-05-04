---
title: Modül tanımlama deyimleri kuralları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- .def
dev_langs:
- C++
helpviewer_keywords:
- module definition files, statement syntax
- module definition files
ms.assetid: f65cd3a7-65d7-4d06-939f-a8b1ecd50f2d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3f8de42480dae9be203a132561d722c18d6952c1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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