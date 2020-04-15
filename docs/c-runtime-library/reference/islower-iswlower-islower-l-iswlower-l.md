---
title: islower, iswlower, _islower_l, _iswlower_l
ms.date: 4/2/2020
api_name:
- iswlower
- _islower_l
- islower
- _iswlower_l
- _o_islower
- _o_iswlower
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
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _istlower
- islower
- _ismbclower_l
- _liswlower_l
- _istlower_l
- _iswlower_l
- _islower _l
- _islower_l
- iswlower
helpviewer_keywords:
- _islower _l function
- _ismbclower_l function
- islower function
- _iswlower_l function
- _liswlower_l function
- _istlower_l function
- istlower function
- _istlower function
- iswlower function
- _islower_l function
ms.assetid: fcc3b70a-2b47-45fd-944d-e5c1942e6457
ms.openlocfilehash: 64fbde1db738dda694a911557748f2b46b6d8af8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343793"
---
# <a name="islower-iswlower-_islower_l-_iswlower_l"></a>islower, iswlower, _islower_l, _iswlower_l

Bir tamsedenin küçük bir karakteri temsil edip etmediğini belirler.

## <a name="syntax"></a>Sözdizimi

```C
int islower(
   int c
);
int iswlower(
   wint_t c
);
int islower_l(
   int c,
   _locale_t locale
);
int _iswlower_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*C*<br/>
Test etmek için sonda.

*Yerel ayar*<br/>
Kullanılacak yerel yer.

## <a name="return-value"></a>Dönüş Değeri

Bu yordamların her *biri, c* küçük bir karakterin belirli bir temsiliyse sıfırsız döndürür. **islower** küçük bir karakter *c* (a - z) ise sıfır olmayan bir değer döndürür. **iswlower,** küçük harfe karşılık gelen geniş bir *karakterse* veya *c,* **iswcntrl**, **iswdigit**, **iswpunct**veya **iswspace'in** sıfır olmadığı, uygulama tanımlı geniş karakter kümesinden biriyse sıfır olmayan bir değer döndürür. *C* test koşulunu karşılamazsa bu yordamların her biri 0 döndürür.

**_l** sonek olan bu işlevlerin sürümleri, yerel e-çözüme bağlı davranışları için geçerli yerel alan yerine geçen yerel alanı kullanır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

*C* EOF değilse veya 0 ile 0xFF aralığında, dahil **ise, daha yavaş** ve **_islower_l** davranışı tanımsızdır. Hata ayıklama CRT kitaplığı kullanıldığında ve *c* bu değerlerden biri değilse, işlevler bir iddiayı yükseltir.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istlower**|**ıslower**|[_ismbclower](ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|**iswlower**|
|**_istlower_l**|`_islower _l`|[_ismbclower_l](ismbclower-ismbclower-l-ismbcupper-ismbcupper-l.md)|**_liswlower_l**|

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**ıslower**|\<ctype.h>|
|**iswlower**|\<ctype.h> \<veya wchar.h>|
|**_islower_l**|\<ctype.h>|
|**_swlower_l**|\<ctype.h> \<veya wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflandırması](../../c-runtime-library/character-classification.md)<br/>
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[olduğunu, isw Rutinleri](../../c-runtime-library/is-isw-routines.md)<br/>
