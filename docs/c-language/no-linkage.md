---
title: "Bağlantı yok | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- no linkage
- linkage [C++], none
ms.assetid: 5a413082-1034-4e04-b76b-8d14668bf434
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: abacc6fbd49f9f42620385a4206c9412648c173b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="no-linkage"></a>Bağlantı Yok
Bir blok içerisindeki tanımlayıcının bildirimi `extern` depolama sınıfı tanımlayıcısını içermiyorsa, tanımlayıcının bağlantısı yoktur ve tanımlayıcı işleve özgüdür.  
  
 Aşağıdaki tanımlayıcıların bağlantısı yoktur:  
  
-   Nesne veya işlev dışında bir şey olarak bildirilmiş tanımlayıcı  
  
-   Bir işlev parametresi olarak bildirilmiş bir tanımlayıcı  
  
-   `extern` depolama sınıfı tanımlayıcısı olmadan bildirilmiş bir nesneye yönelik blok kapsamı tanımlayıcısı  
  
 Tanımlayıcının hiçbir bağlantı yoksa, aynı kapsamda aynı adın yeniden bildirilmesi (bildirimcide veya tür tanımlayıcısında) simge yeniden tanımlama hatası oluşturur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlantıyı Belirtmek için extern Kullanma](../cpp/using-extern-to-specify-linkage.md)