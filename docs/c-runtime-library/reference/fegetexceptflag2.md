---
title: fegetexceptflag | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- fegetexceptflag
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
- fegetexceptflag
- fenv/fegetexceptflag
dev_langs:
- C++
helpviewer_keywords:
- fegetexceptflag function
ms.assetid: 2d28f0ca-70c9-4cff-be8b-3d876eacde71
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: baccf3f32381568472bd4d0d5f37d434ca789fc8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="fegetexceptflag"></a>fegetexceptflag

Belirtilen kayan nokta özel durumu bayrakları geçerli durumunu saklar.

## <a name="syntax"></a>Sözdizimi

```C
int fegetexceptflag(
   fexcept_t* pstatus,
   int excepts
);

```

### <a name="parameters"></a>Parametreler

*pstatus*<br/>
Bir işaretçi bir **fexcept_t** tarafından belirtilen özel durum bayrakları geçerli değerlerini içeren nesne *excepts*.

*excepts*<br/>
Kayan nokta özel durumu bayrakları depolamak üzere *pstatus*.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa 0 döndürür. Aksi takdirde, sıfır olmayan bir değer döndürür.

## <a name="remarks"></a>Açıklamalar

**Fegetexceptflag** işlevi depolar tarafından belirtilen kayan nokta özel durumu bayrakları geçerli durumunu *excepts* içinde **fexcept_t** tarafından nesne işaret için *pstatus*.  *pstatus* geçerli bir işaret etmelidir **fexcept_t** nesne ya da sonraki davranış tanımlanmadı. **Fegetexceptflag** işlevi destekler tanımlanan bu özel durum makroları \<fenv.h >:

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
|**fegetexceptflag**|\<fenv.h >|\<cfenv >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[fesetexceptflag](fesetexceptflag2.md)<br/>
