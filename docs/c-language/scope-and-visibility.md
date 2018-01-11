---
title: "Kapsam ve görünürlük | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- scope, levels
- visibility
- file scope [C++]
ms.assetid: a019eb7c-66ed-46a7-bc9f-89a963930a56
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c61d9c6f38851e48335f83cccfeb5a8bf4aba448
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="scope-and-visibility"></a>Kapsam ve Görünürlük
İçinde başvurulabilir program bölümlerini bir tanımlayıcının "görünürlük" belirler — "kapsamı." Bir görünür bir tanımlayıcıdır (yani, kullanılabilir), (, restrictiveness artan sırada), dosya, işlev, blok veya işlev prototipi göründüğü sınırlı bölümleri kendi "kapsam tarafından" çevrelenmiş bir programın içinde. Tanımlayıcı kapsamını adı kullanılabilir program parçasıdır. Buna bazen "sözcük kapsamı." adı verilir Kapsam dört tür vardır: işlev, dosya, blok ve işlev prototipi.  
  
 Etiketler dışında tüm tanımlayıcılar bildirimi oluştuğu düzeyine göre belirlendiği kapsamlarına sahip. Her tür bir kapsam için aşağıdaki kuralı bir programdan tanımlayıcıların görünürlüğünü yöneten:  
  
 Dosya kapsamı  
 Bildirimcisi veya tür belirteci dosya kapsamlı bir tanımlayıcı için herhangi bir blok veya parametrelerin listesi dışında görünür ve bildiriminden sonra çeviri birimindeki herhangi bir yerden erişilebilir. Dosya kapsamlı tanımlayıcı adları genellikle "Genel" veya "dış" adı verilir Genel bir tanımlayıcı kapsamını, tanım veya bildirimi noktasında başlar ve çeviri birim sonunda sonlandırır.  
  
 İşlev kapsamı  
 Bir etiketi yalnızca işlev kapsamı tanımlayıcısı türüdür. Bir etiket kullanımını bir deyimi tarafından dolaylı olarak bildirildi. Etiket adları bir işlev içinde benzersiz olmalıdır. (Etiketleri ve etiket adları hakkında daha fazla bilgi için bkz: [goto ve etiketli deyimleri](../c-language/goto-and-labeled-statements-c.md).)  
  
 Blok kapsamı  
 Bildirimcisi veya blok kapsamlı bir tanımlayıcı için tür belirteci bloğunun bir ya da bir işlev tanımı biçimsel parametresi bildirimlerinde listesi içinde görüntülenir. Bunu yalnızca kendi bildirimi veya tanımı noktasından bildirimi veya tanımını içeren blok sonuna görülebilir. Kapsamı bu bloğuna ve o bloğu içinde iç içe geçmiş herhangi bir bloğu ile sınırlıdır ve ilişkili blok kapatır kuşak sona erer. Bu tür tanımlayıcıları adlandırılan "yerel değişkenler."  
  
 İşlev prototip kapsamı  
 Bildirimcisi veya tür belirteci işlev prototipi kapsamlı bir tanımlayıcı için bir işlev prototipi (işlev bildirimi parçası değil) parametre bildirimlerinde listesi içinde görüntülenir. Kapsamı işlevi bildirimcisi sonunda sonlandırır.  
  
 Değişkenleri diğer kaynak dosyalarında görünür yapmak için uygun bildirimleri açıklanan [depolama sınıfları](../c-language/c-storage-classes.md). Ancak, değişkenler ve işlevleri bildirilen dış düzeyi ile **statik** depolama sınıfı tanımlayıcısı yalnızca bunlar tanımlı kaynak dosya içinde görünür. Diğer tüm işlevleri genel olarak görünür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ömür, Kapsam, Görünürlük ve Bağlantı](../c-language/lifetime-scope-visibility-and-linkage.md)