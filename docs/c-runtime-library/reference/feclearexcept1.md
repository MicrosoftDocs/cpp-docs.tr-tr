---
title: feclearexcept1
ms.date: 04/05/2018
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
helpviewer_keywords:
- feclearexcept function
ms.assetid: ef419da3-c248-4432-b53c-8e7a475d9533
ms.openlocfilehash: 3c2f037a5be903fc006debfa7319c483431fdd92
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62334742"
---
# <a name="feclearexcept"></a>feclearexcept

Bağımsız değişkeni tarafından belirtilen kayan nokta özel durumu bayrakları sıfırlamaya çalışır.

## <a name="syntax"></a>Sözdizimi

```C
int feclearexcept(
   int excepts
);
```

### <a name="parameters"></a>Parametreler

*excepts*<br/>
Özel durum durumu sıfırlamaya bayraklar.

## <a name="return-value"></a>Dönüş Değeri

Sıfır döndürür *excepts* sıfır veya belirtilen tüm özel durumları başarıyla temizlendi. Aksi takdirde, sıfır olmayan bir değer döndürür.

## <a name="remarks"></a>Açıklamalar

**Feclearexcept** noktası tarafından belirtilen özel durum durumu bayrakları kayan temizlemek için işlevi çalışır *excepts*. İşlev fenv.h içinde tanımlanan bu özel durum makroları destekler:

|Özel durum makrosu|Açıklama|
|---------------------|-----------------|
|FE_DIVBYZERO|Daha önce bir kayan nokta işleminde singularity ya da kutup bir hata oluştu; sonsuz değerle oluşturulur.|
|FE_INEXACT|İşlevi, bir önceki kayan noktalı işlemin depolanmış sonucu yuvarlanacak zorlandı.|
|FE_INVALID|Daha önce bir kayan nokta işleminde bir etki alanı hatası oluştu.|
|FE_OVERFLOW|Aralık bir hata oluştu; önceki bir kayan noktalı işlemin sonucu gösterilemeyecek kadar büyüktü.|
|FE_UNDERFLOW|Önceki bir kayan noktalı işlemin sonucu tam duyarlıklı gösterilemeyecek kadar çok küçük; denormal değer oluşturuldu.|
|FE_ALL_EXCEPT|Bit düzeyinde OR tüm kayan nokta özel durumları desteklenmiyor.|

*Excepts* bağımsız değişkeni sıfır veya bir veya daha fazla desteklenen özel durum makroları, bit düzeyinde OR olabilir. Herhangi bir bağımsız değişken değeri, sonuç tanımsızdır.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üst bilgisi|
|--------------|--------------|------------------|
|**feclearexcept**|\<fenv.h >|\<cfenv >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[fetestexcept](fetestexcept1.md)<br/>
