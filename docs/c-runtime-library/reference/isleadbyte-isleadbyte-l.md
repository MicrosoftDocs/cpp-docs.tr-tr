---
title: isleadbyte, _isleadbyte_l
ms.date: 4/2/2020
api_name:
- _isleadbyte_l
- isleadbyte
- _o__isleadbyte_l
- _o_isleadbyte
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _istleadbyte
- _isleadbyte_l
- isleadbyte
helpviewer_keywords:
- lead bytes
- _isleadbyte_l function
- _istleadbyte function
- istleadbyte function
- isleadbyte function
ms.assetid: 3b2bcf09-d82b-4803-9e80-59d04942802a
ms.openlocfilehash: dddf1d669f77805df8e00f506b6427603ac8fd9f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343834"
---
# <a name="isleadbyte-_isleadbyte_l"></a>isleadbyte, _isleadbyte_l

Bir karakterin çok baytlık karakterin baş bayt olup olmadığını belirler.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
int isleadbyte( int c );
int _isleadbyte_l( int c );
```

### <a name="parameters"></a>Parametreler

*C*<br/>
Test etmek için sonda.

## <a name="return-value"></a>Dönüş Değeri

**isleadbyte,** bağımsız değişken test koşulunu karşılarsa sıfır olmayan bir değer veya yoksa 0 döndürür. "C" yerel ve tek bayt karakter kümesi (SBCS) yerel **ayarlarda, isleadbyte** her zaman 0 döndürür.

## <a name="remarks"></a>Açıklamalar

**Isleadbyte** makro, bağımsız değişkeni çok bayt karakterin ilk bayt'ıysa sıfır olmayan bir değer döndürür. **isleadbayt** ,-1 **(EOF)** ile **UCHAR_MAX** (0xFF) arasında yer alan herhangi bir tamsayı bağımsız değişkeni için anlamlı bir sonuç üretir.

**Isleadbyte** beklenen argüman türü **int**olduğunu; imzalı bir karakter geçirilirse, derleyici işaret uzantısı ile bir tamsayıya dönüştürebilir ve öngörülemeyen sonuçlar verebilir.

Bu işlevin **_l** sonekli sürümü, yerele bağımlı davranışı için geçerli yerel alan yerine geçirilen yerelliği kullanması dışında aynıdır.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istleadbyte**|Her zaman yanlış döndürür|**_isleadbyte**|Her zaman yanlış döndürür|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**isleadbayt**|\<ctype.h>|
|**_isleadbyte_l**|\<ctype.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Bayt Sınıflandırması](../../c-runtime-library/byte-classification.md)<br/>
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[_ismbb Rutinleri](../../c-runtime-library/ismbb-routines.md)<br/>
