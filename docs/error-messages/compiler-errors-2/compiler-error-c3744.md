---
title: Derleyici Hatası C3744 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3744
dev_langs:
- C++
helpviewer_keywords:
- C3744
ms.assetid: a447d050-80d1-406a-9a6e-f15c527d717c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d644a621fc6d8e460e1b97e5baec360de8662365
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46063729"
---
# <a name="compiler-error-c3744"></a>Derleyici Hatası C3744

en az 3 bağımsız değişken yönetilen olaylar için __unhook olmalıdır

[__Unhook](../../cpp/unhook.md) işlevi, C++ için Yönetilen Uzantılar için derlenmiş bir program kullanıldığında üç parametreleri alması gerekir.

`__hook` ve  `__unhook` /CLR programlama ile uyumlu değildir. Bunun yerine += ve-= işleçlerini kullanın.

C3744 eski derleyici seçeneği kullanılarak erişilebilir, yalnızca **/clr:oldSyntax**.
