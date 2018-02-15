---
title: _setmaxstdio | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _setmaxstdio
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
- setmaxstdio
- _setmaxstdio
dev_langs:
- C++
helpviewer_keywords:
- maximum open files
- _setmaxstdio function
- setmaxstdio function
- open files, maximum
ms.assetid: 9e966875-9ff5-47c4-9b5f-e79e83b70249
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5317437202cef423759ac850aab2360892521746
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="setmaxstdio"></a>_setmaxstdio
Aynı anda açık dosyaları sayısı için üst sınır ayarlar `stdio` düzeyi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _setmaxstdio(  
   int newmax   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `newmax`  
 Aynı anda açık dosyaları sayısı için yeni maksimum `stdio` düzeyi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Döndürür `newmax` başarılıysa; Aksi takdirde -1.  
  
 Varsa `newmax` olan değerinden `_IOB_ENTRIES` ya da açıklandığı gibi en yüksek sayısı tanıtıcısı geçersiz parametre işleyicisi işletim sisteminde kullanılabilir çağrılır sonra büyük [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için bu işlev dönüşleri -1 ve kümelerini yürütülmesine izin veriliyorsa `errno` için `EINVAL`.  
  
 Bunlar ve diğer hata kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 `_setmaxstdio` İşlevi değişiklikler, aynı anda açık olabilir dosya sayısı için maksimum değeri `stdio` düzeyi.  
  
 C çalışma zamanı g/ç şimdi önceki sürümlerde Win32 platformları pek çok fazla açık dosyalar destekler. 2.048 dosyaları için aynı anda en açık olabilir [lowio düzeyi](../../c-runtime-library/low-level-i-o.md) (diğer bir deyişle, açılır ve yoluyla erişilen `_open`, `_read`, `_write`, g/ç işlevlerin ailesi vb.). En çok 512 dosyaları aynı anda en açık olabilir [stdio düzeyi](../../c-runtime-library/stream-i-o.md) (diğer bir deyişle, açılır ve yoluyla erişilen `fopen`, `fgetc`, `fputc`, vb. ailesi işlevlerini). 512 açık dosyaları sınırının `stdio` düzeyi yoluyla 2.048 maksimum artırılmasını `_setmaxstdio` işlevi.  
  
 Çünkü `stdio`-gibi işlevler, düzey `fopen`, üstünde oluşturulmuş `lowio` İşlevler, 2.048 en fazla olduğu için C çalışma zamanı kitaplığı erişilen aynı anda açık dosya sayısı üst sınırı.  
  
> [!NOTE]
>  Bu üst sınır ötesindedir belirli Win32 platform ve yapılandırması tarafından desteklenen olabilir.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_setmaxstdio`|\<stdio.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
 Bkz: [_getmaxstdio](../../c-runtime-library/reference/getmaxstdio.md) kullanma örneği için `_setmaxstdio`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış g/ç](../../c-runtime-library/stream-i-o.md)