---
title: _ismbbtrail, _ismbbtrail_l
ms.date: 11/04/2016
api_name:
- _ismbbtrail
- _ismbbtrail_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _ismbbtrail
- ismbbtrail
- _ismbbtrail_l
- ismbbtrail_l
helpviewer_keywords:
- ismbbtrail_l function
- _ismbbtrail function
- _ismbbtrail_l function
- ismbbtrail function
ms.assetid: dfdd0292-960b-4c1d-bf11-146e0fc80247
ms.openlocfilehash: e445de41b05ac4829bdf108d1c98113cd5240ec0
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70953966"
---
# <a name="_ismbbtrail-_ismbbtrail_l"></a>_ismbbtrail, _ismbbtrail_l

Bir baytın çok baytlı bir karakterin sondaki baytı olup olmadığını belirler.

## <a name="syntax"></a>Sözdizimi

```C
int _ismbbtrail(
   unsigned int c
);
int _ismbbtrail_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*c*<br/>
Sınanacak tamsayı.

*ayarlar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**_ısmbbtram** , bir çok baytlı karakterin ikinci *baytı ise sıfır* dışında bir değer döndürür. Örneğin, yalnızca kod sayfası 932 ' de geçerli aralıklar 0x40 ile 0x7E ve 0x80 ile 0xFC arasındadır.

## <a name="remarks"></a>Açıklamalar

**_ismbbiz** , yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır. **_ismbbtrail_l** , bunun yerine geçirilen yerel ayarı kullanması dışında aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_ismbbiz**|\<Mbctype. h > veya \<mbstring. h >|\<CType. h >, * \<limit. h >, \<Stdlib. h >|
|**_ismbbtrail_l**|\<Mbctype. h > veya \<mbstring. h >|\<CType. h >, * \<limit. h >, \<Stdlib. h >|

\*Test koşullarına yönelik bildirim sabitleri için.

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bayt Sınıflandırması](../../c-runtime-library/byte-classification.md)<br/>
[_ismbb Yordamları](../../c-runtime-library/ismbb-routines.md)<br/>
