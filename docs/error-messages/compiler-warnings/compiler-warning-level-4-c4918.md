---
title: Derleyici Uyarısı (düzey 4) C4918
ms.date: 11/04/2016
f1_keywords:
- C4918
helpviewer_keywords:
- C4918
ms.assetid: 1bcf6d35-3467-4aa8-b2ef-cb33f4e70238
ms.openlocfilehash: 801c22a45037492dc609d93c6339ab8feff30494
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988810"
---
# <a name="compiler-warning-level-4-c4918"></a>Derleyici Uyarısı (düzey 4) C4918

' character ': pragma optimizasyon listesinde geçersiz karakter

[En iyi duruma](../../preprocessor/optimize.md) getirme pragma ifadesinin iyileştirme listesinde bilinmeyen bir karakter bulundu.

Örneğin, aşağıdaki ifade C4918 oluşturur:

```cpp
// C4918.cpp
// compile with: /W4
#pragma optimize("X", on) // C4918 expected
int main()
{
}
```
