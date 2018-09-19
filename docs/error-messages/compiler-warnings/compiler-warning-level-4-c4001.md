---
title: Derleyici Uyarısı (düzey 4) C4001 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4001
dev_langs:
- C++
helpviewer_keywords:
- C4001
ms.assetid: 414a47fe-d597-425e-9374-6a569231dc0a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c325656b9e61ee324a3b9f171413f1020440f9ab
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46025418"
---
# <a name="compiler-warning-level-4-c4001"></a>Derleyici Uyarısı (düzey 4) C4001

Standart olmayan uzantı 'tek satır Açıklama' kullanıldı

> [!NOTE]
> Tek satırlı yorumlar C99 standart olduğundan bu uyarı, Visual Studio 2017 sürüm 15.5 kaldırılır.

Tek satırlı yorumlar, standart c++ ve C ile C99 başlatırken standart.
Katı ANSI Uyumluluğu altında ([/Za](../../build/reference/za-ze-disable-language-extensions.md)), tek satırlı açıklama içeren C dosyaları, standart olmayan uzantı kullanımı nedeniyle C4001 oluşturun. Tek satırlı yorumlar C++ standardı olduğundan, tek satırlık açıklamaları içeren C dosyaları C4001 Microsoft Uzatmaları (/Ze) ile derleme yaparken üretmez.

## <a name="example"></a>Örnek

Uyarı devre dışı bırakmak için açıklama durumundan çıkarın [#pragma warning(disable:4001)](../../preprocessor/warning.md).

```
// C4001.cpp
// compile with: /W4 /Za /TC
// #pragma warning(disable:4001)
int main()
{
   // single-line comment in main
   // C4001
}
```