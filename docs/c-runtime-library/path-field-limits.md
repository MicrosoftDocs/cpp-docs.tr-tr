---
title: "Yol alanı sınırları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _MAX_EXT
- _MAX_DIR
- _MAX_PATH
- _MAX_FNAME
- _MAX_DRIVE
dev_langs:
- C++
helpviewer_keywords:
- path field constants
- MAX_FNAME constant
- _MAX_DIR constant
- _MAX_DRIVE constant
- paths, maximum limit
- _MAX_PATH constant
- MAX_DRIVE constant
- _MAX_FNAME constant
- _MAX_EXT constant
- MAX_DIR constant
- MAX_EXT constant
ms.assetid: 2b5d0e43-1347-45b4-8397-24a8a45c444e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c585afee6bbea3d0cc48b696bc005b9a8d6c7992
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="path-field-limits"></a>Yol Alanı Sınırları
## <a name="syntax"></a>Sözdizimi  
  
```  
#include <stdlib.h>  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sabitleri ve tek tek alanların yolu içindeki yol için uzunluk üst sınırını tanımlayın.  
  
|Sabit|Açıklama|  
|--------------|-------------|  
|`_MAX_DIR`|Dizin bileşeni uzunluğu üst sınırı|  
|`_MAX_DRIVE`|Sürücü bileşen uzunluğu üst sınırı|  
|`_MAX_EXT`|Uzantı bileşeni uzunluğu üst sınırı|  
|`_MAX_FNAME`|Dosya adı bileşeni uzunluğu üst sınırı|  
|`_MAX_PATH`|Tam yolunun maksimum uzunluğu|  
  
> [!NOTE]
>  C çalışma zamanı yol uzunluğu en çok 32768 karakter uzunluğu destekler, ancak bu uzun yolları destekleyecek şekilde özellikle dosya sistemi, işletim sistemi kadar olan. Alanların toplamını aşmamanız gereken `_MAX_PATH` için tam geriye dönük uyumluluk FAT32 dosya sistemleri. [!INCLUDE[win2kfamily](../c-runtime-library/includes/win2kfamily_md.md)], [!INCLUDE[WinXpFamily](../atl/reference/includes/winxpfamily_md.md)], [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)], ve Windows Vista NTFS dosya sistemi destekler yolları 32768 karakter kadar uzunlukta ancak yalnızca Unicode API'leri kullanırken. Yolun karakterden uzun yol adları kullanırken, önek \\ \\? \ ve C çalışma zamanı işlevleri Unicode sürümlerini kullanın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Global Sabitler](../c-runtime-library/global-constants.md)