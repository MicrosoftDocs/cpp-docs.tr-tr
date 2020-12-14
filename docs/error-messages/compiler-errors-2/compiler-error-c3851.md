---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3851'
title: Derleyici hatası C3851
ms.date: 09/05/2018
f1_keywords:
- C3851
helpviewer_keywords:
- C3851
ms.assetid: da30c21c-33aa-4439-8fb3-2f5021ea4985
ms.openlocfilehash: 62f35b8828f7c8f1af9769152a88b7240ff9ff93
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255372"
---
# <a name="compiler-error-c3851"></a>Derleyici hatası C3851

> '*char*': bir evrensel karakter adı temel karakter kümesindeki bir karakteri belirleyemez

## <a name="remarks"></a>Açıklamalar

C++ olarak derlenen kodda, bir dize veya karakter sabiti dışında temel kaynak karakter kümesindeki bir karakteri temsil eden bir evrensel karakter adı kullanamazsınız. Daha fazla bilgi için bkz. [karakter kümeleri](../../cpp/character-sets.md). C olarak derlenen kodda, 0x20-0x7F aralığında, 0x24 (' $ '), 0x40 (' \@ ') veya 0x60 (' ') dışındaki karakterler için evrensel karakter adı kullanamazsınız \` .

## <a name="example"></a>Örnek

Aşağıdaki örnekler C3851 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C3851.cpp
int main()
{
   int test1_\u0041 = 0;   // C3851, \u0041 = 'A' in basic character set
   int test2_A = 0;        // OK
}
```
