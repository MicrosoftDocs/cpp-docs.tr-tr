---
title: fetestexcept | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- fetestexept function
ms.assetid: ca4dc43f-5573-440d-bc19-ead7571b13dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0450fcaddf8ca05484d0b2bd122ff006eb8355f1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="fetestexcept"></a>fetestexcept

Belirtilen kayan nokta özel durumu bayrakları hangisinin şu anda ayarlanmış belirler.

## <a name="syntax"></a>Sözdizimi

```C
int fetestexcept(
   int excepts
);

```

### <a name="parameters"></a>Parametreler

*excepts*<br/>
Test etmek için bir Bitsel veya kayan nokta durum bayrakları.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa bir özel durum bayrakları şu anda karşılık kayan nokta özel durum makroları Bitsel veya içeren bit maskesi döndürür ayarlayın. Özel durumlar hiçbiri 0 döndürür ayarlanır.

## <a name="remarks"></a>Açıklamalar

Bir kayan hangi özel durumları ortaya çıktı belirlemek için fetestexcept işlevini nokta işlemi. Kullanım *excepts* sınamak için hangi özel durumu bayrakları belirtmek için parametre. **Fetestexcept** işlevini kullanan tanımlanan bu özel durum makroları \<fenv.h > içinde *excepts* ve dönüş değeri:

|Özel durum makrosu|Açıklama|
|---------------------|-----------------|
|FE_DIVBYZERO|İçinde bir önceki kayan nokta işlemi singularity veya kutbu'na bir hata oluştu; sonsuz değerle oluşturuldu.|
|FE_INEXACT|İşlev, bir önceki kayan nokta işlemi depolanmış sonucu yuvarlanacak zorlandı.|
|FE_INVALID|Daha önce bir kayan nokta işleminde bir etki alanı hatası oluştu.|
|FE_OVERFLOW|Bir aralık hata oluştu; önceki bir kayan nokta işlemi sonuç gösterilemeyecek kadar büyüktü.|
|FE_UNDERFLOW|Önceki bir kayan noktalı işlem sonucu tam duyarlık gösterilemeyecek kadar çok küçüktü; denormal değeri oluşturuldu.|
|FE_ALLEXCEPT|Tüm Bitsel veya kayan nokta özel durumlar desteklenir.|

Belirtilen *excepts* bağımsız değişkeni bir desteklenen kayan nokta özel durum makroları veya Bitsel veya iki veya daha fazla makrolar 0 olabilir. Diğer etkisini *excepts* bağımsız değişken değeri tanımlanmadı.

Bu işlevi kullanmak için erişim kullanarak önleyebilir kayan nokta iyileştirmeler kapatmanız gerekir `#pragma fenv_access(on)` çağrı önce yönergesi. Daha fazla bilgi için bkz: [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üstbilgi|
|--------------|--------------|------------------|
|**fetestexcept**|\<fenv.h >|\<cfenv >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[feclearexcept](feclearexcept1.md)<br/>
[feraiseexcept](feraiseexcept.md)<br/>
