---
title: fesetexceptflag
ms.date: 04/05/2018
api_name:
- fesetexceptflag
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
- fesetexceptflag
- fenv/fesetexceptflag
helpviewer_keywords:
- fesetexceptflag function
ms.assetid: 2f7dad77-9e54-4097-a3e3-35176ace4de5
ms.openlocfilehash: b16de7ea54b5f1df21b6626febe773c8cef556f5
ms.sourcegitcommit: ba4180a2d79d7e391f2f705797505d4aedbc2a5e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2020
ms.locfileid: "76972139"
---
# <a name="fesetexceptflag"></a>fesetexceptflag

Geçerli kayan nokta ortamında belirtilen kayan nokta durum bayraklarını ayarlar.

## <a name="syntax"></a>Sözdizimi

```C
int fesetexceptflag(
     const fexcept_t *pstatus,
     int excepts
);
```

### <a name="parameters"></a>Parametreler

*pStatus*<br/>
Özel durum bayraklarını ayarlamak için değerleri içeren **fexcept_t** nesnesine yönelik işaretçi. Nesne, bir önceki [fegetexceptflag](fegetexceptflag2.md)çağrısıyla ayarlanabilir.

*hariç tutulan*<br/>
Ayarlanacak kayan nokta özel durum durumu bayrakları.

## <a name="return-value"></a>Dönüş Değeri

Belirtilen tüm özel durum bayrakları başarıyla ayarlandıysa, 0 döndürür. Aksi takdirde, sıfır dışında bir değer döndürür.

## <a name="remarks"></a>Açıklamalar

**Fesetexceptflag** işlevi, *hariç tutulan* tarafından belirtilen kayan nokta özel durum bayrakları durumunu, *pstatus*tarafından işaret edilen **fexcept_t** nesnesinde ayarlanan karşılık gelen değerlere ayarlar.  Özel durumları oluşturmaz. *PStatus* işaretçisinin geçerli bir **fexcept_t** nesnesine işaret olması veya sonraki davranışın tanımsız olması gerekir. **Fesetexceptflag** işlevi, \<fenv. h > içinde tanımlanan, *hariç tutulan*, bu özel durum makro değerlerini destekler:

|Özel durum makrosu|Açıklama|
|---------------------|-----------------|
|FE_DIVBYZERO|Daha önceki bir kayan nokta işleminde singularor veya direk hatası oluştu; sonsuz değer oluşturuldu.|
|FE_INEXACT|İşlev, önceki bir kayan nokta işleminin saklı sonucunu yuvarlamak üzere zorlandı.|
|FE_INVALID|Önceki kayan nokta işleminde bir etki alanı hatası oluştu.|
|FE_OVERFLOW|Bir Aralık hatası oluştu; daha önceki bir kayan nokta işlem sonucu gösterilemeyecek kadar büyüktü.|
|FE_UNDERFLOW|Daha önceki bir kayan nokta işlem sonucu tam duyarlıkta gösterilemeyecek kadar küçük; bir denormal değeri oluşturuldu.|
|FE_ALL_EXCEPT|Desteklenen tüm kayan nokta özel durumlarının bit düzeyinde veya dışında.|

*Hariç tutulan* bağımsız değişken sıfır, desteklenen kayan nokta özel durumu makrolarından biri veya iki ya da daha fazla makronun BIT düzeyinde ya da daha fazlası olabilir. Diğer bağımsız değişken değerinin etkisi tanımsızdır.

Bu işlevi kullanmak için, çağrıdan önce `#pragma fenv_access(on)` yönergesini kullanarak erişimi engelleyebilecek kayan nokta iyileştirmelerini kapatmanız gerekir. Daha fazla bilgi için bkz. [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++üst bilgi|
|--------------|--------------|------------------|
|**fesetexceptflag**|\<fenv. h >|\<cfenv >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[fegetexceptflag](fegetexceptflag2.md)<br/>
