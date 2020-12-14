---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4001'
title: Derleyici Uyarısı (düzey 4) C4001
ms.date: 11/04/2016
f1_keywords:
- C4001
helpviewer_keywords:
- C4001
ms.assetid: 414a47fe-d597-425e-9374-6a569231dc0a
ms.openlocfilehash: c28c1391b120983d72dc6e5b7a96faa937ee2598
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262223"
---
# <a name="compiler-warning-level-4-c4001"></a>Derleyici Uyarısı (düzey 4) C4001

Standart olmayan ' tek satırlık açıklama ' uzantısı kullanıldı

> [!NOTE]
> Bu uyarı, Visual Studio 2017 sürüm 15,5 ' de kaldırılarak kaldırılır çünkü tek satırlık açıklamalar C99 içinde standarttır.

Tek satır açıklamaları, C99 ile başlayan C 'de C++ ve Standard 'da standarttır.
Katı ANSI uyumluluğu ([/za](../../build/reference/za-ze-disable-language-extensions.md)) altında, tek satırlık açıklamalar Içeren C dosyaları, standart olmayan bir uzantının kullanımı nedeniyle C4001 oluşturur. Tek satır açıklamaları C++ ' ta standart olduğundan, tek satırlık açıklamalar içeren C dosyaları Microsoft uzantıları ile derlerken C4001 oluşturmaz (/Ze).

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
