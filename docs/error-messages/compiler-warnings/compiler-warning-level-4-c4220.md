---
title: Derleyici Uyarısı (düzey 4) C4220
ms.date: 11/04/2016
f1_keywords:
- C4220
helpviewer_keywords:
- C4220
ms.assetid: aba18868-825f-4763-9af6-3296406a80e4
ms.openlocfilehash: 90b66a9d819d3014c1e1437b691766ade420bd4b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161262"
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
