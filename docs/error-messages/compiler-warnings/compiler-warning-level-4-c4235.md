---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4235'
title: Derleyici Uyarısı (düzey 4) C4235
ms.date: 11/04/2016
f1_keywords:
- C4235
helpviewer_keywords:
- C4235
ms.assetid: d4214799-d62c-4674-b4e2-9e201c303303
ms.openlocfilehash: 011586efb311cab1da5cd4452bbbc03a942a5045
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334886"
---
# <a name="compiler-warning-level-4-c4235"></a>Derleyici Uyarısı (düzey 4) C4235

Standart olmayan uzantı kullanıldı: ' anahtar sözcük ' anahtar sözcüğü Bu mimaride desteklenmiyor

Derleyici, kullandığınız anahtar sözcüğü desteklemez.

Bu uyarı otomatik olarak bir hataya yükseltilir. Bu davranışı değiştirmek isterseniz [#pragma uyarı](../../preprocessor/warning.md)kullanın. Örneğin, C4235 düzey 2 uyarısı oluşturmak için aşağıdaki kod satırını kullanın

```cpp
#pragma warning(2:4235)
```

kaynak kodu dosyanızda.
