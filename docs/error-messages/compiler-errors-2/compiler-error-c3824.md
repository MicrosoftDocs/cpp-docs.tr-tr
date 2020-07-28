---
title: Derleyici hatası C3824
ms.date: 11/04/2016
f1_keywords:
- C3824
helpviewer_keywords:
- C3824
ms.assetid: b6c6adf1-0a29-401c-a06e-616fd50d4c37
ms.openlocfilehash: 78081de44a834b16d34d1f88a5dc996efb1f784c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220151"
---
# <a name="compiler-error-c3824"></a>Derleyici hatası C3824

' üye ': Bu tür bu bağlamda (işlev parametresi, dönüş türü veya statik üye) yer alamaz

Sabitleme işaretçileri işlev parametreleri, dönüş türleri veya bildirilemez **`static`** .

## <a name="example"></a>Örnek

Aşağıdaki örnek C3824 oluşturur:

```cpp
// C3824a.cpp
// compile with: /clr /c
void func() {
   static pin_ptr<int> a; // C3824
   pin_ptr<int> b; // OK
}
```
