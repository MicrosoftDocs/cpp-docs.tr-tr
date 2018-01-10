---
title: "Dosya okuma-yazma erişimi sabitleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.constants.file
dev_langs: C++
helpviewer_keywords:
- read/write access constants
- write access constants
- access constants for file read/write
- constants [C++], file attributes
- file read/write access constants
ms.assetid: 56cd1d22-39a5-4fcf-bea2-7046d249e8ee
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 789d0ae6b0b9b38312896adf079e7c10dcde7556
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="file-readwrite-access-constants"></a>Dosya Okuma/Yazma Erişimi Sabitleri
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#include <stdio.h>  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sabitleri dosya için istenen erişim türüne ("a", "r" veya "w") belirtin. Her iki [çeviri modu](../c-runtime-library/file-translation-constants.md) ("b" veya "t") ve [commit-to-disk modu](../c-runtime-library/commit-to-disk-constants.md) ("c" veya "n"), access, türü ile belirtilebilir.  
  
 Erişim türleri aşağıda açıklanmıştır.  
  
 **"a"**  
 Yazma (ekleme); dosya sonunda açar henüz yoksa dosyayı ilk olarak oluşturur. Tüm işlemler dosyanın sonunda gerçekleşmektedir yazma. Dosya işaretçisini kullanarak konumlandırılmasına ancak `fseek` veya **geri sarma**, herhangi bir işlemi gerçekleştirilir yazmadan önce her zaman geri dosyanın sonuna taşınır.  
  
 **"bir +"**  
 Aynı şekilde yukarıdaki, aynı zamanda okuma izin verir.  
  
 **"r"**  
 Okuma için açılır. Dosya yok veya bulunamadı, dosyayı açmak için çağrı başarısız olur.  
  
 **"r +"**  
 Hem okuma ve yazma için açılır. Dosya yok veya bulunamadı, dosyayı açmak için çağrı başarısız olur.  
  
 **"w"**  
 Boş bir dosya yazma için açılır. Verilen dosya varsa, içeriği yok.  
  
 **"w +"**  
 Hem okumak ve yazmak için boş bir dosya açar. Verilen dosya varsa, içeriği yok.  
  
 "R +", "w +" veya "bir +" türü belirtildiğinde, hem okuma ve yazma izin (dosya "güncelleştirmesi" açık olarak kabul edilir). Ancak, okuma ve yazma arasında geçiş yaptığınızda, olmalıdır bir araya giren `fflush`, `fsetpos`, `fseek`, veya **geri sarma** işlemi. Geçerli konum için belirtilen `fsetpos` veya `fseek` işlemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_fdopen, _wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)   
 [fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen, _wfreopen](../c-runtime-library/reference/freopen-wfreopen.md)   
 [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)   
 [_popen, _wpopen](../c-runtime-library/reference/popen-wpopen.md)   
 [Global Sabitler](../c-runtime-library/global-constants.md)