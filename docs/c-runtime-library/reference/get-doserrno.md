---
title: _get_doserrno
ms.date: 4/2/2020
api_name:
- _get_doserrno
- _o__get_doserrno
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
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _get_doserrno
- get_doserrno
helpviewer_keywords:
- get_doserrno function
- _get_doserrno function
ms.assetid: 7fec7be3-6e39-4181-846b-8ef24489361c
ms.openlocfilehash: 2d5d4e224b39e9fa597e12975d27fa5720fbfbc7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345251"
---
# <a name="_get_doserrno"></a>_get_doserrno

**Bir errno** değerine çevrilmeden önce işletim sistemi tarafından döndürülen hata değerini alır.

## <a name="syntax"></a>Sözdizimi

```C
errno_t _get_doserrno(
   int * pValue
);
```

### <a name="parameters"></a>Parametreler

*pDeğer*<br/>
Genel makronun geçerli değeriyle doldurulması için **_doserrno bir** tamsayı işaretçisi.

## <a name="return-value"></a>Dönüş Değeri

**_get_doserrno** başarılı olursa, sıfır döndürür; başarısız olursa, bir hata kodu döndürür. *pValue* **NULL**ise, geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, bu işlev **EINVAL için errno** ayarlar ve **EINVAL** döndürür. **EINVAL**

## <a name="remarks"></a>Açıklamalar

_doserrno **_doserrno** genel makro, işlem yürütme başlamadan önce CRT başlatma sırasında sıfıra ayarlanır. İşletim sistemi hatasını döndüren herhangi bir sistem düzeyindeki işlev çağrısı tarafından döndürülen işletim sistemi hata değerine ayarlanır ve yürütme sırasında sıfırlanır. Bir işlev tarafından döndürülen hata değerini denetlemek için kod yazdığınızda, işlev çağrısından önce [_set_doserrno](set-doserrno.md) kullanarak her zaman **_doserrno** temizleyin. Başka bir işlev çağrısı **_doserrno**üzerine yazabileceğinden, işlev çağrısından hemen sonra **_get_doserrno** kullanarak değeri kontrol edin.

Taşınabilir hata kodları için **_get_doserrno** yerine [_get_errno](get-errno.md) öneririz.

_doserrno olası değerleri errno.h> tanımlanır. **_doserrno** \<

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|---------------------|
|**_get_doserrno**|\<stdlib.h>, \<cstdlib> (C++)|\<errno.h>, \<cerrno> (C++)|

**_get_doserrno** bir Microsoft uzantısıdır. Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[_set_doserrno](set-doserrno.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
