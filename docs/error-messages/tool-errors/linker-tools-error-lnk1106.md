---
title: Bağlayıcı Araçları Hatası LNK1106
ms.date: 11/04/2016
f1_keywords:
- LNK1106
helpviewer_keywords:
- LNK1106
ms.assetid: 528f7e65-04be-4966-b8af-9276837c7cda
ms.openlocfilehash: 091d4e173bfb2eff8ffee2b5c30647f4d5e3bc04
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80195376"
---
# <a name="linker-tools-error-lnk1106"></a>Bağlayıcı Araçları Hatası LNK1106

Geçersiz dosya veya disk dolu: konum aranamıyor

Araç, bellek eşlemeli bir dosyada `location` okuyamadı veya yazamadı.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri denetleyerek onarmak için

1. Disk dolu.

   Biraz alan boşaltın ve yeniden bağlantı kurun.

1. Bir ağ üzerinden bağlantı kurmaya çalışılıyor.

   Bazı ağlar, bağlayıcı tarafından kullanılan bellek eşlemeli dosyaları tam olarak desteklemez. Yerel diskinize bağlanmayı deneyin.

1. Diskinizde bozuk blok.

   İşletim sistemi ve disk donanımında böyle bir hata algılanırsa, ancak bir disk denetleme programı çalıştırmak isteyebilirsiniz.

1. Yığın alanı yetersiz.

   Daha fazla bilgi için bkz. [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) .
