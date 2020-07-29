---
title: ':::no-loc(strtol):::, :::no-loc(wcstol):::, :::no-loc(_strtol_l):::, :::no-loc(_wcstol_l):::'
ms.date: 4/2/2020
api_name:
- ':::no-loc(strtol):::'
- ':::no-loc(wcstol):::'
- ':::no-loc(_strtol_l):::'
- ':::no-loc(_wcstol_l):::'
- '_o_:::no-loc(_strtol_l):::'
- '_o_:::no-loc(_wcstol_l):::'
- '_o_:::no-loc(strtol):::'
- '_o_:::no-loc(wcstol):::'
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
- api-ms-win-crt-convert-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- ':::no-loc(_wcstol_l):::'
- ':::no-loc(strtol):::'
- ':::no-loc(_tcstol):::'
- ':::no-loc(wcstol):::'
- ':::no-loc(_strtol_l):::'
- ':::no-loc(_tcstol_l):::'
helpviewer_keywords:
- ':::no-loc(wcstol)::: function'
- :::no-loc(wcstol):::_l function
- ':::no-loc(_tcstol)::: function'
- string conversion, to integers
- tcstol function
- :::no-loc(strtol):::_l function
- ':::no-loc(_wcstol_l)::: function'
- ':::no-loc(_strtol_l)::: function'
- ':::no-loc(strtol)::: function'
ms.assetid: 1787c96a-f283-4a83-9325-33cfc1c7e240
no-loc:
- ':::no-loc(strtol):::'
- ':::no-loc(wcstol):::'
- ':::no-loc(_strtol_l):::'
- ':::no-loc(_wcstol_l):::'
- ':::no-loc(LONG_MAX):::'
- ':::no-loc(LONG_MIN):::'
- ':::no-loc(errno):::'
- ':::no-loc(ERANGE):::'
- ':::no-loc(EINVAL):::'
- ':::no-loc(LC_NUMERIC):::'
- ':::no-loc(_tcstol):::'
- ':::no-loc(_tcstol_l):::'
- ':::no-loc(localeconv):::'
- ':::no-loc(setlocale):::'
- ':::no-loc(_wsetlocale):::'
- ':::no-loc(strtod):::'
- ':::no-loc(_strtod_l):::'
- ':::no-loc(wcstod):::'
- ':::no-loc(_wcstod_l):::'
- ':::no-loc(strtoll):::'
- ':::no-loc(_strtoll_l):::'
- ':::no-loc(wcstoll):::'
- ':::no-loc(_wcstoll_l):::'
- ':::no-loc(strtoul):::'
- ':::no-loc(_strtoul_l):::'
- ':::no-loc(wcstoul):::'
- ':::no-loc(_wcstoul_l):::'
- ':::no-loc(atof):::'
- ':::no-loc(_atof_l):::'
- ':::no-loc(_wtof):::'
- ':::no-loc(_wtof_l):::'
ms.openlocfilehash: a5265b434f14f299532d6f5ebb65c83d75ea63ca
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232410"
---
# <a name="no-locstrtol-no-locwcstol-no-loc_strtol_l-no-loc_wcstol_l"></a>:::no-loc(strtol):::, :::no-loc(wcstol):::, :::no-loc(_strtol_l):::, :::no-loc(_wcstol_l):::

Dizeleri bir **`long`** tamsayı değerine dönüştürür.

## <a name="syntax"></a>Söz dizimi

```C
long :::no-loc(strtol):::(
   const char *string,
   char **end_ptr,
   int base
);
long :::no-loc(wcstol):::(
   const wchar_t *string,
   wchar_t **end_ptr,
   int base
);
long :::no-loc(_strtol_l):::(
   const char *string,
   char **end_ptr,
   int base,
   _locale_t locale
);
long :::no-loc(_wcstol_l):::(
   const wchar_t *string,
   wchar_t **end_ptr,
   int base,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*dizisinde*\
Dönüştürülecek null ile sonlandırılmış dize.

*end_ptr*\
Bir çıktı parametresi, son yorumlanan karakterden sonraki karakteri işaret etmek üzere ayarlanır. **Null**ise yoksayıldı.

*temel*\
Kullanılacak sayı temeli.

*ayarlar*\
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**:::no-loc(strtol):::**, **:::no-loc(wcstol):::** , **:::no-loc(_strtol_l):::** ve **:::no-loc(_wcstol_l):::** *dizesinde*temsil edilen değeri döndürür. Dönüştürme mümkün değilse 0 döndürür. Temsili bir taşmaya neden olduğunda, **:::no-loc(LONG_MAX):::** veya döndürür **:::no-loc(LONG_MIN):::** .

**:::no-loc(errno):::****:::no-loc(ERANGE):::** taşma veya yetersiz gelme gerçekleşirse olarak ayarlanır. **:::no-loc(EINVAL):::** *Dize* **null**ise olarak ayarlanır. Ya da *taban* sıfır değilse veya 2 ' den küçükse ya da 36 ' den büyükse. , Ve diğer dönüş kodları hakkında daha fazla bilgi için **:::no-loc(ERANGE):::** **:::no-loc(EINVAL):::** bkz. [_DOS :::no-loc(errno)::: , :::no-loc(errno)::: , _sys_errlist ve _sys_nerr](../../c-runtime-library/:::no-loc(errno):::-dos:::no-loc(errno):::-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**:::no-loc(strtol):::**,, **:::no-loc(wcstol):::** **:::no-loc(_strtol_l):::** Ve **:::no-loc(_wcstol_l):::** işlevleri *dizeyi* öğesine dönüştürür **`long`** . Bir sayının parçası olarak tanınmayan ilk karakterde *dize* okumayı durdurur. Bu, Sonlandırıcı null karakter veya temelden büyük veya buna eşit olan ilk alfasayısal karakter *olabilir.*

**:::no-loc(wcstol):::** ve, **:::no-loc(_wcstol_l):::** ve öğesinin geniş karakterli sürümleridir **:::no-loc(strtol):::** **:::no-loc(_strtol_l):::** . *Dize* bağımsız değişkeni geniş karakterli bir dizedir. Bu işlevler **:::no-loc(strtol):::** , ve diğer koşullarda aynı şekilde davranır **:::no-loc(_strtol_l):::** . Yerel ayarın **:::no-loc(LC_NUMERIC):::** kategori ayarı, *dizedeki*taban karakterinin (kesirli işaret veya ondalık noktanın) tanınmasını belirler. İşlevleri **:::no-loc(strtol):::** ve **:::no-loc(wcstol):::** geçerli yerel ayarı kullanır. **:::no-loc(_strtol_l):::** ve **:::no-loc(_wcstol_l):::** bunun yerine geçirilen yerel ayarı kullanın. Daha fazla bilgi için bkz :::no-loc(setlocale)::: . [] ve [locale](../../c-runtime-library/locale.md).

*End_ptr* **null**olduğunda, yok sayılır. Aksi takdirde, taramayı durduran karaktere yönelik bir işaretçi *end_ptr*tarafından işaret edilen konumda depolanır. Geçerli bir basamak bulunamazsa veya geçersiz bir taban belirtilmişse dönüştürme yapılamaz. Daha sonra *dizenin* değeri *end_ptr*tarafından işaret edilen konumda depolanır.

**:::no-loc(strtol):::***dizenin* aşağıdaki biçimdeki bir dizeye işaret etmek bekler:

> [*boşluk*] [{ **+** &#124; **-** }] [**0** [{ **x** &#124; **x** }]] [*alfasayısal*]

Köşeli parantezler ( `[ ]` ) surround isteğe bağlı öğeleri. Tek bir öğe için küme ayraçları ve dikey çubuk ( `{ | }` ) surround alternatifleri. *boşluk,* yoksayılan boşluk ve sekme karakterlerinden oluşabilir. *alfasayısal* sayılar veya ' a '-' z ' (ya da ' a '-' z ') harfleri ondalık basamaklıdır. Bu forma uymayan ilk karakter taramayı durduruyor. *Taban* 2 ile 36 arasındaysa, sayının temeli olarak kullanılır. *Taban* 0 ise, *dizenin* gösterdiği dizenin başlangıç karakterleri, temeli belirlemede kullanılır. İlk karakter 0 ise ve ikinci karakter ' x ' veya ' X ' değilse, dize sekizlik bir tamsayı olarak yorumlanır. İlk karakter ' 0 ' ise ve ikinci karakter ' x ' veya ' X ' ise, dize onaltılık tamsayı olarak yorumlanır. İlk karakter ' 1 '-' 9 ' arasında ise, dize bir ondalık tamsayı olarak yorumlanır. ' A '-' z ' (veya ' A '-' Z ' arasındaki), 10 ile 35 arası değerlere atanır. Tarama yalnızca değerleri *tabandan*küçük olan harflere izin verir. Taban aralığının dışındaki ilk karakter taramayı sonlandırır. Örneğin, *dizenin* "01" ile başlayacağını varsayın. *Taban* 0 ise, tarayıcı sekizli tamsayı olduğunu varsayar. ' 8 ' veya ' 9 ' karakteri taramayı durduruyor.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**:::no-loc(_tcstol):::**|**:::no-loc(strtol):::**|**:::no-loc(strtol):::**|**:::no-loc(wcstol):::**|
|**:::no-loc(_tcstol_l):::**|**:::no-loc(_strtol_l):::**|**:::no-loc(_strtol_l):::**|**:::no-loc(_wcstol_l):::**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**:::no-loc(strtol):::**|\<stdlib.h>|
|**:::no-loc(wcstol):::**|\<stdlib.h> veya \<wchar.h>|
|**:::no-loc(_strtol_l):::**|\<stdlib.h>|
|**:::no-loc(_wcstol_l):::**|\<stdlib.h> veya \<wchar.h>|

**:::no-loc(_strtol_l):::** Ve **:::no-loc(_wcstol_l):::** Işlevleri, standart C kitaplığının bir parçası değil, Microsoft 'a özgüdür. Ek uyumluluk bilgileri için bkz. [Uyumluluk](../compatibility.md).

## <a name="example"></a>Örnek

İçin örneğe bakın [:::no-loc(strtod):::](:::no-loc(strtod):::-:::no-loc(strtod):::-l-:::no-loc(wcstod):::-:::no-loc(wcstod):::-l.md) .

## <a name="see-also"></a>Ayrıca bkz.

[Veri dönüştürme](../data-conversion.md)\
[Ayarlar](../locale.md)\
[:::no-loc(localeconv):::](:::no-loc(localeconv):::.md)\
[:::no-loc(setlocale):::, :::no-loc(_wsetlocale):::](:::no-loc(setlocale):::-w:::no-loc(setlocale):::.md)\
[Sayısal değer işlevlerine dize](../string-to-numeric-value-functions.md)\
[:::no-loc(strtod):::, :::no-loc(_strtod_l):::, :::no-loc(wcstod):::, :::no-loc(_wcstod_l):::](:::no-loc(strtod):::-:::no-loc(strtod):::-l-:::no-loc(wcstod):::-:::no-loc(wcstod):::-l.md)\
[:::no-loc(strtoll):::, :::no-loc(_strtoll_l):::, :::no-loc(wcstoll):::, :::no-loc(_wcstoll_l):::](:::no-loc(strtoll):::-:::no-loc(strtoll):::-l-:::no-loc(wcstoll):::-:::no-loc(wcstoll):::-l.md)\
[:::no-loc(strtoul):::, :::no-loc(_strtoul_l):::, :::no-loc(wcstoul):::, :::no-loc(_wcstoul_l):::](:::no-loc(strtoul):::-:::no-loc(strtoul):::-l-:::no-loc(wcstoul):::-:::no-loc(wcstoul):::-l.md)\
[:::no-loc(atof):::, :::no-loc(_atof_l):::, :::no-loc(_wtof):::, :::no-loc(_wtof_l):::](:::no-loc(atof):::-:::no-loc(atof):::-l-wtof-wtof-l.md)
