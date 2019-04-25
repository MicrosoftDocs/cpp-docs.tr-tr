---
title: Derleyici Hatası C2687
ms.date: 11/04/2016
f1_keywords:
- C2687
helpviewer_keywords:
- C2687
ms.assetid: 1d24b24a-cd0f-41cc-975c-b08dcfb7f402
ms.openlocfilehash: a30efa264a4e7be387c3c2363940bd5ceca1bcc4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62266198"
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