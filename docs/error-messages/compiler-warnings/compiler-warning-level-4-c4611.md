---
title: Derleyici Uyarısı (düzey 4) C4611
ms.date: 11/04/2016
f1_keywords:
- C4611
helpviewer_keywords:
- C4611
ms.assetid: bd90d0a6-75f9-4e97-968d-dda6773e9fd8
ms.openlocfilehash: 7de4cdf0eacb1b9848a4350f1d223da1fd47d1fc
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198308"
---
# <a name="compiler-warning-level-4-c4611"></a>Derleyici Uyarısı (düzey 4) C4611

' function ' ve C++ nesne yok etme arasındaki etkileşim taşınabilir değildir

Bazı platformlarda, **catch** içeren işlevler, kapsam dışında yok etme C++ nesnesinin nesne semantiğini desteklemiyor olabilir.

Beklenmeyen davranışları önlemek için, oluşturucular ve Yıkıcılar içeren işlevlerde **catch** kullanmaktan kaçının.

Bu uyarı yalnızca bir kez verilir; bkz. [pragma warning](../../preprocessor/warning.md).
