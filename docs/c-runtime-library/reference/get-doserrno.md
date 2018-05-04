---
title: _get_doserrno | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _get_doserrno
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _get_doserrno
- get_doserrno
dev_langs:
- C++
helpviewer_keywords:
- get_doserrno function
- _get_doserrno function
ms.assetid: 7fec7be3-6e39-4181-846b-8ef24489361c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f7cef2c068fad2f18cb1d11d33e551588800cb64
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="getdoserrno"></a>_get_doserrno

İçine çevrilen önce işletim sistemi tarafından döndürülen hata değerini alır bir **errno** değeri.

## <a name="syntax"></a>Sözdizimi

```C
errno_t _get_doserrno( 
   int * pValue 
);
```

### <a name="parameters"></a>Parametreler

*pValue*<br/>
Tamsayı geçerli değeri ile doldurulması için bir işaretçi **_doserrno** genel makrosu.

## <a name="return-value"></a>Dönüş Değeri

Varsa **_get_doserrno** başarılı, sıfır döndürür; başarısız olursa bir hata kodu döndürür. Varsa *pValue* olan **NULL**, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bu işlev devam etmek için yürütülmesine izin veriliyorsa, ayarlar **errno** için **EINVAL** ve döndürür **EINVAL**.

## <a name="remarks"></a>Açıklamalar

**_Doserrno** genel makrosu CRT başlatma sırasında sıfır olarak ayarlandığında, yürütme işleminden önce başlar. Bir işletim sistemi hata veren tüm sistem düzeyindeki işlevi çağrı tarafından döndürülen işletim sistemi hata değerini ayarlayın ve onu hiç yürütme sırasında sıfır sıfırlanır. Döndürülen bir işlev tarafından her zaman açık olduğunda hata değerini denetlemek için kod yazma **_doserrno** kullanarak [_set_doserrno](set-doserrno.md) işlev çağrısı önce. Başka bir işlev çağrısı üzerine çünkü **_doserrno**, kullanarak değerini denetleyin **_get_doserrno** işlev çağrısının hemen sonra.

Öneririz [_get_errno](get-errno.md) yerine **_get_doserrno** taşınabilir hata kodları için.

Olası değerlerini **_doserrno** tanımlanan \<errno.h >.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|---------------------|
|**_get_doserrno**|\<stdlib.h >, \<cstdlib > (C++)|\<errno.h >, \<cerrno > (C++)|

**_get_doserrno** bir Microsoft uzantısıdır. Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[_set_doserrno](set-doserrno.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
