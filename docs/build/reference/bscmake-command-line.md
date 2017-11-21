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
ms.openlocfilehash: 278518ae37a4e76ea4fe0252e3341e54daebe599
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [BSCMAKE başvurusu](../../build/reference/bscmake-reference.md)