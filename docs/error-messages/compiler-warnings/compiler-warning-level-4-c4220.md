---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4220'
title: Derleyici Uyarısı (düzey 4) C4220
ms.date: 11/04/2016
f1_keywords:
- C4220
helpviewer_keywords:
- C4220
ms.assetid: aba18868-825f-4763-9af6-3296406a80e4
ms.openlocfilehash: fd5378fd1e685b2cc6e730c2cff87fcdb041aaa8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330630"
---
# <a name="compiler-warning-level-4-c4220"></a>Derleyici Uyarısı (düzey 4) C4220

VarArgs kalan parametrelerle eşleşiyor

Varsayılan Microsoft uzantıları (/Ze) altında bir işlev işaretçisi, benzer, ancak değişken, bağımsız değişkenlerle bir işlevle eşleşen bir işaretçiye eşleşir.

## <a name="example"></a>Örnek

```c
// C4220.c
// compile with: /W4

int ( *pFunc1) ( int a, ... );
int ( *pFunc2) ( int a, int b);

int main()
{
   if ( pFunc1 != pFunc2 ) {};  // C4220
}
```

Bu tür işaretçiler ANSI uyumluluğu ([/za](../../build/reference/za-ze-disable-language-extensions.md)) altında eşleşmez.
