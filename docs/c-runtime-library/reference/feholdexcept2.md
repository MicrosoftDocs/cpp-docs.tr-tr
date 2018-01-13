---
title: feholdexcept2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname: feholdexcept
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
- feholdexcept
- fenv/feholdexcept
dev_langs: C++
helpviewer_keywords: feholdexcept function
ms.assetid: 88e512ae-b5d8-452c-afe9-c824cd3ef1d8
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b1455f3b963c2d9faf7c2e96a2d6684e0e412ef8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="feholdexcept"></a>feholdexcept
Belirtilen nesne geçerli kayan nokta ortamı kaydeder, kayan nokta durum bayrakları temizler ve, mümkünse durdurma olmayan modu kayan nokta ortamına geçirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int feholdexcept(  
   fenv_t *penv  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `penv`  
 İşaretçi bir `fenv_t` kayan nokta ortamın kopyasını içeren nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlev başarıyla stop kayan nokta özel durum işleme üzerinde açabilirsiniz ve yalnızca, döndürür sıfır.  
  
## <a name="remarks"></a>Açıklamalar  
 `feholdexcept` İşlevi geçerli kayan nokta ortamda durumunu depolamak için kullanılan `fenv_t` tarafından için nesne işaret `penv`ve ortamı yürütülmesine kayan nokta özel durumları kesme değil. Bu Dur olmayan modu olarak bilinir.  Bu mod kullanılarak ortamı geri yüklenene kadar devam [fesetenv](fesetenv1.md) veya [feupdateenv](../../c-runtime-library/reference/feupdateenv.md).  
  
 Bir veya daha fazla kayan nokta özel durumlar çağrıyı yapandan gizlemek için gereken bir alt yordama başındaki bu işlevi kullanabilirsiniz. Bir özel durum raporu için yalnızca istenmeyen özel durumları kullanarak temizleyebilirsiniz [feclearexcept,](../../c-runtime-library/reference/feclearexcept1.md) ve çağrısıyla durdurma olmayan modu bitiş `feupdateenv`.  
  
 Bu işlevi kullanmak için erişim kullanarak önleyebilir kayan nokta iyileştirmeler kapatmanız gerekir `#pragma fenv_access(on)` çağrı önce yönergesi. Daha fazla bilgi için bkz: [fenv_access](../../preprocessor/fenv-access.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|C üstbilgisi|C++ üstbilgi|  
|--------------|--------------|------------------|  
|`feholdexcept`|\<fenv.h >|\<cfenv >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Alfabetik işlev başvurusu](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [feclearexcept](../../c-runtime-library/reference/feclearexcept1.md)   
 [fesetenv](fesetenv1.md)   
 [feupdateenv](../../c-runtime-library/reference/feupdateenv.md)