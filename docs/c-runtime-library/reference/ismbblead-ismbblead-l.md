---
title: _ismbblead, _ismbblead_l
ms.date: 11/04/2016
apiname:
- _ismbblead_l
- _ismbblead
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: 7bf8e8c88153e2f22cfa08bb35ff8d4ba01a8804
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157217"
---
# <a name="ismbblead-ismbbleadl"></a>_ismbblead, _ismbblead_l

Çok baytlı karakterin ön baytı olup olmadığını belirlemek için karakteri test eder.

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
Test edilecek tamsayı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Sıfır dışında bir değer döndürür tamsayı *c* olan çok baytlı bir karakterin ilk baytı.

## <a name="remarks"></a>Açıklamalar

Çok baytlı karakter izleyen son ardından baytı oluşur. Ön baytlar verilen bir karakter kümesi için belirli bir aralıkta olmalarıyla fark. Örneğin, kod sayfası 932'de yalnızca ön bayt 0x81-0x9F ve 0xE0 - 0xFC aralığındadır.

**_ismbblead** yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır. **_ismbblead_l** bunun yerine iletilmiş yerel ayarı kullanması dışında aynıdır. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_istlead**|Daima yanlış getirir|**_ismbblead**|Daima yanlış getirir|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_ismbblead**|\<Mbctype.h > veya \<mbstring.h >|\<CType.h >, * \<lımıts.h >, \<stdlib.h >|
|**_ismbblead_l**|\<Mbctype.h > veya \<mbstring.h >|\<CType.h >, * \<lımıts.h >, \<stdlib.h >|

\* Test koşullarına ilişkin bildirim sabitleri için.

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bayt Sınıflandırması](../../c-runtime-library/byte-classification.md)<br/>
[_ismbb Yordamları](../../c-runtime-library/ismbb-routines.md)<br/>
