---
title: İşlev Türleri
ms.date: 11/04/2016
ms.assetid: 7e33d5f4-dabb-406d-afb3-13777b995028
ms.openlocfilehash: 22778f3eaefa6dbcf5f85e54c0940867ef52ab72
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50526413"
---
# <a name="function-types"></a>İşlev Türleri

Temel işlevleri iki tür vardır. Bir yığın çerçevesini gerektiren bir işlev çerçeve işlevi çağrılır. Bir yığın çerçevesini gerektirmeyen bir işlev, bir yaprak işlevi çağrılır.

Yığın alanı ayırır, diğer işlevleri çağırır, kalıcı Yazmaçları kaydeder veya özel durum işleme kullanan bir işlev bir çerçeve işlevidir. Ayrıca, bir işlevin tablo girişi gerektirir. Çerçeve işlevi, bir giriş ve bitiş gerektirir. Çerçeve işlevi yığın alanı dinamik olarak ayırabilir ve bir çerçeve işaretçisi tercih edebilirsiniz. Çerçeve işlevi tüm özelliklerini, atma standart çağırma vardır.

Çerçeve işlevi başka bir işlevi çağırmadığı sonra yığın hizalamak için gerekli değildir (bölümünde başvurulan [yığın ayırma](../build/stack-allocation.md)).

Bir yaprak işlev bir tablo girişi gerektirmeyen bir işlevdir. Bu, onun tüm işlevler veya yığın alanı ayırmak, yani RSP dahil olmak üzere tüm kalıcı Yazmaçları değişiklik yapamazsınız. Yığın yürütürken hizalanmamış bırakın izin verilir.

## <a name="see-also"></a>Ayrıca Bkz.

[Yığın Kullanımı](../build/stack-usage.md)
