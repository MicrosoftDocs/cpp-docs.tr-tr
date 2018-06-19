---
title: wctype | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- wctype function
- wide characters
ms.assetid: 14aded12-4087-4123-bc48-db4e10999223
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0bb5003db02ed27c2906ebc3619313489e40e5fb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32411906"
---
# <a name="wctype"></a>wctype

Joker karakter kodları için bir sınıflandırma kuralı belirler.

## <a name="syntax"></a>Sözdizimi

```C
wctype_t wctype(
   const char * property
);
```

### <a name="parameters"></a>Parametreler

*property*<br/>
Özellik dizesi.

## <a name="return-value"></a>Dönüş Değeri

Varsa **LC_CTYPE** geçerli yerel ayar kategorisi adı ile eşleşen özellik dizesi bir sınıflandırma kuralı tanımlamak değil *özelliği*, sıfır işlevi döndürür. Aksi takdirde, sıfır olmayan bir değer ikinci bağımsız değişken olarak kullanım için uygun bir sonraki çağrı için döndürür [towctrans](towctrans.md).

## <a name="remarks"></a>Açıklamalar

İşlev joker karakter kodları için bir sınıflandırma kuralı belirler. Çağrıları aşağıdaki çiftleri tüm yerel ayarlarda aynı davranışı sahiptir (ancak uygulaması bile "C" yerel ayarda ek sınıflandırma kurallarını tanımlayabilirsiniz):

|İşlev|Aynı|
|--------------|-------------|
|iswalnum(c)|iswctype (c wctype ("alnum"))|
|iswalpha(c)|iswctype (c wctype ("Alfa"))|
|iswcntrl(c)|iswctype (c wctype ("Dnt"))|
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

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
