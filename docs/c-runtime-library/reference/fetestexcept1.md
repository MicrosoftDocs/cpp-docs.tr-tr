---
title: fetestexcept
ms.date: 04/05/2018
api_name:
- fetestexcept
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
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- fetestexcept
- fenv/fetestexcept
helpviewer_keywords:
- fetestexept function
ms.assetid: ca4dc43f-5573-440d-bc19-ead7571b13dc
ms.openlocfilehash: e70ae1b74420b8186cccd8fc8a817423df618adf
ms.sourcegitcommit: ba4180a2d79d7e391f2f705797505d4aedbc2a5e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2020
ms.locfileid: "76972157"
---
# <a name="fetestexcept"></a>fetestexcept

Belirtilen kayan nokta özel durum durumu bayraklarının hangisinin geçerli olarak ayarlandığını belirler.

## <a name="syntax"></a>Sözdizimi

```C
int fetestexcept(
   int excepts
);
```

### <a name="parameters"></a>Parametreler

*hariç tutulan*<br/>
Test etmek için bir bit düzeyinde veya kayan nokta durum bayraklarının.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda, şu anda ayarlanmış olan özel durum bayraklarıyla karşılık gelen bir bit düzeyinde veya kayan nokta özel durum makroları içeren bir bit maskesi döndürür. Özel durumların hiçbiri ayarlanmamışsa 0 döndürür.

## <a name="remarks"></a>Açıklamalar

Bir kayan nokta işlemi tarafından hangi özel durumların ortaya çıkarılmadığını öğrenmek için fetestexcept işlevini kullanın. Sınanacak özel durum durumu bayraklarını belirtmek için *hariç tutulan* parametresini kullanın. **Fetestexcept** işlevi, *hariç tutulan* ve dönüş değerindeki \<fenv. h > içinde tanımlanan bu özel durum makrolarını kullanır:

|Özel durum makrosu|Açıklama|
|---------------------|-----------------|
|FE_DIVBYZERO|Daha önceki bir kayan nokta işleminde singularor veya direk hatası oluştu; sonsuz değer oluşturuldu.|
|FE_INEXACT|İşlev, önceki bir kayan nokta işleminin saklı sonucunu yuvarlamak üzere zorlandı.|
|FE_INVALID|Önceki kayan nokta işleminde bir etki alanı hatası oluştu.|
|FE_OVERFLOW|Bir Aralık hatası oluştu; daha önceki bir kayan nokta işlem sonucu gösterilemeyecek kadar büyüktü.|
|FE_UNDERFLOW|Daha önceki bir kayan nokta işlem sonucu tam duyarlıkta gösterilemeyecek kadar küçük; bir denormal değeri oluşturuldu.|
|FE_ALL_EXCEPT|Desteklenen tüm kayan nokta özel durumlarının bit düzeyinde veya dışında.|

Belirtilen *hariç tutulan* bağımsız değişken 0, desteklenen kayan nokta özel durumu makrolarından biri veya iki ya da daha fazla makronun BIT düzeyinde ya da daha fazlası olabilir. Diğer tüm *hariç tutulan* bağımsız değişken değerinin etkisi tanımsızdır.

Bu işlevi kullanmak için, çağrıdan önce `#pragma fenv_access(on)` yönergesini kullanarak erişimi engelleyebilecek kayan nokta iyileştirmelerini kapatmanız gerekir. Daha fazla bilgi için bkz. [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++üst bilgi|
|--------------|--------------|------------------|
|**fetestexcept**|\<fenv. h >|\<cfenv >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[feclearexcept](feclearexcept1.md)<br/>
[feraiseexcept](feraiseexcept.md)<br/>
