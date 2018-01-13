---
title: _set_controlfp | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _set_controlfp
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- set_controlfp
- _set_controlfp
dev_langs: C++
helpviewer_keywords:
- set_controlfp function
- floating-point functions, setting control word
- _set_controlfp function
ms.assetid: e0689d50-f68a-4028-a9c1-fb23eedee4ad
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 132680e529c8f38b5eb69e778b6e635bd424b412
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="setcontrolfp"></a>_set_controlfp
Kayan nokta denetim sözcüğü ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void __cdecl _set_controlfp(  
    unsigned int newControl,  
    unsigned int mask  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `newControl`  
 Yeni Denetim sözcüğü bit değerleri.  
  
 `mask`  
 Ayarlanacak yeni denetim sözcüğü bit maskesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Yok.  
  
## <a name="remarks"></a>Açıklamalar  
 `_set_controlfp` Benzer `_control87`, ancak yalnızca kayan nokta denetim sözcüğü ayarlar `newControl`. Değerleri bitleri kayan nokta denetim durumu gösterir. Kayan nokta denetim durumu duyarlık, yuvarlama ve kayan nokta Matematiği paketindeki sonsuz modlarını değiştirmek programın sağlar. Ayrıca maskeleme veya kayan nokta özel durumlar kullanma maskesini kaldırın `_set_controlfp`. Daha fazla bilgi için bkz: [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md).  
  
 Bu işlev ile derleme yapılırken kullanım dışıdır [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) çünkü ortak dil çalışma zamanı yalnızca varsayılan kayan nokta duyarlık destekler.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|Uyumluluk|  
|-------------|---------------------|-------------------|  
|`_set_controlfp`|\<float.h >|x86 yalnızca işlemci|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)   
 [_clear87, _clearfp](../../c-runtime-library/reference/clear87-clearfp.md)   
 [_status87, _statusfp, _statusfp2](../../c-runtime-library/reference/status87-statusfp-statusfp2.md)