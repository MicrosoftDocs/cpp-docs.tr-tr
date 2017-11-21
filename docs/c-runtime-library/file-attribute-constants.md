---
title: "Dosya öznitelik sabitleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- A_HIDDEN
- _A_NORMAL
- _A_SUBDIR
- _A_RDONLY
- A_NORMAL
- A_SUBDIR
- _A_SYSTEM
- c.constants.file
- _A_HIDDEN
- A_RDONLY
- _A_ARCH
- A_ARCH
dev_langs: C++
helpviewer_keywords:
- constants [C++], file attributes
- file attribute constants [C++]
- _A_SYSTEM constant
- files [C++], file attribute constants
- _A_SUBDIR constant
- _A_ARCH constant
- _A_NORMAL constant
- _A_HIDDEN constant
- _A_RDONLY constant
ms.assetid: 8dc8ccb9-99f5-446b-876c-7ebecc2f764f
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 670f8c109593148076c31bd4957f658607a5d5e1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="file-attribute-constants"></a>Dosya Öznitelik Sabitleri
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#include <io.h>  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sabitleri dosya veya dizin işlev tarafından belirtilen geçerli özniteliklerini belirtin.  
  
 Öznitelikleri tarafından bildirim sabitlerden gösterilir:  
  
 `_A_ARCH`  
 Arşiv. Dosya değiştirildi ve yedekleme komutu tarafından işaretli olduğunda ayarlayın. Değer: 0x20  
  
 `_A_HIDDEN`  
 Gizli bir dosya. Normalde /AH seçeneği kullanılmıyorsa DIR komutu ile görülür. Normal dosyalarının yanı sıra bu öznitelik dosyalarıyla ilgili bilgiler döndürür. Değer: 0x02  
  
 `_A_NORMAL`  
 Normal. Dosya okuma veya yazma kısıtlama. Değer: 0x00  
  
 `_A_RDONLY`  
 Salt okunur. Dosya yazma için açılamıyor ve aynı ada sahip bir dosya oluşturulamaz. Değer: 0x01  
  
 `_A_SUBDIR`  
 Alt dizin. Değer: 0x10  
  
 `_A_SYSTEM`  
 Sistem dosyası. Normalde /AS seçeneği kullanılmıyorsa DIR komutu ile görülür. Değer: 0x04  
  
 Birden çok sabitleri OR işleci (&#124;) ile birleştirilebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dosya arama işlevleri](../c-runtime-library/filename-search-functions.md)   
 [Genel sabitler](../c-runtime-library/global-constants.md)