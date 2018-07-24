---
title: BSCMAKE komut satırı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- BSCMAKE, command line
ms.assetid: 8006e8cf-8bfe-4c23-868a-b0a25e6bbf0f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b79f7e7c181112877c795f3601e8211e70403563
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2018
ms.locfileid: "39207753"
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