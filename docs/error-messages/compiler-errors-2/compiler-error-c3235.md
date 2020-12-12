---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3235'
title: Derleyici hatası C3235
ms.date: 11/04/2016
f1_keywords:
- C3235
helpviewer_keywords:
- C3235
ms.assetid: 0554d6c7-e1dc-4c99-8934-cbcf491c8203
ms.openlocfilehash: 5e478e9104599f833d3f63abb042660816425028
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311909"
---
# <a name="compiler-error-c3235"></a>Derleyici hatası C3235

' özelleşme ': bir genel sınıfın açık veya kısmi özelleştirmesine izin verilmiyor

Genel sınıflar açık veya kısmi uzmanlık için kullanılamaz.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3235 oluşturur.

```cpp
// C3235.cpp
// compile with: /clr
generic<class T>
public ref class C {};

generic<>
public ref class C<int> {};   // C3235 Remove this specialization to resolve this error.
```
