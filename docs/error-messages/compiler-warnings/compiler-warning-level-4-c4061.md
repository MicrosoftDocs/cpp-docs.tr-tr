---
title: Derleyici Uyarısı (düzey 4) C4061
ms.date: 11/30/2017
f1_keywords:
- C4061
helpviewer_keywords:
- C4061
ms.assetid: a99cf88e-7941-4519-8b1b-f6889d914b2f
ms.openlocfilehash: 8b730d561134b8b7ca4454ee74f99216fbc72cb4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50453280"
---
# <a name="compiler-warning-level-4-c4061"></a>Derleyici Uyarısı (düzey 4) C4061

> Numaralandırıcı '*tanımlayıcı*'numaralandırıcısının switch' ın*numaralandırma*' case etiketi tarafından açıkça işlenmiyor

İlişkili işleyici yok Numaralandırıcı sahip bir `switch` deyimi.

Varsayılan olarak bu uyarıyı kapalıdır. Bkz: [derleyici uyarıları emin olan kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4061 oluşturur; Servis talebi eksik Numaralandırıcının düzeltmek için ekleyin:

```cpp
// C4061.cpp
// compile with: /W4
#pragma warning(default : 4061)

enum E { a, b, c };
void func ( E e )
{
   switch(e)
   {
      case a:
      case b:
      default:
         break;
   }   // C4061 c' not handled
}

int main()
{
}
```