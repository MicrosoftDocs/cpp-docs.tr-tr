---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3744'
title: Derleyici hatası C3744
ms.date: 11/04/2016
f1_keywords:
- C3744
helpviewer_keywords:
- C3744
ms.assetid: a447d050-80d1-406a-9a6e-f15c527d717c
ms.openlocfilehash: 6d8e9184db37f65fd73a85aaaa6c350303802216
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340235"
---
# <a name="compiler-error-c3744"></a>Derleyici hatası C3744

__unhook yönetilen olaylar için en az 3 bağımsız değişkene sahip olmalıdır

[`__unhook`](../../cpp/unhook.md)İşlev, C++ için yönetilen uzantılar için derlenmiş bir programda kullanıldığında üç parametre almalıdır.

**`__hook`** ve **`__unhook`** programlamayla uyumlu değildir **`/clr`** . Bunun yerine + = ve-= işleçlerini kullanın.

C3744 yalnızca kullanılmayan derleyici seçeneği kullanılarak erişilebilir **`/clr:oldSyntax`** .
