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
ms.openlocfilehash: 278325c1ad1b31ce20b6a17034be5e4731f6da78
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="no-linkage"></a>Bağlantı Yok
Bir blok içerisindeki tanımlayıcının bildirimi `extern` depolama sınıfı tanımlayıcısını içermiyorsa, tanımlayıcının bağlantısı yoktur ve tanımlayıcı işleve özgüdür.  
  
 Aşağıdaki tanımlayıcıların bağlantısı yoktur:  
  
-   Nesne veya işlev dışında bir şey olarak bildirilmiş tanımlayıcı  
  
-   Bir işlev parametresi olarak bildirilmiş bir tanımlayıcı  
  
-   `extern` depolama sınıfı tanımlayıcısı olmadan bildirilmiş bir nesneye yönelik blok kapsamı tanımlayıcısı  
  
 Tanımlayıcının hiçbir bağlantı yoksa, aynı kapsamda aynı adın yeniden bildirilmesi (bildirimcide veya tür tanımlayıcısında) simge yeniden tanımlama hatası oluşturur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlantıyı belirtmek için extern kullanma](../cpp/using-extern-to-specify-linkage.md)