---
description: 'Şu konuda daha fazla bilgi edinin: BSCMAKE komut satırı'
title: BSCMAKE Komut Satırı
ms.date: 11/04/2016
helpviewer_keywords:
- BSCMAKE, command line
ms.assetid: 8006e8cf-8bfe-4c23-868a-b0a25e6bbf0f
ms.openlocfilehash: a0d6cb81fb207c30cd89fbfe3a988380a865a399
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182664"
---
# <a name="bscmake-command-line"></a>BSCMAKE Komut Satırı

> [!WARNING]
> BSCMAKE, Visual Studio ile hala yüklü olsa da artık IDE tarafından kullanılmıyor. Visual Studio 2008 ' den itibaren, gezinme ve sembol bilgileri çözüm klasöründeki bir SQL Server. sdf dosyasında otomatik olarak depolanır.

BSCMAKE çalıştırmak için aşağıdaki komut satırı sözdizimini kullanın:

```
BSCMAKE [options] sbrfiles
```

Seçenekler, yalnızca `options` komut satırındaki alanında görünebilir.

*Sbrfiles* alanı bir derleyici veya Assembler tarafından oluşturulan bir veya daha fazla. sbr dosyasını belirtir. . Sbr dosyalarının adlarını boşluklar veya sekmeler ile ayırın. Uzantıyı belirtmeniz gerekir; Varsayılan yoktur. Dosya adında bir yol belirtebilirsiniz ve işletim sistemi joker karakterlerini ( \* ve?) kullanabilirsiniz.

Artımlı bir yapı sırasında, özgün derleme kapsamında olmayan yeni. sbr dosyaları belirtebilirsiniz. Tüm katkıların tarama bilgileri dosyasında kalmasını istiyorsanız, başlangıçta. bsc dosyasını oluşturmak için kullanılan tüm. sbr dosyalarını (kesilen dosyalar dahil) belirtmeniz gerekir. Bir. sbr dosyasını atlarsanız, bu dosyanın göz at bilgi dosyasına katkısı kaldırılır.

Tam derleme için kesilen. sbr dosyası belirtmeyin. Tam derleme, belirtilen tüm. sbr dosyalarından katılımları gerektirir. Tam yapı gerçekleştirmeden önce, projeyi yeniden derleyin ve her boş dosya için yeni bir. sbr dosyası oluşturun.

Aşağıdaki komut, üç. sbr dosyasından MAIN. bsc adlı bir dosya oluşturmak için BSCMAKE ' i çalıştırır:

```
BSCMAKE main.sbr file1.sbr file2.sbr
```

İlgili bilgiler için bkz. [bscmake komut dosyası](bscmake-command-file-response-file.md) ve [bscmake seçenekleri](bscmake-options.md).

## <a name="see-also"></a>Ayrıca bkz.

[BSCMAKE başvurusu](bscmake-reference.md)
