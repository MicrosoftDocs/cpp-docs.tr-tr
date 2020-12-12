---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4611'
title: Derleyici Uyarısı (düzey 4) C4611
ms.date: 11/04/2016
f1_keywords:
- C4611
helpviewer_keywords:
- C4611
ms.assetid: bd90d0a6-75f9-4e97-968d-dda6773e9fd8
ms.openlocfilehash: df53392b2d56b9afb1ab0cbcb2fc7b6267d5f00f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97168273"
---
# <a name="compiler-warning-level-4-c4611"></a>Derleyici Uyarısı (düzey 4) C4611

' function ' ve C++ nesne yok etme arasındaki etkileşim taşınabilir değildir

Bazı platformlarda, dahil edilen işlevler **`catch`** kapsam dışı bırakıldığında yok etme Işlevinin C++ nesne semantiğini desteklemiyor olabilir.

Beklenmeyen davranışları önlemek için, **`catch`** oluşturucular ve Yıkıcılar içeren işlevlerde kullanmaktan kaçının.

Bu uyarı yalnızca bir kez verilir; bkz. [pragma warning](../../preprocessor/warning.md).
