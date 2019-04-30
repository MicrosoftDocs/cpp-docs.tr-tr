---
title: Derleyici Hatası C3851
ms.date: 09/05/2018
f1_keywords:
- C3851
helpviewer_keywords:
- C3851
ms.assetid: da30c21c-33aa-4439-8fb3-2f5021ea4985
ms.openlocfilehash: 52c4f3a393ffaf2b61a65c8e2e0dcc8efac08288
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62380948"
---
# <a name="compiler-error-c3851"></a>Derleyici Hatası C3851

> '*char*': bir evrensel karakter adı temel karakter kümesindeki bir karakteri belirtemez

## <a name="remarks"></a>Açıklamalar

C++ derlenmiş kod içinde bir karakter, temel kaynak karakter kümesi dışında bir dize veya karakter sabiti temsil eden bir evrensel karakter adı kullanamazsınız. Daha fazla bilgi için [karakter kümesi](../../cpp/character-sets.md). C derlenmiş kodda, bir evrensel karakter adı karakterleri aralığında 0x20 0x7f, kapsamlı 0x24 ('$')'hariç 0x40 kullanamazsınız ('\@'), veya 0x60 ('\`').

## <a name="example"></a>Örnek

Aşağıdaki örnekleri C3851 oluşturmak ve bu sorunun nasıl göster:

```cpp
// C3851.cpp
int main()
{
   int test1_\u0041 = 0;   // C3851, \u0041 = 'A' in basic character set
   int test2_A = 0;        // OK
}
```