---
title: _ismbbkpunct, _ismbbkpunct_l
ms.date: 11/04/2016
api_name:
- _ismbbkpunct_l
- _ismbbkpunct
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
- ismbbkpunct_l
- _ismbbkpunct_l
- ismbbkpunct
- _ismbbkpunct
helpviewer_keywords:
- _ismbbkpunct_l function
- ismbbkpunct_l function
- ismbbkpunct function
- _ismbbkpunct function
ms.assetid: a04c59cd-5ca7-4296-bec0-2b0d7f04edd0
ms.openlocfilehash: 35f09013fbbe522a1eb747f2d2131a5fbb23f765
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70954084"
---
# <a name="_ismbbkpunct-_ismbbkpunct_l"></a>_ismbbkpunct, _ismbbkpunct_l

Çok baytlı bir karakterin bir noktalama karakteri olup olmadığını denetler.

## <a name="syntax"></a>Sözdizimi

```C
int _ismbbkpunct(
   unsigned int c
);
int _ismbbkpunct_l(
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

**_ismbbkpunct** , tamsayı *c* ASCII olmayan bir noktalama sembolse veya değilse 0 dışında bir değer döndürür. Örneğin, yalnızca kod sayfası 932 ' de, Katakana noktalama işaretleri için **_ismbbkpunct** testleri. **_ismbbkpunct** , yerel ayara bağımlı karakter ayarları için geçerli yerel ayarı kullanır. **_ismbbkpunct_l** , geçirilen yerel ayarı kullanması dışında aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_ismbbkpunct**|\<Mbctype. h >|
|**_ismbbkpunct_l**|\<Mbctype. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bayt Sınıflandırması](../../c-runtime-library/byte-classification.md)<br/>
[_ismbb Yordamları](../../c-runtime-library/ismbb-routines.md)<br/>
