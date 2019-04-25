---
title: _ismbbblank, _ismbbblank_l
ms.date: 11/04/2016
apiname:
- _ismbbblank_l
- _ismbbblank
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
ms.assetid: d21b2e41-7206-41f5-85bb-9c9ab4f3e21b
ms.openlocfilehash: c6709d5a5870c44d200b704e4a34043ff9c37226
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62286957"
---
# <a name="ismbbblank-ismbbblankl"></a>_ismbbblank, _ismbbblank_l

Belirtilen bir çok baytlı karakterin boşluk karakteri olup olmadığını belirler.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _ismbbblank(
   unsigned int c
);
int _ismbbblank_l(
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

**_ismbbblank** sıfır olmayan bir değer döndürür *c* boşluk (0x20) karakterini, yatay sekme (0x09) karakteri veya hangi içinmetinsatırıiçindesözcükleriayırmakiçinkullanılanbiryerelayaraözgükaraktertemsileden**isspace** true; Aksi takdirde, 0 döndürür. **_ismbbblank** herhangi bir yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır. **_ismbbblank_l** bunun yerine geçirilen yerel ayarı kullanması hariç, aynıdır. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_ismbbblank**|\<Mbctype.h >|
|**_ismbbblank_l**|\<Mbctype.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bayt Sınıflandırması](../../c-runtime-library/byte-classification.md)<br/>
[_ismbb Yordamları](../../c-runtime-library/ismbb-routines.md)<br/>
