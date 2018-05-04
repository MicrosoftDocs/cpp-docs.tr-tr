---
title: fesetexceptflag | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eef8ba1c91e6db4f0d620ef820a6487b3b17e649
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="fesetexceptflag"></a>fesetexceptflag

Belirtilen kayan nokta durumu bayrakları geçerli kayan nokta ortamında ayarlar.

## <a name="syntax"></a>Sözdizimi

```C
int fesetexceptflag(
     const fexcept_t *pstatus,
     int excepts
);
```

### <a name="parameters"></a>Parametreler

*pstatus*<br/>
İşaretçi bir **fexcept_t** özel durumu bayrakları ayarlamak için değerleri içeren nesne. Nesne için önceki bir çağrı tarafından ayarlanabilir [fegetexceptflag](fegetexceptflag2.md).

*excepts*<br/>
Kayan nokta özel durumu ayarlamak için bayraklar.

## <a name="return-value"></a>Dönüş Değeri

Tüm belirtilen özel durumu bayrakları başarılı bir şekilde ayarlarsanız, 0 döndürür. Aksi takdirde, sıfır olmayan bir değer döndürür.

## <a name="remarks"></a>Açıklamalar

**Fesetexceptflag** işlevi tarafından belirtilen kayan nokta özel durumu bayrakları durumunu ayarlar *excepts* kümesinde karşılık gelen değerler için **fexcept_t** tarafından için nesne işaret *pstatus*.  Özel durumları oluşturmaz. *Pstatus* işaretçi işaret etmelidir geçerli bir **fexcept_t** nesne ya da sonraki davranış tanımlanmadı. **Fesetexceptflag** işlevi destekler bu özel durum makrosu değerleri *excepts*, içinde tanımlı \<fenv.h >:

|Özel durum makrosu|Açıklama|
|---------------------|-----------------|
|FE_DIVBYZERO|İçinde bir önceki kayan nokta işlemi singularity veya kutbu'na bir hata oluştu; sonsuz değerle oluşturuldu.|
|FE_INEXACT|İşlev, bir önceki kayan nokta işlemi depolanmış sonucu yuvarlanacak zorlandı.|
|FE_INVALID|Daha önce bir kayan nokta işleminde bir etki alanı hatası oluştu.|
|FE_OVERFLOW|Bir aralık hata oluştu; önceki bir kayan nokta işlemi sonuç gösterilemeyecek kadar büyüktü.|
|FE_UNDERFLOW|Önceki bir kayan noktalı işlem sonucu tam duyarlık gösterilemeyecek kadar çok küçüktü; denormal değeri oluşturuldu.|
|FE_ALLEXCEPT|Tüm Bitsel veya kayan nokta özel durumlar desteklenir.|

*Excepts* bağımsız değişkeni sıfır olabilir bir desteklenen kayan nokta özel durum makroları veya Bitsel veya iki veya daha fazla makrolar. Herhangi bir bağımsız değişken değeri etkisini tanımlanmamıştır.

Bu işlevi kullanmak için erişim kullanarak önleyebilir kayan nokta iyileştirmeler kapatmanız gerekir `#pragma fenv_access(on)` çağrı önce yönergesi. Daha fazla bilgi için bkz: [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üstbilgi|
|--------------|--------------|------------------|
|**fesetexceptflag**|\<fenv.h >|\<cfenv >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[fegetexceptflag](fegetexceptflag2.md)<br/>
