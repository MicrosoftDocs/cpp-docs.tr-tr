---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4233'
title: Derleyici Uyarısı (düzey 4) C4233
ms.date: 10/25/2017
f1_keywords:
- C4233
helpviewer_keywords:
- C4233
ms.assetid: 9aa51fc6-8ef3-43b5-bafb-c9333cf60de3
ms.openlocfilehash: 3e797bcefeaeee615014ea8e0bd109e4cf4ffbef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344022"
---
# <a name="compiler-warning-level-4-c4233"></a>Derleyici Uyarısı (düzey 4) C4233

> Standart olmayan uzantı kullanıldı: '*anahtar sözcük*' anahtar sözcüğü yalnızca C++ sürümünde desteklenir, C değil

Derleyici, kaynak kodunuzu C++ yerine C olarak derlemiştir ve yalnızca C++ içinde geçerli olan bir anahtar sözcük kullandınız. Kaynak dosyanın uzantısı. c ise veya [/TC](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)kullanıyorsanız, derleyici kaynak dosyanızı C olarak derler.

Bu uyarı otomatik olarak bir hataya yükseltilir. Bu davranışı değiştirmek isterseniz [#pragma uyarı](../../preprocessor/warning.md)kullanın. Örneğin, C4233 4. düzey bir uyarı sorununa dönüştürmek için, bu satırı kaynak kodu dosyanıza ekleyin:

```cpp
#pragma warning(4:4233)
```
