---
title: Derleyici Uyarısı (düzey 4) C4611
ms.date: 11/04/2016
f1_keywords:
- C4611
helpviewer_keywords:
- C4611
ms.assetid: bd90d0a6-75f9-4e97-968d-dda6773e9fd8
ms.openlocfilehash: b799c568d73a081a4d4cf5616f376f3efc9eeffb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50542317"
---
# <a name="compiler-warning-level-4-c4611"></a>Derleyici Uyarısı (düzey 4) C4611

'function' ile C++ nesne yok etme arasındaki etkileşim taşınabilir değildir.

Bazı platformlarda, içeren işlevler **catch** C++ nesnesi semantiğini yok etme zaman kapsam dışına desteklemiyor olabilir.

Beklenmeyen davranışları önlemek için kullanmaktan kaçının **catch** oluşturucular ve Yıkıcılar işlevlerde.

Bu uyarı yalnızca bir kez verilir; bkz: [pragma Uyarısı](../../preprocessor/warning.md).