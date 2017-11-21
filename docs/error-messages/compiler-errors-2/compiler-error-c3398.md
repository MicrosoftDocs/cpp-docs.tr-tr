---
title: "Derleyici Hatası C3398 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3398
dev_langs: C++
helpviewer_keywords: C3398
ms.assetid: 26f8c8a4-526f-415b-8047-155c5cd4f180
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 54241a6e57bdfd8795d6f894a1410c1e6c90cf49
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3398"></a>Derleyici Hatası C3398
'işleci': 'function_signature' 'function_pointer' dönüştürülemiyor. İşlev simgesi kaynağı deyim olmalıdır  
  
 Zaman [__clrcall](../../cpp/clrcall.md) çağırma kuralı belirtilmedi ile derleme yapılırken **/CLR**, iki giriş noktaları (adresleri) her işlev, yerel giriş noktası ve yönetilen bir giriş noktası için derleyici oluşturur.  
  
 Varsayılan olarak, yerel giriş noktası derleyici verir, ancak yönetilen giriş noktası istenen olduğu bazı durumlar vardır (örneğin adresine atarken bir `__clrcall` işlev işaretçisi). Derleyicinin güvenilir bir atamasında yönetilen giriş noktasını seçmek sağ taraftaki işlev simgesi olmalı.