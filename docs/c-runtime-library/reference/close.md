---
title: _close | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _close
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
f1_keywords: _close
dev_langs: C++
helpviewer_keywords:
- _close function
- close function
- files [C++], closing
ms.assetid: 4708a329-8acf-4cd9-b7b0-a952e1897247
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f46560346718016af015410730696e766afa5c9a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="close"></a>_close
Bir dosyayı kapatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _close(   
   int fd   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `fd`  
 Açık olan dosyaya başvuran dosya tanımlayıcısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `_close`Dosya başarılı bir şekilde kapatıldı 0 döndürür. Dönüş değeri-1 hata gösterir.  
  
## <a name="remarks"></a>Açıklamalar  
 `_close` İşlev ile ilişkili dosya kapatır `fd`.  
  
 Dosya tanımlayıcısı ve temel işletim sistemi dosya işleci kapatılır. Bu nedenle, çağırmak gerekli değildir `CloseHandle` dosyayı ilk olarak Win32 işlevi kullanılarak açılmışsa `CreateFile` ve kullanarak bir dosyaya tanımlayıcısı dönüştürülen `_open_osfhandle`.  
  
 Bu işlev parametrelerini doğrular. Varsa `fd` hatalı dosya tanımlayıcısı açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, -1 döndürür işlevleri ve `errno` ayarlanır `EBADF`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|  
|-------------|---------------------|---------------------|  
|`_close`|\<io.h >|\<errno.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [_kurulum Aç](../../c-runtime-library/reference/open-wopen.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Düşük düzey g/ç](../../c-runtime-library/low-level-i-o.md)   
 [_chsize](../../c-runtime-library/reference/chsize.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_dup, _dup2](../../c-runtime-library/reference/dup-dup2.md)   
 [_kurulum Aç, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_unlink, _wunlink](../../c-runtime-library/reference/unlink-wunlink.md)