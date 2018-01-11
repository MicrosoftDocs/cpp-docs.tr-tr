---
title: stdin, stdout, stderr | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- stdin
- stderr
- stdout
dev_langs: C++
helpviewer_keywords:
- stdout function
- standard output stream
- standard error stream
- stdin function
- standard input stream
- stderr function
ms.assetid: badd4735-596d-4498-857c-ec8b7e670e4c
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7683a0ed1e40a0b65ea3a400c460dcd23ecef2d0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="stdin-stdout-stderr"></a>stdin, stdout, stderr
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      FILE *stdin;   
FILE *stdout;   
FILE *stderr;   
#include <stdio.h>  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu giriş, çıkış ve hata çıkışı için standart akışlarıdır.  
  
 Standart çıktı ve standart hata ekrana yazdırılır sırasında varsayılan olarak, standart giriş klavyeden okunur.  
  
 Aşağıdaki akış işaretçileri standart akışlarına erişmek kullanılabilir:  
  
|İşaretçi|Akış|  
|-------------|------------|  
|`stdin`|Standart giriş|  
|**STDOUT**|Standart çıktı|  
|`stderr`|Standart hata|  
  
 Bu işaretçileri işlevleri bağımsız değişken olarak kullanılabilir. Gibi bazı işlevleri **getchar** ve `putchar`, kullanın `stdin` ve **stdout** otomatik olarak.  
  
 Bu işaretçileri sabittir ve yeni değerler atanamaz. `freopen` İşlevi, disk dosyaları veya diğer aygıtlar için akışlar yönlendirmek için kullanılabilir. İşletim sistemi, programın standart giriş ve çıkış komut düzeyinde yönlendirmenizi sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış g/ç](../c-runtime-library/stream-i-o.md)   
 [Global Sabitler](../c-runtime-library/global-constants.md)