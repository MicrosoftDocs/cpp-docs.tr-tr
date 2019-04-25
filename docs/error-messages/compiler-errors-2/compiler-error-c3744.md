---
title: Derleyici Hatası C3744
ms.date: 11/04/2016
f1_keywords:
- C3744
helpviewer_keywords:
- C3744
ms.assetid: a447d050-80d1-406a-9a6e-f15c527d717c
ms.openlocfilehash: 407ed4b30b55b63aa9bf36de9f8675a531d70534
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62227117"
---
# <a name="compiler-error-c3744"></a>Derleyici Hatası C3744

en az 3 bağımsız değişken yönetilen olaylar için __unhook olmalıdır

[__Unhook](../../cpp/unhook.md) işlevi için Yönetilen Uzantılar için derlenmiş bir program kullanıldığında üç parametre gerçekleştirmeniz gereken C++.

`__hook` ve  `__unhook` /CLR programlama ile uyumlu değildir. Bunun yerine += ve-= işleçlerini kullanın.

C3744 eski derleyici seçeneği kullanılarak erişilebilir, yalnızca **/clr:oldSyntax**.
