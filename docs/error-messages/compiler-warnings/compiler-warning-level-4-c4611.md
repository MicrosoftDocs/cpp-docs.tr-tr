---
title: Derleyici Uyarısı (düzey 4) C4611
ms.date: 11/04/2016
f1_keywords:
- C4611
helpviewer_keywords:
- C4611
ms.assetid: bd90d0a6-75f9-4e97-968d-dda6773e9fd8
ms.openlocfilehash: 2ce261b36344126d541a9b453c88f7f8289ecba0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214340"
---
# <a name="compiler-warning-level-4-c4611"></a>Derleyici Uyarısı (düzey 4) C4611

' function ' ve C++ nesne yok etme arasındaki etkileşim taşınabilir değildir

Bazı platformlarda, dahil edilen işlevler **`catch`** kapsam dışı bırakıldığında yok etme Işlevinin C++ nesne semantiğini desteklemiyor olabilir.

Beklenmeyen davranışları önlemek için, **`catch`** oluşturucular ve Yıkıcılar içeren işlevlerde kullanmaktan kaçının.

Bu uyarı yalnızca bir kez verilir; bkz. [pragma warning](../../preprocessor/warning.md).
