---
title: Derleyici hatası C3398
ms.date: 11/04/2016
f1_keywords:
- C3398
helpviewer_keywords:
- C3398
ms.assetid: 26f8c8a4-526f-415b-8047-155c5cd4f180
ms.openlocfilehash: f76515d58f020b414e6b79a7737463af80bd2d07
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80200830"
---
# <a name="compiler-error-c3398"></a>Derleyici hatası C3398

' operator ': ' function_signature ' değerinden ' function_pointer ' türüne dönüştürülemez. Kaynak ifadesi bir işlev simgesi olmalıdır

**/Clr**ile derlerken [__clrcall](../../cpp/clrcall.md) çağırma kuralı belirtilmediğinde, derleyici her bir işlev için iki giriş noktası (adres) oluşturur, yerel bir giriş noktası ve yönetilen giriş noktası.

Varsayılan olarak, derleyici yerel giriş noktasını döndürür, ancak yönetilen giriş noktasının istendiği bazı durumlar vardır (örneğin, adresi bir `__clrcall` işlev işaretçisine atarken). Derleyicinin bir atamadaki yönetilen giriş noktasını güvenilir bir şekilde seçmesi için sağ taraftaki bir işlev simgesi olması gerekir.
