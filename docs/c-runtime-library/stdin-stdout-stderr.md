---
title: stdin, stdout, stderr | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- stdin
- stderr
- stdout
dev_langs:
- C++
helpviewer_keywords:
- stdout function
- standard output stream
- standard error stream
- stdin function
- standard input stream
- stderr function
ms.assetid: badd4735-596d-4498-857c-ec8b7e670e4c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0f6226a6e38326a39ce2921e2a0d6219d01f005b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32408867"
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