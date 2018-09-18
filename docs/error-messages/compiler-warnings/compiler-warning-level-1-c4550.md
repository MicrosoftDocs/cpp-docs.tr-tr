---
title: Derleyici Uyarısı (düzey 1) C4550 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4550
dev_langs:
- C++
helpviewer_keywords:
- C4550
ms.assetid: f902b4ed-5f17-48ea-b693-92f4fb8c8054
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 926a2bcca82fb76e4fb13450531a9ceb0089c979
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46052985"
---
# <a name="compiler-warning-level-1-c4550"></a>Derleyici Uyarısı (düzey 1) C4550

ifade bir bağımsız değişken listesi eksik bir işlev olarak değerleniyor

Başvurusu kaldırılmış bir işaretçi bir işlev için bağımsız değişken listesi eksik.

## <a name="example"></a>Örnek

```
// C4550.cpp
// compile with: /W1
bool f()
{
   return true;
}

typedef bool (*pf_t)();

int main()
{
   pf_t pf = f;
   if (*pf) {}  // C4550
   return 0;
}
```