---
description: 'Daha fazla bilgi edinin: fegetexceptflag'
title: fegetexceptflag
ms.date: 04/05/2018
api_name:
- fegetexceptflag
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
- fegetexceptflag
- fenv/fegetexceptflag
helpviewer_keywords:
- fegetexceptflag function
ms.assetid: 2d28f0ca-70c9-4cff-be8b-3d876eacde71
ms.openlocfilehash: 9690263168c9eef46b5a8b684fa00dfd9d6f8715
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322569"
---
# <a name="fegetexceptflag"></a>fegetexceptflag

Belirtilen kayan nokta özel durum bayraklarının geçerli durumunu depolar.

## <a name="syntax"></a>Sözdizimi

```C
int fegetexceptflag(
   fexcept_t* pstatus,
   int excepts
);
```

### <a name="parameters"></a>Parametreler

*pStatus*<br/>
**Fexcept_t** nesnesine yönelik bir işaretçi, *hariç tutulan* tarafından belirtilen özel durum bayraklarının geçerli değerlerini içerir.

*hariç tutulan*<br/>
*PStatus* içinde depolanacak kayan nokta özel durum bayrakları.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda 0 döndürür. Aksi takdirde, sıfır olmayan bir değer döndürür.

## <a name="remarks"></a>Açıklamalar

**Fegetexceptflag** işlevi, *pStatus* tarafından işaret edilen **fexcept_t** nesnesindeki *exceptler* tarafından belirtilen kayan nokta özel durum bayraklarının geçerli durumunu depolar.  *pStatus* geçerli bir **fexcept_t** nesnesine işaret etmelidir ya da sonraki davranış tanımsızdır. **Fegetexceptflag** işlevi, içinde tanımlanan bu özel durum makrolarını destekler \<fenv.h> :

|Özel durum makrosu|Açıklama|
|---------------------|-----------------|
|FE_DIVBYZERO|Daha önceki bir kayan nokta işleminde singularor veya direk hatası oluştu; sonsuz değer oluşturuldu.|
|FE_INEXACT|İşlev, önceki bir kayan nokta işleminin saklı sonucunu yuvarlamak üzere zorlandı.|
|FE_INVALID|Önceki kayan nokta işleminde bir etki alanı hatası oluştu.|
|FE_OVERFLOW|Bir Aralık hatası oluştu; daha önceki bir kayan nokta işlem sonucu gösterilemeyecek kadar büyüktü.|
|FE_UNDERFLOW|Daha önceki bir kayan nokta işlem sonucu tam duyarlıkta gösterilemeyecek kadar küçük; bir denormal değeri oluşturuldu.|
|FE_ALL_EXCEPT|Desteklenen tüm kayan nokta özel durumlarının bit düzeyinde veya dışında.|

*Hariç tutulan* bağımsız değişken sıfır, desteklenen kayan nokta özel durumu makrolarından biri veya iki ya da daha fazla makronun BIT düzeyinde ya da daha fazlası olabilir. Diğer bağımsız değişken değerinin etkisi tanımsızdır.

Bu işlevi kullanmak için, çağrıdan önce yönergesini kullanarak erişimi engelleyebilecek kayan nokta iyileştirmelerini kapatmanız gerekir `#pragma fenv_access(on)` . Daha fazla bilgi için bkz. [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üstbilgisi|
|--------------|--------------|------------------|
|**fegetexceptflag**|\<fenv.h>|\<cfenv>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[fesetexceptflag](fesetexceptflag2.md)<br/>
