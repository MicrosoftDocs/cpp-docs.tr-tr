---
title: _ismbblead, _ismbblead_l
ms.date: 11/04/2016
api_name:
- _ismbblead_l
- _ismbblead
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
ms.openlocfilehash: c0f9ec748a86d5d1413cf4f881234d786c2a2d78
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70954060"
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

*c*<br/>
Sınanacak tamsayı.

*ayarlar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Tamsayı *c* , çok baytlı bir karakterin ilk baytı ise sıfır dışında bir değer döndürür.

## <a name="remarks"></a>Açıklamalar

Çok baytlı karakterler bir ön bayt ve sonrasında sondaki bir bayt oluşur. Ön baytlar, belirli bir karakter kümesi için belirli bir aralıkta olacak şekilde ayırt edilir. Örneğin, yalnızca kod sayfası 932 ' de, 1.0x9F ve 0xE0-0xFC içindeki ön baytlar arasındadır.

**_ismbblider** , yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır. **_ismbblead_l** , bunun yerine geçirilen yerel ayarı kullanması dışında aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_istlider**|Her zaman yanlış döndürür|**_ismbblider**|Her zaman yanlış döndürür|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_ismbblider**|\<Mbctype. h > veya \<mbstring. h >|\<CType. h >, * \<limit. h >, \<Stdlib. h >|
|**_ismbblead_l**|\<Mbctype. h > veya \<mbstring. h >|\<CType. h >, * \<limit. h >, \<Stdlib. h >|

\*Test koşullarına yönelik bildirim sabitleri için.

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bayt Sınıflandırması](../../c-runtime-library/byte-classification.md)<br/>
[_ismbb Yordamları](../../c-runtime-library/ismbb-routines.md)<br/>
