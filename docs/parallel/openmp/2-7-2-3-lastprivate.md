---
title: 2.7.2.3 lastprivate | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 77f6a5c9-704f-4a88-8476-29db852ed800
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5caf9d870dce301c6055dcb55418b3dbbc3e741f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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