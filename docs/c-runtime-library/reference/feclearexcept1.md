---
title: feclearexcept1 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- feclearexcept
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
- feclearexcept
- fenv/feclearexcept
dev_langs:
- C++
helpviewer_keywords:
- feclearexcept function
ms.assetid: ef419da3-c248-4432-b53c-8e7a475d9533
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 661e93b181005acbd822fbb3ea2a2f970bbedf3d
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="feclearexcept"></a>feclearexcept
Bağımsız değişkeni tarafından belirtilen kayan nokta özel durumu bayrakları sıfırlamaya çalışır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int feclearexcept(  
   int excepts  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `excepts`  
 Temizlemek için özel durum bayraklar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Sıfır verir `excepts` sıfır veya belirtilen tüm özel durumları başarıyla temizlendi. Aksi takdirde, sıfır olmayan bir değer döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 `feclearexcept` Noktası tarafından belirtilen özel durumu bayrakları kayan temizlemek için işlevi çalışır `excepts`. İşlev fenv.h içinde tanımlanan bu özel durum makroları destekler:  
  
|Özel durum makrosu|Açıklama|  
|---------------------|-----------------|  
|FE_DIVBYZERO|İçinde bir önceki kayan nokta işlemi singularity veya kutbu'na bir hata oluştu; sonsuz değerle oluşturuldu.|  
|FE_INEXACT|İşlev, bir önceki kayan nokta işlemi depolanmış sonucu yuvarlanacak zorlandı.|  
|FE_INVALID|Daha önce bir kayan nokta işleminde bir etki alanı hatası oluştu.|  
|FE_OVERFLOW|Bir aralık hata oluştu; önceki bir kayan nokta işlemi sonuç gösterilemeyecek kadar büyüktü.|  
|FE_UNDERFLOW|Önceki bir kayan noktalı işlem sonucu tam duyarlık gösterilemeyecek kadar çok küçüktü; denormal değeri oluşturuldu.|  
|FE_ALLEXCEPT|Tüm Bitsel veya kayan nokta özel durumlar desteklenir.|  
  
 `excepts` Bağımsız değişkeni sıfır veya bir veya daha fazla desteklenen özel durum makroları Bitsel veya olabilir. Herhangi bir bağımsız değişken değeri sonucunu tanımlanmamıştır.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|C üstbilgisi|C++ üstbilgi|  
|--------------|--------------|------------------|  
|`feclearexcept`|\<fenv.h >|\<cfenv>|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Alfabetik işlev başvurusu](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fetestexcept](../../c-runtime-library/reference/fetestexcept1.md)