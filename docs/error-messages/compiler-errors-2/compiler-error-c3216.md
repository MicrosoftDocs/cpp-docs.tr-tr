---
title: Derleyici Hatası C3216 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3216
dev_langs:
- C++
helpviewer_keywords:
- C3216
ms.assetid: bbab1efe-8779-4489-8bb0-b11e45f5cbe5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4eb1fb93335dc6fb61e8e73ea11cfc91c6b461b8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46043696"
---
# <a name="compiler-error-c3216"></a>Derleyici Hatası C3216

Genel bir parametre değil 'type' kısıtlaması olmalıdır

Kısıtlama ill oluşturulmuş.

Aşağıdaki örnek, C3216 oluşturur:

```
// C3216.cpp
// compile with: /clr
interface struct A {};

generic <class T>
where F : A   // C3216
// Try the following line instead:
// where T : A    // C3216
ref class C {};
```

Aşağıdaki örnek, olası çözümü göstermektedir:

```
// C3216b.cpp
// compile with: /clr /c
interface struct A {};

generic <class T>
where T : A
ref class C {};
```