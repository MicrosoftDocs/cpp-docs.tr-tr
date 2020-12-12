---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2393'
title: Derleyici hatası C2393
ms.date: 11/04/2016
f1_keywords:
- C2393
helpviewer_keywords:
- C2393
ms.assetid: 4bd95728-e813-4ce8-844a-c6ebe235ca82
ms.openlocfilehash: 7cf1b333afac9f976bb4bf38ce769e6982255959
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318994"
---
# <a name="compiler-error-c2393"></a>Derleyici hatası C2393

> '*symbol*': per-AppDomain simgesi segmenti '*segment*' içinde ayrılamaz

## <a name="remarks"></a>Açıklamalar

**/Clr: Pure** ve **/clr: Safe** derleyici seçenekleri Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ' de desteklenmez.

[AppDomain](../../cpp/appdomain.md) değişkenlerinin kullanımı **/clr: Pure** veya **/clr: Safe** ile derlediğiniz ve güvenli ya da saf bir görüntünün veri kesimleri içeremeyeceği anlamına gelir.

Daha fazla bilgi için bkz. [/clr (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) .

## <a name="example"></a>Örnek

Aşağıdaki örnek C2393 oluşturur. Bu sorunu giderecek bir veri segmenti oluşturmayın.

```cpp
// C2393.cpp
// compile with: /clr:pure /c
#pragma data_seg("myseg")
int n = 0;   // C2393
```
