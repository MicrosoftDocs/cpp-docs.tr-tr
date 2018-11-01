---
title: Derleyici Hatası C3744
ms.date: 11/04/2016
f1_keywords:
- C3744
helpviewer_keywords:
- C3744
ms.assetid: a447d050-80d1-406a-9a6e-f15c527d717c
ms.openlocfilehash: 407ed4b30b55b63aa9bf36de9f8675a531d70534
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50516239"
---
# <a name="compiler-error-c3744"></a>Derleyici Hatası C3744

en az 3 bağımsız değişken yönetilen olaylar için __unhook olmalıdır

[__Unhook](../../cpp/unhook.md) işlevi, C++ için Yönetilen Uzantılar için derlenmiş bir program kullanıldığında üç parametreleri alması gerekir.

`__hook` ve  `__unhook` /CLR programlama ile uyumlu değildir. Bunun yerine += ve-= işleçlerini kullanın.

C3744 eski derleyici seçeneği kullanılarak erişilebilir, yalnızca **/clr:oldSyntax**.
