---
title: "BSCMAKE komut satırı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: BSCMAKE, command line
ms.assetid: 8006e8cf-8bfe-4c23-868a-b0a25e6bbf0f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c00a3842db37cc5027809f717ac47bd471dd073f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="bscmake-command-line"></a>BSCMAKE Komut Satırı
BSCMAKE çalıştırmak için aşağıdaki komut satırı söz dizimini kullanın:  
  
```  
BSCMAKE [options] sbrfiles  
```  
  
 Seçenekler yalnızca görünebilir `options` komut satırında alan.  
  
 *Sbrfiles* alan derleyici veya derleyici tarafından oluşturulan bir veya daha fazla .sbr dosyaları belirtir. .Sbr dosyaları adları, boşluk ya da sekme ile ayırın. Uzantı belirtmeniz gerekir; Varsayılan yok. Dosya adı ile bir yolu belirtebilirsiniz ve işletim sistemi joker karakterleri kullanabilirsiniz (* ve?).  
  
 Bir artımlı derleme sırasında özgün yapı parçası değildi yeni .sbr dosyaları belirtebilirsiniz. Gözatma bilgileri dosyası kalmasına tüm Katkıları istiyorsanız, ilk olarak .bsc dosyası oluşturmak için kullanılan (kesilmiş dosyaları dahil) tüm .sbr dosyaları belirtmeniz gerekir. .Sbr dosyası atlarsanız, o dosyanın katkı için gözatma bilgileri dosyası kaldırılır.  
  
 Tam bir yapı için kesilmiş .sbr dosyası belirtmeyin. Tam bir yapı Katkıları tüm belirtilen .sbr dosyalarından gerektirir. Tam bir yapı gerçekleştirmeden önce Proje derlenir ve boş her dosya için yeni bir .sbr dosyası oluşturun.  
  
 BSCMAKE MAIN.bsc üç .sbr dosyaları adlı bir dosya oluşturmak için şu komutu çalıştırır:  
  
```  
BSCMAKE main.sbr file1.sbr file2.sbr  
```  
  
 İlgili bilgi için bkz: [BSCMAKE komut dosyası](../../build/reference/bscmake-command-file-response-file.md) ve [BSCMAKE seçenekleri](../../build/reference/bscmake-options.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [BSCMAKE Başvurusu](../../build/reference/bscmake-reference.md)