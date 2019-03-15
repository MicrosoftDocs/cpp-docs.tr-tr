---
title: BSCMAKE Komut Satırı
ms.date: 11/04/2016
helpviewer_keywords:
- BSCMAKE, command line
ms.assetid: 8006e8cf-8bfe-4c23-868a-b0a25e6bbf0f
ms.openlocfilehash: 7724069a401aadcdb2e3e8487dc85273dac357fc
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57818654"
---
# <a name="bscmake-command-line"></a>BSCMAKE Komut Satırı

BSCMAKE çalıştırmak için aşağıdaki komut satırı sözdizimini kullanın:

```
BSCMAKE [options] sbrfiles
```

Seçenekler yalnızca görünebilir `options` komut satırında alan.

*Sbrfiles* alan bir derleme veya derleyici tarafından oluşturulan bir veya daha fazla .sbr dosyaları belirtir. .Sbr dosyaları adları, boşluk veya sekme ile ayırın. Uzantı belirtmeniz gerekir; Varsayılan yok. Bir yol ile dosya adı belirtin ve işletim sistemi joker karakterleri kullanabilirsiniz (\* ve?).

Artımlı derleme sırasında özgün yapının bir parçası değildi yeni .sbr dosyaları belirtebilirsiniz. Tüm katkılar gözatma bilgisi dosyası içinde kalmasını istiyorsanız, .bsc dosyası oluşturmak için kullanılan (kesilmiş dosyaları dahil) tüm .sbr dosyaları belirtmeniz gerekir. .Sbr dosyası atlarsanız, gözatma bilgisi dosyası için bu dosyanın katkı kaldırılır.

Kesilen .sbr dosyası için tam bir yapı belirtmeyin. Tam derleme Katkıları tüm belirtilen .sbr dosyalarını gerektirir. Tam derleme gerçekleştirmeden önce projeyi yeniden derleyin ve boş her dosya için yeni bir .sbr dosyası oluştur.

BSCMAKE üç .sbr dosyaları MAIN.bsc adlı bir dosya oluşturmak için şu komutu çalıştırır:

```
BSCMAKE main.sbr file1.sbr file2.sbr
```

İlgili bilgiler için bkz. [BSCMAKE komut dosyası](bscmake-command-file-response-file.md) ve [BSCMAKE seçenekleri](bscmake-options.md).

## <a name="see-also"></a>Ayrıca bkz.

[BSCMAKE Başvurusu](bscmake-reference.md)
