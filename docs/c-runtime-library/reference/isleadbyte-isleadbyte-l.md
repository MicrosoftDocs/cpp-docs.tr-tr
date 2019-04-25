---
title: isleadbyte, _isleadbyte_l
ms.date: 11/04/2016
apiname:
- _isleadbyte_l
- isleadbyte
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: 1a3f427e49e53bb553020da100b0e713350fab3f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62286924"
---
# <a name="isleadbyte-isleadbytel"></a>isleadbyte, _isleadbyte_l

Bir karakterin çok baytlı karakterin ön baytı olup olmadığını belirler.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int isleadbyte( int c );
int _isleadbyte_l( int c );
```

### <a name="parameters"></a>Parametreler

*c*<br/>
Test edilecek tamsayı.

## <a name="return-value"></a>Dönüş Değeri

**isleadbyte** kullanmıyorsa, bağımsız değişken test koşulunu veya 0 karşılıyorsa, sıfır olmayan bir değer döndürür. "C" yerel ayarında ve tek baytlık karakter (SBCS) yerel kümesi **isleadbyte** her zaman 0 değerini döndürür.

## <a name="remarks"></a>Açıklamalar

**İsleadbyte** makrosu, kendi bağımsız değişken çok baytlı bir karakterin ilk baytı ise sıfır olmayan bir değer döndürür. **isleadbyte** -1 herhangi bir tamsayı bağımsız değişkeni için anlamlı bir sonuç üretir (**EOF**) için **UCHAR_MAX** (0xFF) dahil.

Beklenen değişken türü **isleadbyte** olduğu **int**; işaretli bir karakter geçerse derleyici öngörülemeyen sonuçlara işaret uzantısı ilse, bir tamsayıya dönüştürmek.

Bu işlevle sürümünü **_l** soneki, yerel ayara bağlı davranışı için geçerli yerel ayarı yerine iletilen yerel ayarı kullanması hariç, aynıdır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istleadbyte**|Daima yanlış getirir|**_isleadbyte**|Daima yanlış getirir|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**isleadbyte**|\<CType.h >|
|**_isleadbyte_l**|\<CType.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bayt Sınıflandırması](../../c-runtime-library/byte-classification.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[_ismbb Yordamları](../../c-runtime-library/ismbb-routines.md)<br/>
