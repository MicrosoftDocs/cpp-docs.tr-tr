---
title: Dosya kapsamlı Adlardaki | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 770b30516d16cf9ffccaae4724b368ca8fa33be0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32419787"
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
 [Program ve Bağlantı](../cpp/program-and-linkage-cpp.md)