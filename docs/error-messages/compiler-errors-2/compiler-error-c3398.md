---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3398'
title: Derleyici hatası C3398
ms.date: 11/04/2016
f1_keywords:
- C3398
helpviewer_keywords:
- C3398
ms.assetid: 26f8c8a4-526f-415b-8047-155c5cd4f180
ms.openlocfilehash: 024390ec03ad145f418f79d2db3228bd790a6de7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321947"
---
# <a name="compiler-error-c3398"></a>Derleyici hatası C3398

' operator ': ' function_signature ' değerinden ' function_pointer ' türüne dönüştürülemez. Kaynak ifadesi bir işlev simgesi olmalıdır

**/Clr** ile derlerken [__clrcall](../../cpp/clrcall.md) çağırma kuralı belirtilmediğinde, derleyici her bir işlev için iki giriş noktası (adres) oluşturur, yerel bir giriş noktası ve yönetilen giriş noktası.

Varsayılan olarak, derleyici yerel giriş noktasını döndürür, ancak yönetilen giriş noktasının istendiği bazı durumlar vardır (örneğin, adresi bir `__clrcall` işlev işaretçisine atarken). Derleyicinin bir atamadaki yönetilen giriş noktasını güvenilir bir şekilde seçmesi için sağ taraftaki bir işlev simgesi olması gerekir.
