---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları hata LNK1106'
title: Bağlayıcı Araçları Hatası LNK1106
ms.date: 11/04/2016
f1_keywords:
- LNK1106
helpviewer_keywords:
- LNK1106
ms.assetid: 528f7e65-04be-4966-b8af-9276837c7cda
ms.openlocfilehash: 85f353b6424cdd9ad12a99b29fec4f6119472cdb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281411"
---
# <a name="linker-tools-error-lnk1106"></a>Bağlayıcı Araçları Hatası LNK1106

Geçersiz dosya veya disk dolu: konum aranamıyor

Araç, `location` bellek eşlemeli bir dosyayı okuyamadı veya yazamadı.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri denetleyerek onarmak için

1. Disk dolu.

   Biraz alan boşaltın ve yeniden bağlantı kurun.

1. Bir ağ üzerinden bağlantı kurmaya çalışılıyor.

   Bazı ağlar, bağlayıcı tarafından kullanılan bellek eşlemeli dosyaları tam olarak desteklemez. Yerel diskinize bağlanmayı deneyin.

1. Diskinizde bozuk blok.

   İşletim sistemi ve disk donanımında böyle bir hata algılanırsa, ancak bir disk denetleme programı çalıştırmak isteyebilirsiniz.

1. Yığın alanı yetersiz.

   Daha fazla bilgi için bkz. [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) .
