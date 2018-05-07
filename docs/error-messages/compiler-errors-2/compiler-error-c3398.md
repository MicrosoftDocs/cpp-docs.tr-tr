---
title: Derleyici Hatası C3398 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3398
dev_langs:
- C++
helpviewer_keywords:
- C3398
ms.assetid: 26f8c8a4-526f-415b-8047-155c5cd4f180
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b870479977bfb49ff39d5a15fe19fc700ed66b8e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3398"></a>Derleyici Hatası C3398
'işleci': 'function_signature' 'function_pointer' dönüştürülemiyor. İşlev simgesi kaynağı deyim olmalıdır  
  
 Zaman [__clrcall](../../cpp/clrcall.md) çağırma kuralı belirtilmedi ile derleme yapılırken **/CLR**, iki giriş noktaları (adresleri) her işlev, yerel giriş noktası ve yönetilen bir giriş noktası için derleyici oluşturur.  
  
 Varsayılan olarak, yerel giriş noktası derleyici verir, ancak yönetilen giriş noktası istenen olduğu bazı durumlar vardır (örneğin adresine atarken bir `__clrcall` işlev işaretçisi). Derleyicinin güvenilir bir atamasında yönetilen giriş noktasını seçmek sağ taraftaki işlev simgesi olmalı.