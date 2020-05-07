---
title: _ismbblead, _ismbblead_l
description: Microsoft C çalışma zamanı kitaplığı (CRT) _ismbblead ve _ismbblead_l işlevlerini açıklar.
ms.date: 4/2/2020
api_name:
- _ismbblead_l
- _ismbblead
- _o__ismbblead
- _o__ismbblead_l
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- ismbblead_l
- istlead
- _ismbblead
- _ismbblead_l
- ismbblead
- _istlead
helpviewer_keywords:
- _ismbblead_l function
- ismbblead function
- _ismbblead function
- istlead function
- ismbblead_l function
- _istlead function
ms.assetid: 2abc6f75-ed5c-472e-bfd0-e905a1835ccf
ms.openlocfilehash: 7680793b71c4535ed75433ac98167e52a39896ba
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82918663"
---
# <a name="_ismbblead-_ismbblead_l"></a>_ismbblead, _ismbblead_l

Bir karakteri, çok baytlı bir karakterin bir ön baytı olup olmadığını belirleyecek şekilde sınar.

## <a name="syntax"></a>Sözdizimi

```C
int _ismbblead(
   unsigned int c
);
int _ismbblead_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*,*\
Sınanacak tamsayı.

*ayarlar*\
Kullanılacak yerel ayar.

## <a name="return-value"></a>Döndürülen değer

Tamsayı *c* , çok baytlı bir karakterin ilk baytı ise sıfır dışında bir değer döndürür.

## <a name="remarks"></a>Açıklamalar

Çok baytlı karakterler bir ön bayt ve sonrasında sondaki bir bayt oluşur. Ön baytlar, belirli bir karakter kümesi için belirli bir aralıkta olacak şekilde ayırt edilir. Örneğin, yalnızca kod sayfası 932 ' de, 1.0x9F ve 0xE0-0xFC içindeki ön baytlar arasındadır.

**_ismbblead** , yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır. **_ismbblead_l** , bunun yerine geçirilen yerel ayarı kullanması dışında aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

Yerel ayar UTF-8 olduğunda **_ismbblead** ve **_ismbblead_l** her zaman, *c* 'nin bir ön bayt olup olmadığı her zaman 0 (yanlış) döndürür.

**_ismbblead** ve **_Ismbblead_l** , standart C kitaplığının bir parçası değil, Microsoft 'a özgüdür. Bunları, taşınabilir kod istediğiniz yerde kullanmanız önerilmez. Standart C uyumluluğu için bunun yerine **mbrlen** kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel metin rutin eşlemeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_istlead**|Her zaman yanlış döndürür|**_ismbblead**|Her zaman yanlış döndürür|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_ismbblead**|\<Mbctype. h> veya \<mbstring. h>|\<CType. h>, * \<limit. h>, \<stdlib. h>|
|**_ismbblead_l**|\<Mbctype. h> veya \<mbstring. h>|\<CType. h>, * \<limit. h>, \<stdlib. h>|

\*Test koşullarına yönelik bildirim sabitleri için.

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bayt sınıflandırması](../../c-runtime-library/byte-classification.md)\
[_ismbb yordamlar](../../c-runtime-library/ismbb-routines.md)\
[mbrlen](mbrlen.md)
