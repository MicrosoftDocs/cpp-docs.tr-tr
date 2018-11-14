---
title: _get_doserrno
ms.date: 11/04/2016
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
helpviewer_keywords:
- get_doserrno function
- _get_doserrno function
ms.assetid: 7fec7be3-6e39-4181-846b-8ef24489361c
ms.openlocfilehash: 700f710e6d94f48b03697325bb720dbc539fe04e
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51331028"
---
# <a name="getdoserrno"></a>_get_doserrno

Veri dönüştürülür önce işletim sistemi tarafından döndürülen hata değerini alır bir **errno** değeri.

## <a name="syntax"></a>Sözdizimi

```C
errno_t _get_doserrno(
   int * pValue
);
```

### <a name="parameters"></a>Parametreler

*pValue*<br/>
Geçerli değeri ile doldurulacak bir tamsayı işaretçisi **_doserrno** genel makro.

## <a name="return-value"></a>Dönüş Değeri

Varsa **_get_doserrno** başarılı, sıfır döndürür; başarısız olursa hata kodu döndürür. Varsa *pValue* olduğu **NULL**, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse, bu işlev ayarlar **errno** için **EINVAL** ve döndürür **EINVAL**.

## <a name="remarks"></a>Açıklamalar

**_Doserrno** genel makro, CRT başlatma sırasında sıfır olarak ayarlandığında, yürütme işleminden önce başlar. Bir işletim sistemi hata döndüren sistem düzeyindeki işlevi çağrısı tarafından döndürülen işletim sistemi hata değerine ayarlanır ve, hiçbir zaman sıfıra yürütme sırasında sıfırlanır. Hata değeri denetlemek için kod yazdığınızda, işlev tarafından her zaman NET döndürülen **_doserrno** kullanarak [_set_doserrno](set-doserrno.md) işlevi çağırmadan önce. Başka bir işlev çağrısı üzerine yazılabilir olmadığından **_doserrno**, değeri kullanarak kontrol **_get_doserrno** işlev çağrısının hemen sonra.

Öneririz [_get_errno](get-errno.md) yerine **_get_doserrno** taşınabilir hata kodları.

Olası değerleri **_doserrno** tanımlanan \<errno.h >.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_get_doserrno**|\<stdlib.h >, \<cstdlib > (C++)|\<errno.h >, \<cerrno > (C++)|

**_get_doserrno** bir Microsoft uzantısıdır. Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[_set_doserrno](set-doserrno.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
