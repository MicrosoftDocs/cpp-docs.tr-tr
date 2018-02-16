---
title: fesetexceptflag2 | Microsoft Docs
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
- fesetexceptflag
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
- fesetexceptflag
- fenv/fesetexceptflag
dev_langs:
- C++
helpviewer_keywords:
- fesetexceptflag function
ms.assetid: 2f7dad77-9e54-4097-a3e3-35176ace4de5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 24aff3007d88f9ae5ebc30811e652284ecebeba5
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="fesetexceptflag"></a>fesetexceptflag
Belirtilen kayan nokta durumu bayrakları geçerli kayan nokta ortamında ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int fesetexceptflag(  
     const fexcept_t *pstatus,  
     int excepts  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pstatus`  
 İşaretçi bir `fexcept_t` özel durumu bayrakları ayarlamak için değerleri içeren nesne. Nesne için önceki bir çağrı tarafından ayarlanabilir [fegetexceptflag](fegetexceptflag2.md).  
  
 `excepts`  
 Kayan nokta özel durumu ayarlamak için bayraklar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Tüm belirtilen özel durumu bayrakları başarılı bir şekilde ayarlarsanız, 0 döndürür. Aksi takdirde, sıfır olmayan bir değer döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 `fesetexceptflag` İşlevi tarafından belirtilen kayan nokta özel durumu bayrakları durumunu ayarlar `excepts` kümesinde karşılık gelen değerler için `fexcept_t` tarafından için nesne işaret `pstatus`.  Özel durumları oluşturmaz. `pstatus` İşaretçi işaret etmelidir geçerli bir `fexcept_t` nesne ya da sonraki davranış tanımlanmadı. `fesetexceptflag` İşlevi destekler bu özel durum makrosu değerleri `excepts`, içinde tanımlı \<fenv.h >:  
  
|Özel durum makrosu|Açıklama|  
|---------------------|-----------------|  
|FE_DIVBYZERO|İçinde bir önceki kayan nokta işlemi singularity veya kutbu'na bir hata oluştu; sonsuz değerle oluşturuldu.|  
|FE_INEXACT|İşlev, bir önceki kayan nokta işlemi depolanmış sonucu yuvarlanacak zorlandı.|  
|FE_INVALID|Daha önce bir kayan nokta işleminde bir etki alanı hatası oluştu.|  
|FE_OVERFLOW|Bir aralık hata oluştu; önceki bir kayan nokta işlemi sonuç gösterilemeyecek kadar büyüktü.|  
|FE_UNDERFLOW|Önceki bir kayan noktalı işlem sonucu tam duyarlık gösterilemeyecek kadar çok küçüktü; denormal değeri oluşturuldu.|  
|FE_ALLEXCEPT|Tüm Bitsel veya kayan nokta özel durumlar desteklenir.|  
  
 `excepts` Bağımsız değişkeni sıfır olabilir bir desteklenen kayan nokta özel durum makroları veya Bitsel veya iki veya daha fazla makrolar. Herhangi bir bağımsız değişken değeri etkisini tanımlanmamıştır.  
  
 Bu işlevi kullanmak için erişim kullanarak önleyebilir kayan nokta iyileştirmeler kapatmanız gerekir `#pragma fenv_access(on)` çağrı önce yönergesi. Daha fazla bilgi için bkz: [fenv_access](../../preprocessor/fenv-access.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|C üstbilgisi|C++ üstbilgi|  
|--------------|--------------|------------------|  
|`fesetexceptflag`|\<fenv.h >|\<cfenv>|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Alfabetik işlev başvurusu](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fegetexceptflag](../../c-runtime-library/reference/fegetexceptflag2.md)