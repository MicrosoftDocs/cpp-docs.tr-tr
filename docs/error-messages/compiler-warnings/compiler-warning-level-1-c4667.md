---
title: Derleyici Uyarısı (düzey 1) C4667
ms.date: 11/04/2016
f1_keywords:
- C4667
helpviewer_keywords:
- C4667
ms.assetid: 5d2b7fe0-4f0e-4cd6-b432-ca02c3d194ab
ms.openlocfilehash: 9ae0d5cdcc1f6cca25f55cd1d7c03cc345c39e5e
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051403"
---
# <a name="compiler-warning-level-1-c4667"></a>Derleyici Uyarısı (düzey 1) C4667

' function ': zorunlu örnek oluşturma ile eşleşen hiçbir işlev şablonu tanımlanmadı

Bildirilmemiş bir işlev şablonunu örnekleyemezsiniz.

Aşağıdaki örnek C4667 neden olacaktır:

```cpp
// C4667a.cpp
// compile with: /LD /W1
template
void max(const int &, const int &); // C4667 expected
```

Bu uyarıyı önlemek için önce işlev şablonunu bildirin:

```cpp
// C4667b.cpp
// compile with: /LD
// Declare the function template
template<typename T>
const T &max(const T &a, const T &b) {
   return (a > b) ? a : b;
}
// Then forcibly instantiate it with a desired type ... i.e. 'int'
//
template
const int &max(const int &, const int &);
```