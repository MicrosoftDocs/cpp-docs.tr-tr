---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4061'
title: Derleyici Uyarısı (düzey 4) C4061
ms.date: 04/05/2019
f1_keywords:
- C4061
helpviewer_keywords:
- C4061
ms.assetid: a99cf88e-7941-4519-8b1b-f6889d914b2f
ms.openlocfilehash: 9e76fd864e57e6d84ed28b1646e8950186945d11
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262067"
---
# <a name="compiler-warning-level-4-c4061"></a>Derleyici Uyarısı (düzey 4) C4061

> '*Enumeration*' numaralandırmasının anahtarındaki '*Identifier*' numaralandırıcısı bir Case etiketi tarafından açıkça işlenmiyor

Belirtilen Numaralandırıcı *tanımlayıcısının* , **`switch`** **`default`** büyük/küçük harf içeren bir bildirimde ilişkili işleyicisi yok. Eksik durum, bir gözetim olabilir veya bir sorun olmayabilir. Bu, Numaralandırıcının varsayılan durum tarafından işlenip işlenmediğini bağlı olabilir. Durum içermeyen ifadelerde kullanılmayan numaralandırıcılara ilişkin ilgili bir uyarı için **`switch`** **`default`** bkz. [C4062](compiler-warning-level-4-c4062.md).

Bu uyarı varsayılan olarak kapalıdır. Varsayılan olarak kapalı olan uyarıların nasıl etkinleştirileceği hakkında daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C4061 oluşturur; düzeltilmesi için eksik Numaralandırıcı için bir durum ekleyin:

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

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Uyarısı (düzey 4) C4062](compiler-warning-level-4-c4062.md)
