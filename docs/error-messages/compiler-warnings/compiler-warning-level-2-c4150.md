---
title: Derleyici Uyarısı (düzey 2) C4150
ms.date: 11/04/2016
f1_keywords:
- C4150
helpviewer_keywords:
- C4150
ms.assetid: ff1760ec-0d9f-4d45-b797-94261624becf
ms.openlocfilehash: a3993d2b993205c98de968ca893f24f703b3b635
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218149"
---
# <a name="compiler-warning-level-2-c4150"></a>Derleyici Uyarısı (düzey 2) C4150

eksik ' Type ' türüne yönelik işaretçinin silinmesi; yok edici çağrılmadı

**`delete`** İşleci, tanımlanmış ancak tanımlanmamış bir türü silmek için çağrılır, bu nedenle derleyici bir yıkıcı bulamaz.

Aşağıdaki örnek C4150 oluşturur:

```cpp
// C4150.cpp
// compile with: /W2
class  IncClass;

void NoDestruct( IncClass* pIncClass )
{
   delete pIncClass;
} // C4150, define class to resolve

int main()
{
}
```
