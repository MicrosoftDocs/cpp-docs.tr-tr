---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2785'
title: Derleyici hatası C2785
ms.date: 11/04/2016
f1_keywords:
- C2785
helpviewer_keywords:
- C2785
ms.assetid: d8d13360-0d00-4815-8475-b49c7f0dc0f3
ms.openlocfilehash: f40b652e30b30f0ef17426b547337352181383e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297908"
---
# <a name="compiler-error-c2785"></a>Derleyici hatası C2785

' declaration1 ' ve ' declaration2 ' farklı dönüş türlerine sahip

İşlev şablonu özelleşmenin dönüş türü, birincil işlev şablonunun dönüş türünden farklıdır.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Tutarlılık için işlev şablonunun tüm özelleştirmelerini denetleyin.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2785 oluşturur:

```cpp
// C2785.cpp
// compile with: /c
template<class T> void f(T);

template<> int f(int); // C2785
template<> void f(int); // OK
```
