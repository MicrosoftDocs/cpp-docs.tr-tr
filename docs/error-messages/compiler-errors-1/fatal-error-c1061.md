---
title: "Önemli hata C1061 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1061
dev_langs:
- C++
helpviewer_keywords:
- C1061
ms.assetid: 9366c0bc-96e0-4967-aa7d-4ebf098de806
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 81963b0fffdf1b86b56b10c0776874b37ae9daa2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1061"></a>Önemli hata C1061
derleyici sınırı: bloklar çok derin şekilde iç içe geçmiş  
  
 Kod bloklarının iç içe geçmesi, 128 iç içe geçme düzeyini aşıyor. Bu, hem 32-bit hem de 64-bit araç kümesinde C ve C++için derleyicideki kesin sınırdır. İç içe geçme düzeylerinin sayısı, bir kapsam ya da blok oluşturan herhangi bir şey tarafından artırılabilir. Örneğin, ad alanları, kullanma yönergeleri, önişlemci genişletmeleri, şablon genişletme, özel durum işleme, döngü yapıları ve else-if yan tümceleri tüm derleyici tarafından görülen iç içe geçme düzeyini artırabilir.  
  
 Bu hatayı düzeltmek için kodunuzu yeniden düzenlemelisiniz. Her durumda, derin bir biçimde iç içe geçmiş kodu anlamak zordur. Kodunuzu daha az iç içe geçme düzeyine sahip olacak şekilde yeniden düzenlemeniz, kodunuzun kalitesini artırabilir ve bakımı kolaylaştırabilir. Derin bir biçimde iç içe geçmiş kodu, orijinal içerikten çağrılan işlevlere ayırın. Bir blok içindeki döngü sayısını veya zincirli else-if yan tümcelerinin sayısını sınırlayın.