---
title: BSCMAKE Komut Satırı
ms.date: 11/04/2016
helpviewer_keywords:
- BSCMAKE, command line
ms.assetid: 8006e8cf-8bfe-4c23-868a-b0a25e6bbf0f
ms.openlocfilehash: 61035ce0f211e6a474bb83fc7de7d95b4a29cf3d
ms.sourcegitcommit: 06fc71a46e3c4f6202a1c0bc604aa40611f50d36
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/27/2019
ms.locfileid: "58508773"
---
# <a name="bscmake-command-line"></a>BSCMAKE Komut Satırı

> [!WARNING]
> BSCMAKE hala Visual Studio ile yüklenir ancak artık IDE tarafından kullanılır. Visual Studio 2008'den itibaren göz atma ve sembol bilgilerini otomatik olarak bir SQL Server .sdf dosyası çözüm klasöründe depolanır.

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
