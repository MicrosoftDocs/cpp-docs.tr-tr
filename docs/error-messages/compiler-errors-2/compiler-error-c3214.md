---
title: Derleyici Hatası C3214 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3214
dev_langs:
- C++
helpviewer_keywords:
- C3214
ms.assetid: 49ee4a9a-2549-4adb-9d3a-38e154303c2e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a4ac7e1e5f07de87d19995e661520ed44fced955
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46135835"
---
# <a name="compiler-error-c3214"></a>Derleyici Hatası C3214

'type': 'generic_type' genel ' param' genel parametresi için geçersiz tür bağımsız değişkeni 'kısıtlaması' kısıtlamasını karşılamıyor

Türü bir genel sınıfın kısıtlamasını karşılamıyor genel bir sınıf örneğinin için belirtildi.

Aşağıdaki örnek, C3214 oluşturur:

```
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