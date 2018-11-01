---
title: feraiseexcept
ms.date: 04/05/2018
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
helpviewer_keywords:
- feraiseexcept function
ms.assetid: 87e89151-83c2-4563-9a9a-45666245d437
ms.openlocfilehash: 581dd4026a20ce7221945c5815af3ae102f132fa
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50532255"
---
# <a name="feraiseexcept"></a>feraiseexcept

Belirtilen kayan nokta özel durumlarını oluşturur.

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

Belirtilen tüm özel durumlar başarıyla oluşturuldu, 0 döndürür.

## <a name="remarks"></a>Açıklamalar

**Feraiseexcept** işlevi tarafından belirtilen kayan nokta özel durumlarını yükseltmek girişimlerini *excepts*.   **Feraiseexcept** işlevini desteklemektedir tanımlanan bu özel durum makroları \<fenv.h >:

|Özel durum makrosu|Açıklama|
|---------------------|-----------------|
|FE_DIVBYZERO|Daha önce bir kayan nokta işleminde singularity ya da kutup bir hata oluştu; sonsuz değerle oluşturulur.|
|FE_INEXACT|İşlevi, bir önceki kayan noktalı işlemin depolanmış sonucu yuvarlanacak zorlandı.|
|FE_INVALID|Daha önce bir kayan nokta işleminde bir etki alanı hatası oluştu.|
|FE_OVERFLOW|Aralık bir hata oluştu; önceki bir kayan noktalı işlemin sonucu gösterilemeyecek kadar büyüktü.|
|FE_UNDERFLOW|Önceki bir kayan noktalı işlemin sonucu tam duyarlıklı gösterilemeyecek kadar çok küçük; denormal değer oluşturuldu.|
|FE_ALLEXCEPT|Bit düzeyinde OR tüm kayan nokta özel durumları desteklenmiyor.|

*Excepts* sıfır bağımsız değişken olabilir özel durum makrosu değerleri veya bit ya da iki veya daha fazla desteklenen özel durum makroları. Belirtilen özel durum makroları FE_OVERFLOW veya FE_UNDERFLOW ise, bir yan etkisi olarak FE_INEXACT özel duruma neden.

Bu işlevi kullanmak için erişim kullanarak engelleyebilir kayan nokta iyileştirmelerinin kapatmanız gerekir `#pragma fenv_access(on)` çağrıdan önceki yönerge. Daha fazla bilgi için [fenv_access](../../preprocessor/fenv-access.md).

**Microsoft Specific:** belirtilen özel durumları *excepts* FE_INVALID, sırayla gerçekleştirilen FE_DIVBYZERO, FE_OVERFLOW, FE_UNDERFLOW, FE_INEXACT. FE_OVERFLOW veya FE_UNDERFLOW ortaya çıktığında, Bununla birlikte, FE_INEXACT içinde belirtilmemiş olsa bile yükseltilebilir *excepts*. **End Microsoft özgü**

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üst bilgisi|
|--------------|--------------|------------------|
|*feraiseexcept*|\<fenv.h >|\<cfenv >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[fesetexceptflag](fesetexceptflag2.md)<br/>
[feholdexcept](feholdexcept2.md)<br/>
[fetestexcept](fetestexcept1.md)<br/>
[feupdateenv](feupdateenv.md)<br/>
