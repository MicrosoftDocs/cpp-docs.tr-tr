---
title: Derleyici Hatası C2055 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2055
dev_langs:
- C++
helpviewer_keywords:
- C2055
ms.assetid: 6cec79cc-6bec-443f-9897-fbf5452718c7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d6c63d79325417fbd9b1f451fb4a51f13957b4df
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019348"
---
# <a name="compiler-error-c2055"></a>Derleyici Hatası C2055

tür listesi değil biçimsel parametre listesi bekleniyordu

Bir işlev tanımı bir biçimsel parametre listesi yerine bir parametre türü listesi içerir. ANSI C biçimsel parametreler void veya üç nokta olmadıkları sürece olarak adlandırılmasını gerektirir (`...`).

Aşağıdaki örnek, C2055 oluşturur:

```
// C2055.c
// compile with: /c
void func(int, char) {}  // C2055
void func (int i, char c) {}   // OK
```