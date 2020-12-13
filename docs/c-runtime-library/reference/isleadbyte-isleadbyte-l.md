---
description: 'Daha fazla bilgi edinin: ıleadbyte, _isleadbyte_l'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 544adda1b794db6a003e3ae7d51b15456574f875
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332659"
---
# <a name="isleadbyte-_isleadbyte_l"></a>isleadbyte, _isleadbyte_l

Bir karakterin çok baytlı bir karakterin ön baytı olup olmadığını belirler.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int isleadbyte( int c );
int _isleadbyte_l( int c );
```

### <a name="parameters"></a>Parametreler

*,*<br/>
Sınanacak tamsayı.

## <a name="return-value"></a>Dönüş Değeri

bağımsız değişken test koşulunu karşılıyorsa veya değilse 0 sıfır olmayan bir **değer döndürür.** "C" yerel ayarında ve tek baytlık karakter kümesi (SBCS) yerel ayarında, **ıleadbyte** her zaman 0 değerini döndürür.

## <a name="remarks"></a>Açıklamalar

**Ileadbyte** makrosu, bağımsız değişkeni çok baytlı bir karakterin ilk baytı ise sıfır dışında bir değer döndürür. **ıleadbyte** ,-1 (**EOF**) ile **uchar_max** (0xFF) (dahil) arasında herhangi bir tamsayı bağımsız değişkeni için anlamlı bir sonuç üretir.

**Ileadbyte** 'ın beklenen bağımsız değişken türü **`int`** ; imzalı bir karakter geçirilirse, derleyici imza uzantısı tarafından bir tamsayıya dönüştürebilir ve öngörülemeyen sonuçlara neden olabilir.

Bu işlevin **_l** sonekine sahip sürümü, yerel ayara bağlı davranışı için geçerli yerel ayar yerine geçirilen yerel ayarı kullanması dışında aynıdır.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istleadbyte**|Her zaman yanlış döndürür|**_isleadbyte**|Her zaman yanlış döndürür|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**ıleadbyte**|\<ctype.h>|
|**_isleadbyte_l**|\<ctype.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bayt sınıflandırması](../../c-runtime-library/byte-classification.md)<br/>
[Ayarlar](../../c-runtime-library/locale.md)<br/>
[_ismbb yordamlar](../../c-runtime-library/ismbb-routines.md)<br/>
