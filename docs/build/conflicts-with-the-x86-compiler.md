---
title: x86 Derleyicisi ile Çakışma
ms.date: 11/04/2016
ms.assetid: 8e47f0d3-afe0-42d9-9efa-de239ddd3a05
ms.openlocfilehash: e56ebc5631ac5c96a9cdd2dfc2b8e81cdeed9769
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50614272"
---
# <a name="conflicts-with-the-x86-compiler"></a>x86 Derleyicisi ile Çakışma

X86 kullandığınızda 4 bayt yığın üzerinde otomatik olarak hizalanmaz daha büyük olan veri türleri bir uygulama derlemek için derleyici. Çünkü derleyicisidir bir 4 bayt hizalı yığını, örneğin, bir 64-bit tamsayı olan 4 bayt daha büyük bir şey olamaz otomatik olarak hizalanmayacak 8 baytlık adresin x86 mimarisi.

Hizalanmamış veri ile çalışma, iki olası etkilere sahiptir.

- Hizalanmış konumlara erişmek için gereken daha Hizalanmamış konumlara erişmek için daha uzun sürebilir.

- Hizalanmamış konumları birbirine kenetlenmiş işlemler içinde kullanılamaz.

Daha fazla katı hizalama gerektiren kullanırsanız `__declspec(align(N)) on your variable declarations`. Bu, derleyicinin yığın belirtimleri karşılamak için dinamik olarak hizalamak neden olur. Ancak, yığın çalışma zamanında dinamik olarak ayarlama, uygulamanızın daha yavaş yürütme neden olabilir.

## <a name="see-also"></a>Ayrıca Bkz.

[Türler ve Depolama](../build/types-and-storage.md)<br/>
[align](../cpp/align-cpp.md)