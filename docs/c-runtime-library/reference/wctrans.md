---
title: wctrans
ms.date: 11/04/2016
apiname:
- wctrans
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wctrans
helpviewer_keywords:
- character codes, wctrans
- characters, codes
- characters, converting
- wctrans function
ms.assetid: 215404bf-6d60-489c-9ae9-880e6b586162
ms.openlocfilehash: 3c7aace7a93160d2e9a4c1523d49bcaf6ae4dc20
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188461"
---
# <a name="wctrans"></a>wctrans

Başka bir karakter kodlarını kümesindeki bir eşleme belirler.

## <a name="syntax"></a>Sözdizimi

```C
wctrans_t wctrans(
   const char *property
);
```

### <a name="parameters"></a>Parametreler

*property*<br/>
Geçerli dönüşümler birini belirten bir dize.

## <a name="return-value"></a>Dönüş Değeri

Varsa **LC_CTYPE** geçerli yerel ayarının kategori adı, özellik dizesi ile eşleşen bir eşleme tanımlamıyor *özelliği*, sıfır döndürür. Aksi takdirde, sıfır dışında bir değeri ikinci bağımsız değişken olarak kullanmak için uygun bir sonraki çağrı döndürür [towctrans](towctrans.md).

## <a name="remarks"></a>Açıklamalar

Bu işlev, başka bir karakter kodlarını kümesindeki bir eşleme belirler.

Aşağıdaki çağrıları çiftleri tüm yerel ayarlarda aynı davranışa sahip, ancak ek eşlemeleri bile "C" yerel ayarında tanımlamak da mümkündür:

|İşlev|Aynı|
|--------------|-------------|
|tolower(c)|towctrans (c wctrans("towlower"))|
|towupper(c)|towctrans (c wctrans("toupper"))|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**wctrans**|\<wctype.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_wctrans.cpp
// compile with: /EHsc
// This example determines a mapping from one set of character
// codes to another.

#include <wchar.h>
#include <wctype.h>
#include <stdio.h>
#include <iostream>

int main()
{
    wint_t c = 'a';
    printf_s("%d\n",c);

    wctrans_t i = wctrans("toupper");
    printf_s("%d\n",i);

    wctrans_t ii = wctrans("towlower");
    printf_s("%d\n",ii);

    wchar_t wc = towctrans(c, i);
    printf_s("%d\n",wc);
}
```

```Output
97
1
0
65
```

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
