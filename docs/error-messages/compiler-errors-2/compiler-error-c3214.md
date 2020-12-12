---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3214'
title: Derleyici hatası C3214
ms.date: 11/04/2016
f1_keywords:
- C3214
helpviewer_keywords:
- C3214
ms.assetid: 49ee4a9a-2549-4adb-9d3a-38e154303c2e
ms.openlocfilehash: 8f1b558b37e3a9f4daa08ecdd2f90b0f7a74a2a8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173824"
---
# <a name="compiler-error-c3214"></a>Derleyici hatası C3214

' Type ': genel ' generic_type ' öğesinin ' param ' genel parametresi için geçersiz tür bağımsız değişkeni, ' Constraint ' kısıtlamasını karşılamıyor

Tür, genel sınıfın kısıtlamasına uymayan bir genel sınıfın örneklemesi için belirtildi.

Aşağıdaki örnek C3214 oluşturur:

```cpp
// C3214.cpp
// compile with: /clr
interface struct A {};

generic <class T>
where T : A
ref class C {};

ref class X : public A {};

int main() {
   C<int>^ c = new C<int>;   // C3214
   C<X ^> ^ c2 = new C<X^>;   // OK
}
```
