---
title: BSCMAKE Komut Satırı
ms.date: 11/04/2016
helpviewer_keywords:
- BSCMAKE, command line
ms.assetid: 8006e8cf-8bfe-4c23-868a-b0a25e6bbf0f
ms.openlocfilehash: a5a1e8f8e1d022fab9dc1bf4f67713302c11f758
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50446728"
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

İlgili bilgiler için bkz. [BSCMAKE komut dosyası](../../build/reference/bscmake-command-file-response-file.md) ve [BSCMAKE seçenekleri](../../build/reference/bscmake-options.md).

## <a name="see-also"></a>Ayrıca Bkz.

[BSCMAKE Başvurusu](../../build/reference/bscmake-reference.md)