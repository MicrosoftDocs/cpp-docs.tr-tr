---
title: feraiseexcept | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- feraiseexcept
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
apitype: HeaderDef
f1_keywords:
- feraiseexcept
- fenv/feraiseexcept
dev_langs:
- C++
helpviewer_keywords:
- feraiseexcept function
ms.assetid: 87e89151-83c2-4563-9a9a-45666245d437
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 93414d09b898212e3748c1de510796b401b6aa56
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="feraiseexcept"></a>feraiseexcept

Belirtilen kayan nokta özel durumları oluşturur.

## <a name="syntax"></a>Sözdizimi

```C
int feraiseexcept(
   int excepts
);
```

### <a name="parameters"></a>Parametreler

*excepts*<br/>
Yükseltmek için kayan nokta özel durumları.

## <a name="return-value"></a>Dönüş Değeri

Belirtilen tüm özel durumları başarıyla oluşturuldu, 0 döndürür.

## <a name="remarks"></a>Açıklamalar

**Feraiseexcept** işlevi çalışır tarafından belirtilen kayan nokta özel durumlar yükseltmek *excepts*.   **Feraiseexcept** işlevi destekler tanımlanan bu özel durum makroları \<fenv.h >:

|Özel durum makrosu|Açıklama|
|---------------------|-----------------|
|FE_DIVBYZERO|İçinde bir önceki kayan nokta işlemi singularity veya kutbu'na bir hata oluştu; sonsuz değerle oluşturuldu.|
|FE_INEXACT|İşlev, bir önceki kayan nokta işlemi depolanmış sonucu yuvarlanacak zorlandı.|
|FE_INVALID|Daha önce bir kayan nokta işleminde bir etki alanı hatası oluştu.|
|FE_OVERFLOW|Bir aralık hata oluştu; önceki bir kayan nokta işlemi sonuç gösterilemeyecek kadar büyüktü.|
|FE_UNDERFLOW|Önceki bir kayan noktalı işlem sonucu tam duyarlık gösterilemeyecek kadar çok küçüktü; denormal değeri oluşturuldu.|
|FE_ALLEXCEPT|Tüm Bitsel veya kayan nokta özel durumlar desteklenir.|

*Excepts* bağımsız değişkeni sıfır olabilir bir özel durum makrosu değerler veya Bitsel veya iki veya daha fazla desteklenen özel durum makroları. Belirtilen özel durum makroları FE_OVERFLOW veya FE_UNDERFLOW ise, FE_INEXACT özel durum yan etkisi olarak oluşturulabilir.

Bu işlevi kullanmak için erişim kullanarak önleyebilir kayan nokta iyileştirmeler kapatmanız gerekir `#pragma fenv_access(on)` çağrı önce yönergesi. Daha fazla bilgi için bkz: [fenv_access](../../preprocessor/fenv-access.md).

**Microsoft Specific:** belirtilen özel durum *excepts* FE_INVALID, sırayla gerçekleştirilen FE_DIVBYZERO, FE_OVERFLOW, FE_UNDERFLOW, FE_INEXACT. FE_OVERFLOW veya FE_UNDERFLOW oluştuğunda, ancak FE_INEXACT içinde belirtilmemiş olsa bile yükseltilebilir *excepts*. **Son Microsoft özel**

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üstbilgi|
|--------------|--------------|------------------|
|*feraiseexcept*|\<fenv.h >|\<cfenv >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[fesetexceptflag](fesetexceptflag2.md)<br/>
[feholdexcept](feholdexcept2.md)<br/>
[fetestexcept](fetestexcept1.md)<br/>
[feupdateenv](feupdateenv.md)<br/>
