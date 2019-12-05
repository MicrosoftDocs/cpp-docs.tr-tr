---
title: feraiseexcept
ms.date: 04/05/2018
api_name:
- feraiseexcept
api_location:
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
api_type:
- HeaderDef
f1_keywords:
- feraiseexcept
- fenv/feraiseexcept
helpviewer_keywords:
- feraiseexcept function
ms.assetid: 87e89151-83c2-4563-9a9a-45666245d437
ms.openlocfilehash: 07c8a79e0a9569db80607e1ec1e16cd4b502783c
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857833"
---
# <a name="feraiseexcept"></a>feraiseexcept

Belirtilen kayan nokta özel durumlarını yükseltir.

## <a name="syntax"></a>Sözdizimi

```C
int feraiseexcept(
   int excepts
);
```

### <a name="parameters"></a>Parametreler

*hariç tutulan*<br/>
Tetiklemeli kayan nokta özel durumları.

## <a name="return-value"></a>Dönüş Değeri

Belirtilen tüm özel durumlar başarıyla harekete geçirilir, 0 döndürür.

## <a name="remarks"></a>Açıklamalar

**Feraiseexcept** işlevi, *hariç tutulan*tarafından belirtilen kayan nokta özel durumlarını oluşturmayı dener.   **Feraiseexcept** işlevi, \<fenv. h > tanımlanan bu özel durum makrolarını destekler:

|Özel durum makrosu|Açıklama|
|---------------------|-----------------|
|FE_DIVBYZERO|Daha önceki bir kayan nokta işleminde singularor veya direk hatası oluştu; sonsuz değer oluşturuldu.|
|FE_INEXACT|İşlev, önceki bir kayan nokta işleminin saklı sonucunu yuvarlamak üzere zorlandı.|
|FE_INVALID|Önceki kayan nokta işleminde bir etki alanı hatası oluştu.|
|FE_OVERFLOW|Bir Aralık hatası oluştu; daha önceki bir kayan nokta işlem sonucu gösterilemeyecek kadar büyüktü.|
|FE_UNDERFLOW|Daha önceki bir kayan nokta işlem sonucu tam duyarlıkta gösterilemeyecek kadar küçük; bir denormal değeri oluşturuldu.|
|FE_ALLEXCEPT|Desteklenen tüm kayan nokta özel durumlarının bit düzeyinde veya dışında.|

*Hariç tutulan* bağımsız değişken sıfır, özel durum makrosu değerlerinden biri ya da desteklenen özel durum makrolarının BIT seviyesinde veya iki ya da daha fazlası olabilir. Belirtilen özel durum makrolarından biri FE_OVERFLOW veya FE_UNDERFLOW, FE_INEXACT özel durumu bir yan etkisi olarak ortaya çıkabilir.

Bu işlevi kullanmak için, çağrıdan önce `#pragma fenv_access(on)` yönergesini kullanarak erişimi engelleyebilecek kayan nokta iyileştirmelerini kapatmanız gerekir. Daha fazla bilgi için bkz. [fenv_access](../../preprocessor/fenv-access.md).

**Microsoft 'a özgü:** *Hariç tutulan* ' de belirtilen özel durumlar sırasıyla FE_INVALID, FE_DIVBYZERO, FE_OVERFLOW, FE_UNDERFLOW, FE_INEXACT olarak oluşturulur. Ancak, FE_OVERFLOW veya FE_UNDERFLOW başlatıldığında, *hariç tutulan*' de belirtilmese bile FE_INEXACT oluşturulabilir.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++üst bilgi|
|--------------|--------------|------------------|
|*feraiseexcept*|\<fenv. h >|\<cfenv >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[fesetexceptflag](fesetexceptflag2.md)<br/>
[feholdexcept](feholdexcept2.md)<br/>
[fetestexcept](fetestexcept1.md)<br/>
[feupdateenv](feupdateenv.md)<br/>
