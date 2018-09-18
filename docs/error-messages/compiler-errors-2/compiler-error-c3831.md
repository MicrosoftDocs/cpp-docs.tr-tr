---
title: Derleyici Hatası C3831 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3831
dev_langs:
- C++
helpviewer_keywords:
- C3831
ms.assetid: a125d8dc-b75a-4ea0-b6c7-fe7b119dba25
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8525df7eb854ee56eef7bc9167d3630ea3c72ad5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46029890"
---
# <a name="compiler-error-c3831"></a>Derleyici Hatası C3831

'member': 'class' sabitlenmiş veri üyesi veya bir sabitleme işaretçisi döndüren bir üye işlevine sahip olamaz

[pin_ptr (C + +/ CLI)](../../windows/pin-ptr-cpp-cli.md) yanlış kullanıldı.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3831 oluşturur:

```
// C3831a.cpp
// compile with: /clr
ref class Y
{
public:
   int i;
};

ref class X
{
   pin_ptr<int> mbr_Y;   // C3831
   int^ mbr_Y2;   // OK
};

int main() {
   Y y;
   pin_ptr<int> p = &y.i;
}
```
