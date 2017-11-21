---
title: _get_fmode | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _get_fmode
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- get_fmode
- _get_fmode
dev_langs: C++
helpviewer_keywords:
- _get_fmode function
- file translation [C++], default mode
- get_fmode function
ms.assetid: 22ea70e2-b9b5-422d-b514-64f4beaea45c
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b3e123b563a2d39fd1ec614a6481e8beceaad631
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="getfmode"></a>_get_fmode
Dosya g/ç işlemleri için varsayılan dosya çevirisi modu alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
errno_t _get_fmode(   
   int * pmode   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [out]`pmode`  
 Tamsayı geçerli varsayılan mod ile doldurulması için bir işaretçi: `_O_TEXT` veya `_O_BINARY`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır döndürür; hatasında bir hata kodu. Varsa `pmode` olan `NULL`, geçersiz parametre işleyicisi açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa `errno` ayarlanır `EINVAL` ve işlevi döndürür `EINVAL`.  
  
## <a name="remarks"></a>Açıklamalar  
 İşlev değerini alır [_fmode](../../c-runtime-library/fmode.md) genel değişkeni. Bu değişken alt düzey her ikisi için varsayılan dosya çevirisi modu belirtir ve dosya g/ç işlemleri gibi akışını `_open`, `_pipe`, `fopen`, ve `freopen`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|  
|-------------|---------------------|---------------------|  
|`_get_fmode`|\<stdlib.h >|\<fcntl.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
 Örnekte bkz [_set_fmode](../../c-runtime-library/reference/set-fmode.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_fmode](../../c-runtime-library/fmode.md)   
 [_set_fmode](../../c-runtime-library/reference/set-fmode.md)   
 [_setmode](../../c-runtime-library/reference/setmode.md)   
 [Metin ve ikili mod dosyası g/ç](../../c-runtime-library/text-and-binary-mode-file-i-o.md)