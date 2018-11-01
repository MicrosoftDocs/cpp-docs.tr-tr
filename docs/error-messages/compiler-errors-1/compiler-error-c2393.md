---
title: Derleyici Hatası C2393
ms.date: 11/04/2016
f1_keywords:
- C2393
helpviewer_keywords:
- C2393
ms.assetid: 4bd95728-e813-4ce8-844a-c6ebe235ca82
ms.openlocfilehash: 39ca693aed3f08e7b2df3d687f94d93384393f23
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50566861"
---
# <a name="compiler-error-c2393"></a>Derleyici Hatası C2393

> '*sembol*': per-appdomain simgesi kesiminde ayrılamaz '*segment*'

## <a name="remarks"></a>Açıklamalar

**/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor.

Kullanımını [appdomain](../../cpp/appdomain.md) değişkenleri gelir ile derleme yapıyorsanız **/CLR: pure** veya **/CLR: safe**, ve güvenli veya saf bir görüntü veri segmentleri içeremez.

Bkz: [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2393 oluşturur. Bu sorunu gidermek için bir veri segmentini oluşturmayın.

```cpp
// C2393.cpp
// compile with: /clr:pure /c
#pragma data_seg("myseg")
int n = 0;   // C2393
```