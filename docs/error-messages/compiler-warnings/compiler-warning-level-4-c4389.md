---
title: Derleyici Uyarısı (düzey 4) C4389
description: Microsoft C/C++ derleyicisi uyarı C4389, nedenleri ve çözümlemesi.
ms.date: 10/16/2020
f1_keywords:
- c4389
helpviewer_keywords:
- C4389
ms.openlocfilehash: b06b013151ed12b4f66bb23a7e862992d05e6b30
ms.sourcegitcommit: f19f02f217b80804ab321d463c76ce6f681abcc6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/19/2020
ms.locfileid: "92176264"
---
# <a name="compiler-warning-level-4-c4389"></a>Derleyici Uyarısı (düzey 4) C4389

> '*eşitlik-işleç*': imzalı/imzasız uyuşmazlığı

**`==`** Veya **`!=`** ile ilgili bir işlem **`signed`** ve **`unsigned`** değişkenler. Bu, veri kaybına neden olabilir.

## <a name="remarks"></a>Açıklamalar

Bu uyarıyı gidermenin bir yolu, ve türlerini karşılaştırdığınızda iki türden birini saçmanız durumunda olur **`signed`** **`unsigned`** .

## <a name="example"></a>Örnek

Aşağıdaki örnek C4389 oluşturur:

```cpp
// C4389.cpp
// compile with: cl /EHsc /W4 C4389.cpp

int main()
{
   int a = 9;
   unsigned int b = 10;
   int result = 0;

   if (a == b)   // C4389
      result = 1;
   else
      result = 2;

   if (unsigned(a) == b) // OK
      result = 3;
   else
      result = 4;

   return result;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Uyarısı C4018](compiler-warning-level-3-c4018.md)\
[Derleyici Uyarısı (düzey 4) C4388](c4388.md)
