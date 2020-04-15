---
title: _ismbbkalnum, _ismbbkalnum_l
ms.date: 4/2/2020
api_name:
- _ismbbkalnum
- _ismbbkalnum_l
- _o__ismbbkalnum
- _o__ismbbkalnum_l
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _ismbbkalnum
- ismbbkalnum
- ismbbkalnum_l
- _ismbbkalnum_l
helpviewer_keywords:
- _ismbbkalnum_l function
- ismbbkalnum_l function
- _ismbbkalnum function
- ismbbkalnum function
ms.assetid: e1d70e7b-29d0-469c-9d93-442b99de22ac
ms.openlocfilehash: 936a7708a824ac6e9e8a07b34bbdb9a3b9e761ff
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343670"
---
# <a name="_ismbbkalnum-_ismbbkalnum_l"></a>_ismbbkalnum, _ismbbkalnum_l

Belirli bir çok bayt karakterin ASCII olmayan bir metin simgesi olup olmadığını belirler.

## <a name="syntax"></a>Sözdizimi

```C
int _ismbbkalnum(
   unsigned int c
);
int _ismbbkalnum_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*C*<br/>
İnteger test edilecek.

*Yerel ayar*<br/>
Kullanılacak yerel yer.

## <a name="return-value"></a>Dönüş Değeri

**_ismbbkalnum,** tamsayı *c* noktalama işareti dışında ASCII olmayan bir metin simgesiyse sıfır olmayan bir değer veya değilse 0 değeri döndürür. **_ismbbkalnum,** yerel e-iş bağımlı karakter bilgileri için geçerli yerel alanı kullanır. **_ismbbkalnum_l,** yerel alanı parametre olarak alması dışında **_ismbbkalnum** ile aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_ismbbkalnum**|\<mbctype.h>|
|**_ismbbkalnum_l**|\<mbctype.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Bayt Sınıflandırması](../../c-runtime-library/byte-classification.md)<br/>
[_ismbb Rutinleri](../../c-runtime-library/ismbb-routines.md)<br/>
