---
title: wctype
ms.date: 11/04/2016
apiname:
- wctype
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
apitype: DLLExport
f1_keywords:
- wctype
helpviewer_keywords:
- wctype function
- wide characters
ms.assetid: 14aded12-4087-4123-bc48-db4e10999223
ms.openlocfilehash: 81caf8e1ab04635d205d7b01af2d4c2896eec01c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456907"
---
# <a name="wctype"></a>wctype

Geniş karakter kodlarını için bir sınıflandırma kuralı belirler.

## <a name="syntax"></a>Sözdizimi

```C
wctype_t wctype(
   const char * property
);
```

### <a name="parameters"></a>Parametreler

*property*<br/>
Dize özelliği.

## <a name="return-value"></a>Dönüş Değeri

Varsa **LC_CTYPE** geçerli yerel ayarının kategori adı, özellik dizesi ile eşleşen bir sınıflandırma kuralı tanımlamıyor *özelliği*, sıfır döndürür. Aksi takdirde, sıfır dışında bir değeri ikinci bağımsız değişken olarak kullanmak için uygun bir sonraki çağrı döndürür [towctrans](towctrans.md).

## <a name="remarks"></a>Açıklamalar

İşlev geniş karakter kodlarını için bir sınıflandırma kuralı belirler. Aşağıdaki çağrıları çiftleri tüm yerel ayarlarda aynı davranışa sahip (ancak bir uygulama da "C" yerel ayarında ek sınıflandırma kuralları tanımlayabilirsiniz):

|İşlev|Aynı|
|--------------|-------------|
|iswalnum(c)|iswctype (c wctype ("alnum'la"))|
|iswalpha(c)|iswctype (c wctype ("Alfa"))|
|iswcntrl(c)|iswctype (c wctype ("CTRL"))|
|iswdigit(c)|iswctype (c wctype ("basamaklı"))|
|iswgraph(c)|iswctype (c wctype ("grafiği"))|
|iswlower(c)|iswctype (c wctype ("alt"))|
|iswprint(c)|iswctype (c wctype ("PRINT"))|
|iswpunct(c)|iswctype (c wctype ("noktalama işareti"))|
|iswspace(c)|iswctype (c wctype ("alanı"))|
|iswupper(c)|iswctype (c wctype ("üst"))|
|iswxdigit(c)|iswctype (c wctype ("xdigit"))|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**wctype**|\<wctype.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
