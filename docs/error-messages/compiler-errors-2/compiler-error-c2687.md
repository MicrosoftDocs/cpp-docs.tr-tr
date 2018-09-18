---
title: Derleyici Hatası C2687 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2687
dev_langs:
- C++
helpviewer_keywords:
- C2687
ms.assetid: 1d24b24a-cd0f-41cc-975c-b08dcfb7f402
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1333d26a7733ffeb0876a9b563377e5ead010261
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46042682"
---
# <a name="compiler-error-c2687"></a>Derleyici Hatası C2687

'type': özel durum bildirimi 'void' veya bir eksik tür veya işaretçi veya başvuru tamamlanmamış bir türü belirtmek

Bir özel durum bildirimi bir parçası olarak bir tür için tanımlanmış ve void olmayan olmalıdır.

Aşağıdaki örnek, C2687 oluşturur:

```
// C2687.cpp
class C;

int main() {
   try {}
   catch (C) {}   // C2687 error
}
```

Olası çözüm:

```
// C2687b.cpp
// compile with: /EHsc
class C {};

int main() {
   try {}
   catch (C) {}
}
```