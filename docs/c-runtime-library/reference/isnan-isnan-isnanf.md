---
title: isNaN, _isnan, _isnanf | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _isnan
- _isnanf
- isnan
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _isnan
- isnan
- math/isnan
- math/_isnan
- math/_isnanf
- _isnanf
dev_langs:
- C++
helpviewer_keywords:
- NAN (not a number)
- _isnan function
- IEEE floating-point representation
- Not a Number (NANs)
- isnan function
ms.assetid: 391fbc5b-89a4-4fba-997e-68f1131caf82
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6b8552f59bc0d49ebae0d4a534225af5d9f5facb
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="isnan-isnan-isnanf"></a>isNaN, _isnan, _isnanf

Testleri bir kayan nokta değer bir sayı (NAN) değil.

## <a name="syntax"></a>Sözdizimi

```C
int isnan(
   /* floating-point */ x
); /* C-only macro */

int _isnan(
   double x
);

int _isnanf(
   float x
); /* x64 only */

template <class T>
bool isnan(
   T x
) throw(); /* C++ only */
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Test etmek için kayan nokta değeri.

## <a name="return-value"></a>Dönüş Değeri

C, **isnan** makrosu ve **_isnan** ve **_isnanf** İşlevler, sıfır olmayan bir değer döndürür bağımsız değişkeni *x* bir NAN olup; Aksi halde bunlar 0 döndürür.

C++ ' ta **isnan** şablon işlevleri return **true** , bağımsız değişkeni *x* NAN; olup aksi döndürmeleri **false**.

## <a name="remarks"></a>Açıklamalar

C **isnan** makrosu ve **_isnan** ve **_isnanf** işlevleri sınama kayan nokta değeri *x*, sıfır olmayan bir değer varsa döndürme *x* olmayan bir sayı (NAN) değeri. Belirtilen tür için IEEE 754 kayan nokta biçiminde bir kayan noktalı işlem sonucunu temsil edilemeyen bir NAN oluşturulur. Bir NAN çıktı için nasıl temsil hakkında daha fazla bilgi için bkz: [printf](printf-printf-l-wprintf-wprintf-l.md).

C++ derlendiğinde **isnan** makrosu tanımlı değil ve bir **isnan** şablon işlevi yerine tanımlanır. Türünde bir değer döndürür **bool** yerine bir tamsayı.

**_İsnan** ve **_isnanf** Microsoft belirli işlevlerdir. **_İsnanf** işlevidir yalnızca x64 için derlenmiş olduğunda kullanılabilir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli üstbilgisi (C)|Gerekli üstbilgisi (C++)|
|-------------|---------------------------|-------------------------------|
|**isNaN**, **_isnanf**|\<Math.h >|\<Math.h > veya \<cmath >|
|**_isnan**|\<float.h >|\<float.h > veya \<cfloat >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[_finite, _finitef](finite-finitef.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
