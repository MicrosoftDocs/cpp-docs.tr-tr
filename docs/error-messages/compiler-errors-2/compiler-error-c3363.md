---
title: Derleyici Hatası C3363
ms.date: 11/04/2016
f1_keywords:
- C3363
helpviewer_keywords:
- C3363
ms.assetid: 41aa922f-608e-4f7a-ba66-451fc1161935
ms.openlocfilehash: eca598233dbe4cae4730e952b45945653ec8ffaa
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59775888"
---
# <a name="compiler-error-c3363"></a>Derleyici Hatası C3363

'type': 'typeid' yalnızca bir türe uygulanabilir

[TypeID](../../extensions/typeid-cpp-component-extensions.md) işleci yanlış kullanıldı.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3363 oluşturur.

```
// C3363.cpp
// compile with: /clr
int main() {
   System::typeid;   // C3363
}
```