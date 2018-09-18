---
title: Derleyici Hatası C3174 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3174
dev_langs:
- C++
helpviewer_keywords:
- C3174
ms.assetid: fe6b3b5a-8196-485f-a45f-0b2e51df4086
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1ca73c1fa16f2cc8b25f355705c7f0a72916158d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46105195"
---
# <a name="compiler-error-c3174"></a>Derleyici Hatası C3174

Modül özniteliği belirtilmedi

Visual C++ öznitelikleri kullanan bir program değil de kullanmadı [Modülü](../../windows/module-cpp.md) öznitelikleri kullanan herhangi bir programda gereken öznitelik.

Aşağıdaki örnek, C3174 oluşturur:

```
// C3174.cpp
// C3174 expected
// uncomment the following line to resolve this C3174
// [module(name="x")];
[export]
struct S
{
   int i;
};

int main()
{
}
```