---
title: fesetenv | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname: fesetenv
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
- fesetenv
- fenv/fesetenv
dev_langs: C++
helpviewer_keywords: fesetenv function
ms.assetid: ffc64fff-8ea7-4d59-9e04-ff96ef8cd012
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 98ceb7a1be89284f02de2f1f2ed42e6e3198d885
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="fesetenv"></a>fesetenv
Geçerli kayan nokta ortamını ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int fesetenv(  
   const fenv_t *penv  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `penv`  
 İşaretçi bir `fenv_t` içeren bir kayan nokta ortamı kümesi olarak yapılan bir çağrı tarafından nesne [fegetenv](fegetenv1.md) veya [feholdexcept](feholdexcept2.md). Varsayılan başlangıç kayan nokta ortamını FE_DFL_ENV makrosu kullanarak da belirtebilirsiniz.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Ortam başarılı bir şekilde ayarlarsanız 0 döndürür. Aksi takdirde, sıfır olmayan bir değer döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 `fesetenv` İşlevi ayarlar depolanan değeriyle geçerli kayan nokta ortamından `fenv_t` tarafından için nesne işaret `penv`. Kayan nokta ortamıdır durumu bayrakları ve kayan nokta hesaplamaları etkileyecek denetim modları kümesi. Bu yuvarlama modu ve kayan nokta özel durumlar için durumu bayrakları içerir.  Varsa `penv` FE_DFL_ENV değil veya geçerli bir göstermiyor `fenv_t` nesnesi, sonraki davranış tanımlanmadı.  
  
 Bu işlev için bir çağrı bulunan durumu bayrakları özel ayarlar `penv` nesnesi, ancak değil yükselt Bu özel durumlar.  
  
 Bu işlevi kullanmak için erişim kullanarak önleyebilir kayan nokta iyileştirmeler kapatmanız gerekir `#pragma fenv_access(on)` çağrı önce yönergesi. Daha fazla bilgi için bkz: [fenv_access](../../preprocessor/fenv-access.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|C üstbilgisi|C++ üstbilgi|  
|--------------|--------------|------------------|  
|`fesetenv`|\<fenv.h >|\<cfenv >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Alfabetik işlev başvurusu](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fegetenv](../../c-runtime-library/reference/fegetenv1.md)   
 [feclearexcept](../../c-runtime-library/reference/feclearexcept1.md)   
 [feholdexcept](../../c-runtime-library/reference/feholdexcept2.md)   
 [fesetexceptflag](../../c-runtime-library/reference/fesetexceptflag2.md)