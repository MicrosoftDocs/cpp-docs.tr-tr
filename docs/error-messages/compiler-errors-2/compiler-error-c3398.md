---
title: Derleyici Hatası C3398
ms.date: 11/04/2016
f1_keywords:
- C3398
helpviewer_keywords:
- C3398
ms.assetid: 26f8c8a4-526f-415b-8047-155c5cd4f180
ms.openlocfilehash: 3b688012009a87c1e3d0db05e47133893daeaf34
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50451070"
---
# <a name="compiler-error-c3398"></a>Derleyici Hatası C3398

'operator': 'function_pointer' için 'function_signature' dönüştürülemiyor. Kaynak ifadesi bir işlev simgesi olmalıdır

Zaman [__clrcall](../../cpp/clrcall.md) çağırma kuralı belirtilmediği ile derleme yaparken **/CLR**, derleyici her işlev, yerel giriş noktası ve yönetilen bir giriş noktası için iki giriş noktaları (adresleri) oluşturur.

Varsayılan olarak, derleyici yerel giriş noktası döndürür, ancak yönetilen giriş noktasını istenen olduğu bazı durumlar vardır (örneğin adresine atarken bir `__clrcall` işlev işaretçisi). Güvenilir bir şekilde atama içinde yönetilen giriş noktasını seçmek derleyici için sırada sağ tarafı bir işlev simgesi olmalıdır.