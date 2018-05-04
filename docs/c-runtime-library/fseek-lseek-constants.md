---
title: fseek, _lseek sabitleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- SEEK_END
- SEEK_SET
- SEEK_CUR
dev_langs:
- C++
helpviewer_keywords:
- SEEK_SET constant
- SEEK_END constant
- SEEK_CUR constant
ms.assetid: 9deeb13e-5aa3-4c33-80d8-721c80a4de9d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fbcf0a1106610740a585b7e4f8b68e3fc9b6a8f7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="fseek-lseek-constants"></a>fseek, _lseek Sabitleri
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#include <stdio.h>  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 *Kaynak* bağımsız değişkeni ilk konumlarını belirtir ve bildirim sabitlerden biri olabilir:  
  
|Sabit|Açıklama|  
|--------------|-------------|  
|`SEEK_END`|Dosya sonu|  
|`SEEK_CUR`|Dosya işaretçisini geçerli konumu|  
|`SEEK_SET`|Dosya başlangıcı|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [fseek, _fseeki64](../c-runtime-library/reference/fseek-fseeki64.md)   
 [_lseek, _lseeki64](../c-runtime-library/reference/lseek-lseeki64.md)   
 [Global Sabitler](../c-runtime-library/global-constants.md)