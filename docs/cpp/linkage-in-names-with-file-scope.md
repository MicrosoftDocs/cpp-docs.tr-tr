---
title: "Dosya kapsamlı Adlardaki | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- scope [C++], linkage rules
- linkage [C++], scope linkage rules
- names [C++], scope linkage rules
- static modifier, file scope
- static names and file scope
- file scope [C++]
- declarations [C++], external
- external linkage, scope linkage rules
- static variables, external declarations
ms.assetid: 38d3fa5e-1861-466e-a590-84b86f7b184e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 581d7798f4f3aaa409d843f8b7f3b5869b47407e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="linkage-in-names-with-file-scope"></a>Dosya Kapsamlı Adlardaki Bağlantı
Aşağıdaki bağlantı kuralları, şu dosya kapsamına sahip adlara (`typedef` ve numaralandırıcı adları dışındaki) uygulanır:  
  
-   Bir ad olarak açıkça bildirilirse **statik**, iç bağlantı varsa ve kendi çeviri birim içinde bir program öğesi tanımlar.  
  
-   Numaralandırıcı adları ve `typedef` adlarının bağlantısı yoktur.  
  
-   Dosya kapsamına sahip diğer tüm adların dış bağlantısı vardır.  
  
 **Microsoft özel**  
  
-   Dosya kapsamlı bir işlev adı olarak açıkça bildirilmiş varsa **satır içi**, bu örneği veya adresini başvurulan dış bağlantı vardır. Bu nedenle, dosya kapsamına sahip bir işlevin iç veya dış bağlantısı olabilir.  
  
 **SON Microsoft özel**  
  
 Bir sınıfın şu koşullarda bir iç bağlantısı vardır:  
  
-   Hiçbir C++ işlevi (örneğin, üye erişim denetimi, üye işlevleri, oluşturucular, yıkıcılar, vb.) kullanmıyorsa.  
  
-   Dış bağlantısı olan başka bir adın bildiriminde kullanılmıyorsa. Bu kısıtlama, dış bağlantıyla işlevlere geçirilen sınıf türündeki nesnelerin sınıfın dış bağlantıya sahip olmasına yol açacağı anlamına gelir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Program ve bağlantı](../cpp/program-and-linkage-cpp.md)