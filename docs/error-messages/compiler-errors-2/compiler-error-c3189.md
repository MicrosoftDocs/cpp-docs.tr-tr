---
title: Derleyici Hatası C3189
ms.date: 11/04/2016
f1_keywords:
- C3189
helpviewer_keywords:
- C3189
ms.assetid: b254de79-931e-4a59-a9f4-1c690d90ca5e
ms.openlocfilehash: b2de290178657ae427b5ad7999c511ae7ff9f1eb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62300652"
---
# <a name="compiler-error-c3189"></a>Derleyici Hatası C3189

' typeid\<soyut bildirimci yazın >': Bu sözdizimi artık desteklenmiyor, kullanın:: typeid yerine

Eski bir biçimi [TypeID](../../extensions/typeid-cpp-component-extensions.md) olan kullanıldığında, yeni formu kullanın.

Aşağıdaki örnek, C3189 oluşturur:

```
// C3189.cpp
// compile with: /clr
int main() {
   System::Type^ t  = typeid<System::Object>;   // C3189
   System::Type^ t2  = System::Object::typeid;   // OK
}
```