---
title: Derleyici Hatası C2687
ms.date: 11/04/2016
f1_keywords:
- C2687
helpviewer_keywords:
- C2687
ms.assetid: 1d24b24a-cd0f-41cc-975c-b08dcfb7f402
ms.openlocfilehash: a30efa264a4e7be387c3c2363940bd5ceca1bcc4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50540952"
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