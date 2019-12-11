---
title: Derleyici Uyarısı (düzey 4) C4001
ms.date: 11/04/2016
f1_keywords:
- C4001
helpviewer_keywords:
- C4001
ms.assetid: 414a47fe-d597-425e-9374-6a569231dc0a
ms.openlocfilehash: ceb7e65a292e5b9e9ef960ca9553183b703c93f0
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991690"
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
