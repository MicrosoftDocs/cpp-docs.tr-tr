---
title: Derleyici Uyarısı (düzey 4) C4001
ms.date: 11/04/2016
f1_keywords:
- C4001
helpviewer_keywords:
- C4001
ms.assetid: 414a47fe-d597-425e-9374-6a569231dc0a
ms.openlocfilehash: fc4ae55c5d25719e930a7435e0f9bf3ee2071a21
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541635"
---
# <a name="compiler-warning-level-4-c4001"></a>Derleyici Uyarısı (düzey 4) C4001

Standart olmayan ' tek satırlık açıklama ' uzantısı kullanıldı

> [!NOTE]
> Bu uyarı, Visual Studio 2017 sürüm 15,5 ' de kaldırılarak kaldırılır çünkü tek satırlık açıklamalar C99 içinde standarttır.

Tek satır açıklamaları, C99 ile başlayan C++ C 'de standart ve standart bir standarttır.
Katı ANSI uyumluluğu ([/za](../../build/reference/za-ze-disable-language-extensions.md)) altında, tek satırlık açıklamalar Içeren C dosyaları, standart olmayan bir uzantının kullanımı nedeniyle C4001 oluşturur. Tek satır açıklamaları içinde C++standart olduğundan, tek satırlık açıklamalar içeren C dosyaları Microsoft uzantıları Ile derlerken C4001 oluşturmaz (/Ze).

## <a name="example"></a>Örnek

Uyarıyı devre dışı bırakmak için [#pragma uyarının açıklamasını kaldırın (devre dışı bırak: 4001)](../../preprocessor/warning.md).

```cpp
// C4001.cpp
// compile with: /W4 /Za /TC
// #pragma warning(disable:4001)
int main()
{
   // single-line comment in main
   // C4001
}
```