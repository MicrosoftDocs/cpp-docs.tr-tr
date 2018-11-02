---
title: Bağlayıcı Araçları Hatası LNK1106
ms.date: 11/04/2016
f1_keywords:
- LNK1106
helpviewer_keywords:
- LNK1106
ms.assetid: 528f7e65-04be-4966-b8af-9276837c7cda
ms.openlocfilehash: 7551e2f3f1efc90913981feb674f48aadb9ace51
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50619043"
---
# <a name="linker-tools-error-lnk1106"></a>Bağlayıcı Araçları Hatası LNK1106

dosya geçersiz veya disk dolu: konumuna aranamıyor

Aracı yüklenemedi okuma veya yazma `location` bellek eşlemeli dosya olarak.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için

1. Disk dolu.

   Biraz alan boşaltın ve yeniden bağlayın.

1. Bir ağ üzerinden bağlantı çalışılıyor.

   Bazı ağlar bağlayıcı tarafından kullanılan bellek eşlemeli dosyalar tam olarak desteklemez. Yerel diskinizde bağlamayı deneyin.

1. Diskinizde bozuk blok.

   Disk donanım ve işletim sistemi gibi bir hata algılandı olsa da, bir disk denetleme programı çalıştırmak isteyebilirsiniz.

1. Yığın alanı kalmadı.

   Bkz: [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) daha fazla bilgi için.