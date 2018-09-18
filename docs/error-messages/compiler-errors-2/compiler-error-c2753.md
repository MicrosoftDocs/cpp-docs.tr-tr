---
title: Derleyici Hatası C2753 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2753
dev_langs:
- C++
helpviewer_keywords:
- C2753
ms.assetid: 92bfeeac-524a-4a8e-9a4f-fb8269055826
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 722176744dc614e54d7b25ffd75be679ef9e63dc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46060596"
---
# <a name="compiler-error-c2753"></a>Derleyici Hatası C2753

'*şablon*': Kısmi özelleştirme birincil şablonun bağımsız değişken listesi eşleşemez

Derleyici şablon bağımsız değişken listesi parametre listesi eşleşirse, aynı şablon olarak değerlendirir. İki kez aynı şablon tanımlama izin verilmez.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2753 oluşturur ve bunu düzeltmek için bir yol gösterir:

```cpp
// C2753.cpp
// compile with: cl /c C2753.cpp
template<class T>
struct A {};

template<class T>
struct A<T> {};   // C2753
// try the following line instead
// struct A<int> {};

template<class T, class U, class V, class W, class X>
struct B {};
```