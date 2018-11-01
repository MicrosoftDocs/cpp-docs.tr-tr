---
title: fegetexceptflag
ms.date: 04/05/2018
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
helpviewer_keywords:
- fegetexceptflag function
ms.assetid: 2d28f0ca-70c9-4cff-be8b-3d876eacde71
ms.openlocfilehash: 8dc82f6ee054dc3d0f86055cb63da1fc63c79a8b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50605484"
---
# <a name="fegetexceptflag"></a>fegetexceptflag

Belirtilen kayan nokta özel durumu bayrakları geçerli durumunu depolar.

## <a name="syntax"></a>Sözdizimi

```C
int fegetexceptflag(
   fexcept_t* pstatus,
   int excepts
);

```

### <a name="parameters"></a>Parametreler

*pstatus*<br/>
Bir işaretçi bir **fexcept_t** nesnesi tarafından belirtilen özel durum bayrakların geçerli değerler içerecek şekilde *excepts*.

*excepts*<br/>
Depolamak için kayan nokta özel durumu bayrakları *pstatus*.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa 0 döndürür. Aksi takdirde, sıfır olmayan bir değer döndürür.

## <a name="remarks"></a>Açıklamalar

**Fegetexceptflag** işlevi kayan nokta özel durum durumu bayrakları tarafından belirtilen geçerli durumunu depolar *excepts* içinde **fexcept_t** nesne tarafından işaret edilen *pstatus*.  *pstatus* geçerli bir işaret etmelidir **fexcept_t** nesne veya sonraki davranışı tanımsızdır. **Fegetexceptflag** işlevini desteklemektedir tanımlanan bu özel durum makroları \<fenv.h >:

|Özel durum makrosu|Açıklama|
|---------------------|-----------------|
|FE_DIVBYZERO|Daha önce bir kayan nokta işleminde singularity ya da kutup bir hata oluştu; sonsuz değerle oluşturulur.|
|FE_INEXACT|İşlevi, bir önceki kayan noktalı işlemin depolanmış sonucu yuvarlanacak zorlandı.|
|FE_INVALID|Daha önce bir kayan nokta işleminde bir etki alanı hatası oluştu.|
|FE_OVERFLOW|Aralık bir hata oluştu; önceki bir kayan noktalı işlemin sonucu gösterilemeyecek kadar büyüktü.|
|FE_UNDERFLOW|Önceki bir kayan noktalı işlemin sonucu tam duyarlıklı gösterilemeyecek kadar çok küçük; denormal değer oluşturuldu.|
|FE_ALLEXCEPT|Bit düzeyinde OR tüm kayan nokta özel durumları desteklenmiyor.|

*Excepts* sıfır bağımsız değişken olabilir desteklenen kayan nokta özel durum makroları veya bit ya da iki veya daha fazla makroları. Herhangi bir bağımsız değişken değeri etkisini tanımsızdır.

Bu işlevi kullanmak için erişim kullanarak engelleyebilir kayan nokta iyileştirmelerinin kapatmanız gerekir `#pragma fenv_access(on)` çağrıdan önceki yönerge. Daha fazla bilgi için [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üst bilgisi|
|--------------|--------------|------------------|
|**fegetexceptflag**|\<fenv.h >|\<cfenv >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[fesetexceptflag](fesetexceptflag2.md)<br/>
