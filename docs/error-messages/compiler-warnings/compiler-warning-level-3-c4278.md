---
title: Derleyici Uyarısı (Düzey 3) C4278
ms.date: 08/27/2018
f1_keywords:
- C4278
helpviewer_keywords:
- C4278
ms.assetid: 4b6053fb-df62-4c04-b6c8-c011759557b8
ms.openlocfilehash: 8c5c15105581602566116d3ed82b89a6337435c9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402170"
---
# <a name="compiler-warning-level-3-c4278"></a>Derleyici Uyarısı (Düzey 3) C4278

> '*tanımlayıcı*': tür kitaplığındaki tanımlayıcı '*tlb*' zaten bir makro; 'rename' niteleyicisini kullanın

Kullanırken [#import](../../preprocessor/hash-import-directive-cpp.md), içeri aktardığınız tür kitaplığı bir tanımlayıcıda bir tanımlayıcı bildirmek çalışıyor *tanımlayıcı*. Ancak, geçerli bir simge zaten budur.

Kullanım `#import` **Yeniden Adlandır** sembol tür kitaplığında bir diğer ad atamak için özniteliği.