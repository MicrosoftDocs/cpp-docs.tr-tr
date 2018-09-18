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
ms.openlocfilehash: 336494ea9581289efd9a41e604a28984125ae61a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46018138"
---
# <a name="compiler-error-c3398"></a>Derleyici Hatası C3398

'operator': 'function_pointer' için 'function_signature' dönüştürülemiyor. Kaynak ifadesi bir işlev simgesi olmalıdır

Zaman [__clrcall](../../cpp/clrcall.md) çağırma kuralı belirtilmediği ile derleme yaparken **/CLR**, derleyici her işlev, yerel giriş noktası ve yönetilen bir giriş noktası için iki giriş noktaları (adresleri) oluşturur.

Varsayılan olarak, derleyici yerel giriş noktası döndürür, ancak yönetilen giriş noktasını istenen olduğu bazı durumlar vardır (örneğin adresine atarken bir `__clrcall` işlev işaretçisi). Güvenilir bir şekilde atama içinde yönetilen giriş noktasını seçmek derleyici için sırada sağ tarafı bir işlev simgesi olmalıdır.