---
description: Derleyici Uyarısı hakkında daha fazla bilgi edinin (düzey 1) C4027
title: Derleyici Uyarısı (düzey 1) C4027
ms.date: 12/16/2020
f1_keywords:
- C4027
helpviewer_keywords:
- C4027
ms.openlocfilehash: 1489ca32211854bcf1ef55d1a4ac806ab1611f43
ms.sourcegitcommit: 387ce22a3b0137f99cbb856a772b5a910c9eba99
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/17/2020
ms.locfileid: "97645182"
---
# <a name="compiler-warning-level-1-c4027"></a>Derleyici Uyarısı (düzey 1) C4027

> işlev biçimsel parametre listesi olmadan bildiriliyor

İşlev bildiriminde hiç biçimsel parametre yoktu, ancak işlev tanımında veya bir çağrıda gerçek parametrelerde biçimsel parametreler var.

Derleyici bir parametre listesi olmadan işlev adının eski C stili ileri bildirimini kabul eder, ancak bunu uyarır. Daha sonra bu işleve yapılan çağrılar için, derleyici işlevin işlev tanımında veya çağrısında bulunan türlerin gerçek parametrelerini aldığını varsayar. İşlev bildiridefinizin işlev tanımının imzasıyla eşleşecek şekilde değiştirmenizi öneririz.
