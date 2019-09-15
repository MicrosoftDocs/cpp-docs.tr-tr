---
title: _ismbbblank, _ismbbblank_l
ms.date: 11/04/2016
api_name:
- _ismbbblank_l
- _ismbbblank
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
ms.assetid: d21b2e41-7206-41f5-85bb-9c9ab4f3e21b
ms.openlocfilehash: 21f4c88b00774159f8e6945973641e67718494e6
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70954242"
---
# <a name="_ismbbblank-_ismbbblank_l"></a>_ismbbblank, _ismbbblank_l

Belirtilen çok baytlı karakterin boş bir karakter olup olmadığını belirler.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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
Sınanacak tamsayı.

*ayarlar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**_ısmbbblank** , *c* bir boşluk (0x20) karakteri, yatay sekme (0x09) karakteri veya bir metin satırı **içinde, bir** metin satırı içinde olan sözcükleri ayırmak için kullanılan yerel ayara özgü bir karakter gösteriyorsa sıfır dışında bir değer döndürür; Aksi takdirde, 0 döndürür. **_ismbbblank** , yerel ayara bağlı herhangi bir davranış için geçerli yerel ayarı kullanır. **_ismbbblank_l** , bunun yerine geçirilen yerel ayarı kullanması dışında aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_ismbbboş**|\<Mbctype. h >|
|**_ismbbblank_l**|\<Mbctype. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bayt Sınıflandırması](../../c-runtime-library/byte-classification.md)<br/>
[_ismbb Yordamları](../../c-runtime-library/ismbb-routines.md)<br/>
