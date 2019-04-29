---
title: fesetexceptflag
ms.date: 04/05/2018
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
helpviewer_keywords:
- fesetexceptflag function
ms.assetid: 2f7dad77-9e54-4097-a3e3-35176ace4de5
ms.openlocfilehash: 9ac79e790f0b1e7a89413a0d4974f6053c95616e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62334001"
---
# <a name="fesetexceptflag"></a>fesetexceptflag

Kayan nokta geçerli ortamda belirtilen bir kayan nokta durumu bayrakları ayarlar.

## <a name="syntax"></a>Sözdizimi

```C
int fesetexceptflag(
     const fexcept_t *pstatus,
     int excepts
);
```

### <a name="parameters"></a>Parametreler

*pstatus*<br/>
İşaretçi bir **fexcept_t** özel durumu bayrakları ayarlanmış değerleri içeren nesne. Nesne için bir çağrı tarafından ayarlanabilir [fegetexceptflag](fegetexceptflag2.md).

*excepts*<br/>
Kayan nokta özel durum durumu ayarlamak için bayrakları.

## <a name="return-value"></a>Dönüş Değeri

Belirtilen özel durumu bayrakları başarılı bir şekilde ayarlarsanız, 0 döndürür. Aksi takdirde, sıfır olmayan bir değer döndürür.

## <a name="remarks"></a>Açıklamalar

**Fesetexceptflag** işlevi tarafından belirtilen kayan nokta özel durum durumu bayrakları durumuna ayarlar *excepts* kümesindeki karşılık gelen değerlere **fexcept_t** nesne tarafından işaret edilen *pstatus*.  Özel durum oluşturmaz. *Pstatus* işaretçi işaret etmelidir geçerli bir **fexcept_t** nesne veya sonraki davranışı tanımsızdır. **Fesetexceptflag** işlevi destekler, bu özel durum makrosu değerleri *excepts*içinde tanımlanmış \<fenv.h >:

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
|**fesetexceptflag**|\<fenv.h >|\<cfenv >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[fegetexceptflag](fegetexceptflag2.md)<br/>
