---
title: 2.7.2.3 lastprivate | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 77f6a5c9-704f-4a88-8476-29db852ed800
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 08f331862d6e48b1c0882382285ddffa9699e79c
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="2723-lastprivate"></a>2.7.2.3 lastprivate
`lastprivate` Yan tümcesi tarafından sağlanan işlevleri bir alt kümesi sağlar `private` yan tümcesi. Söz dizimi `lastprivate` yan tümcesi aşağıdaki gibidir:  
  
```  
lastprivate(variable-list)  
```  
  
 Belirtilen değişkenleri *değişken listesi* sahip `private` yan tümcesinde semantiği. Zaman bir `lastprivate` yan tümcesi görünür değeri, her bir iş paylaşım yapısı tanımlayan yönergesi üzerinde `lastprivate` ilişkili döngü ya da sözcüksel olarak son bölüm yönergesi sırayla son yinelemesi değişkeninden atanır değişkenin özgün nesne. Olmayan değişkenleri atanmış bir değer tarafından son yinelemesi **için** veya **için paralel**, veya sözcüksel olarak son Kısım **bölümleri** veya  **Paralel bölümleri** yönergesi, sonra yapısı belirsiz değerlere sahip. Atanmamış alt nesnelerinin da sonra yapı belirsiz bir değere sahip.  
  
 Kısıtlamaları `lastprivate` yan tümcesi aşağıdaki gibidir:  
  
-   İçin tüm kısıtlamaları `private` uygulayın.  
  
-   Olarak belirtilen bir sınıf türü sahip bir değişken `lastprivate` erişilebilir, anlaşılır kopya atama işleci olması gerekir.  
  
-   Paralel bir bölge içinde özel olan veya görünen değişkenleri `reduction` yan tümcesinde bir **paralel** yönergesi belirtilemez bir `lastprivate` paralel yapı bağlar iş paylaşım bir yönergesi yan tümcesi.