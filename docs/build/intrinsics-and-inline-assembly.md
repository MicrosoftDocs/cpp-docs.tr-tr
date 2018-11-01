---
title: Yapı İçi Değerler ve Satır İçi Derleme
ms.date: 11/04/2016
ms.assetid: 8affd4bb-279d-46f3-851f-8be0a9c5ed3f
ms.openlocfilehash: 033225259c0a33414fe45eba313bb1f1c94eb379
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50515108"
---
# <a name="intrinsics-and-inline-assembly"></a>Yapı İçi Değerler ve Satır İçi Derleme

Bir x64 için kısıtlamaların derleyici satır içi assembler desteği yok etmektir. İşlevler yani C veya C++ ortamında ya da alt yordamlar veya derleyici tarafından desteklenen iç işlevleri olarak yazılması gerekir yazılamaz. Diğerleri oluşturulmazken belirli performans duyarlı işlevlerdir. Performans açısından duyarlı işlevleri, iç işlev olarak uygulanmalıdır.

Derleyici tarafından desteklenen yapı içlerini açıklanan [derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md).

## <a name="see-also"></a>Ayrıca Bkz.

[x64 Yazılım Kuralları](../build/x64-software-conventions.md)