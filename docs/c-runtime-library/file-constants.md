---
title: Dosya sabitleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _O_EXCL
- _O_RDWR
- _O_APPEND
- _O_RDONLY
- _O_TRUNC
- _O_CREAT
- _O_WRONLY
dev_langs:
- C++
helpviewer_keywords:
- _O_RDWR constant
- O_EXCL constant
- O_RDWR constant
- O_WRONLY constant
- O_APPEND constant
- O_CREAT constant
- _O_CREAT constant
- _O_APPEND constant
- _O_EXCL constant
- O_TRUNC constant
- _O_RDONLY constant
- _O_TRUNC constant
- O_RDONLY constant
- _O_WRONLY constant
ms.assetid: c8fa5548-9ac2-4217-801d-eb45e86f2fa4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 31d6deadb3d7cae7ed8717056b632cd46fa79370
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32389721"
---
# <a name="file-constants"></a>Dosya Sabitleri
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#include <fcntl.h>  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bir tamsayı ifade oluşturulmuş ya da bu sabitleri birkaçını okuma veya yazma işlemlerini izin türünü belirler. Bir veya daha fazla sabit bir çeviri modu sabit ile birleştirerek biçimlendirilmemiş.  
  
 Dosya sabitleri aşağıdaki gibidir:  
  
 `_O_APPEND`  
 Dosya işaretçisini sonuna kadar her yazma işlemi önce dosyayı yeniden konumlandırır.  
  
 `_O_CREAT`  
 Oluşturur ve yazmak için yeni bir dosya açar; dosya tarafından belirtilen, bunun hiçbir etkisi olmaz *filename* bulunmaktadır.  
  
 `_O_EXCL`  
 Belirtilen dosya bir hata değeri döndürür *filename* bulunmaktadır. Yalnızca kullanıldığında geçerlidir `_O_CREAT`.  
  
 `_O_RDONLY`  
 Yalnızca okumak için dosyayı açar; Bu bayrak, tipleri belirtilmezse `_O_RDWR` ya da `_O_WRONLY` verilebilir.  
  
 `_O_RDWR`  
 Hem okumak ve yazmak için dosyayı açar; Bu bayrak, tipleri belirtilmezse `_O_RDONLY` ya da `_O_WRONLY` verilebilir.  
  
 `_O_TRUNC`  
 Açılır ve uzunluğu sıfır olarak varolan bir dosyanın keser; Dosya yazma iznine sahip olmalıdır. Dosya içeriği yok. Bu bayrak verilen varsa belirtemezsiniz `_O_RDONLY`.  
  
 `_O_WRONLY`  
 Yalnızca yazmak için dosyayı açar; Bu bayrak, tipleri belirtilmezse `_O_RDONLY` ya da `_O_RDWR` verilebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_kurulum Aç, _wopen](../c-runtime-library/reference/open-wopen.md)   
 [_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md)   
 [Global Sabitler](../c-runtime-library/global-constants.md)