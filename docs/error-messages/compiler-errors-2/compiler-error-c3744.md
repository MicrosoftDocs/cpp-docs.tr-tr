---
title: Derleyici hatası C3744
ms.date: 11/04/2016
f1_keywords:
- C3744
helpviewer_keywords:
- C3744
ms.assetid: a447d050-80d1-406a-9a6e-f15c527d717c
ms.openlocfilehash: 8db81afc348434e9ea2f57c991962fb15dc6bf98
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220164"
---
# <a name="compiler-error-c3744"></a>Derleyici hatası C3744

__unhook yönetilen olaylar için en az 3 bağımsız değişkene sahip olmalıdır

[`__unhook`](../../cpp/unhook.md)İşlev, C++ için yönetilen uzantılar için derlenmiş bir programda kullanıldığında üç parametre almalıdır.

**`__hook`** ve **`__unhook`** programlamayla uyumlu değildir **`/clr`** . Bunun yerine + = ve-= işleçlerini kullanın.

C3744 yalnızca kullanılmayan derleyici seçeneği kullanılarak erişilebilir **`/clr:oldSyntax`** .
