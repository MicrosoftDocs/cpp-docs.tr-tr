---
title: fetestexcept
ms.date: 04/05/2018
apiname:
- fetestexcept
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
- fetestexcept
- fenv/fetestexcept
helpviewer_keywords:
- fetestexept function
ms.assetid: ca4dc43f-5573-440d-bc19-ead7571b13dc
ms.openlocfilehash: ed75ab0ff13029f6ec10c1aafbcb7f7b23b46fd6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62334171"
---
# <a name="fetestexcept"></a>fetestexcept

Belirtilen bir kayan nokta özel durumu bayrakları hangisinin şu anda ayarlanmış belirler.

## <a name="syntax"></a>Sözdizimi

```C
int fetestexcept(
   int excepts
);
```

### <a name="parameters"></a>Parametreler

*excepts*<br/>
Test etmek için bir bit seviyesinde veya kayan nokta durumu bayrakları.

## <a name="return-value"></a>Dönüş Değeri

Başarı, özel durum durumu bayrakları için şu anda karşılık gelen kayan nokta özel durum makroları bir bit düzeyinde OR içeren bit maskesi döndürür ayarlayın. Özel durumların yok ise 0 döndürür ayarlanır.

## <a name="remarks"></a>Açıklamalar

Bir kayan hangi özel durumları ortaya çıktı belirlemek için fetestexcept işlevini nokta işlemi. Kullanım *excepts* test etmek için hangi özel durum durumu bayrakları belirtmek için parametre. **Fetestexcept** işlevi kullanır bu özel durum makroları tanımlanan \<fenv.h > içinde *excepts* ve dönüş değeri:

|Özel durum makrosu|Açıklama|
|---------------------|-----------------|
|FE_DIVBYZERO|Daha önce bir kayan nokta işleminde singularity ya da kutup bir hata oluştu; sonsuz değerle oluşturulur.|
|FE_INEXACT|İşlevi, bir önceki kayan noktalı işlemin depolanmış sonucu yuvarlanacak zorlandı.|
|FE_INVALID|Daha önce bir kayan nokta işleminde bir etki alanı hatası oluştu.|
|FE_OVERFLOW|Aralık bir hata oluştu; önceki bir kayan noktalı işlemin sonucu gösterilemeyecek kadar büyüktü.|
|FE_UNDERFLOW|Önceki bir kayan noktalı işlemin sonucu tam duyarlıklı gösterilemeyecek kadar çok küçük; denormal değer oluşturuldu.|
|FE_ALLEXCEPT|Bit düzeyinde OR tüm kayan nokta özel durumları desteklenmiyor.|

Belirtilen *excepts* bağımsız değişkeni 0, desteklenen bir kayan nokta özel durum makroları veya bit ya da iki veya daha fazla makroları olabilir. Diğer etkisini *excepts* bağımsız değişken değeri tanımsızdır.

Bu işlevi kullanmak için erişim kullanarak engelleyebilir kayan nokta iyileştirmelerinin kapatmanız gerekir `#pragma fenv_access(on)` çağrıdan önceki yönerge. Daha fazla bilgi için [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üst bilgisi|
|--------------|--------------|------------------|
|**fetestexcept**|\<fenv.h >|\<cfenv >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[feclearexcept](feclearexcept1.md)<br/>
[feraiseexcept](feraiseexcept.md)<br/>
