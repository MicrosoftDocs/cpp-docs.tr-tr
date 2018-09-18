---
title: Derleyici Hatası C3452 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3452
dev_langs:
- C++
helpviewer_keywords:
- C3452
ms.assetid: e5293dcf-cb70-4133-ae2a-0bb496950ba0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 392bddb57b90892bc867bcd201a99fdfc1e3f226
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118108"
---
# <a name="compiler-error-c3452"></a>Derleyici Hatası C3452

Liste bağımsız değişken üyesi sabit değil

Bir sabit, derleme zamanında değerlendirilebilen bir değer beklenen bir öznitelik için bağımsız değişken geçirildi.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3452 oluşturur.

```
// C3452.cpp
// compile with: /c
int i;
[module( name="mod", type=dll, custom={i} ) ];   // C3452
// try the following line instead
// [module( name="mod", type=dll, custom={"a"} ) ];
```