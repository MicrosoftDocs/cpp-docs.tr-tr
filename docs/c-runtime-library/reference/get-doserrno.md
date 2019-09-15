---
title: _get_doserrno
ms.date: 11/04/2016
api_name:
- _get_doserrno
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
ms.openlocfilehash: 2810ead8bdd7d6c77cb2b55f4f97371bfc9751e6
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70956034"
---
# <a name="_get_doserrno"></a>_get_doserrno

Bir **errno** değerine çevrilmeden önce işletim sistemi tarafından döndürülen hata değerini alır.

## <a name="syntax"></a>Sözdizimi

```C
errno_t _get_doserrno(
   int * pValue
);
```

### <a name="parameters"></a>Parametreler

*pValue*<br/>
**_Doserrno** genel makrosunun geçerli değeriyle doldurulacak bir tamsayıya yönelik bir işaretçi.

## <a name="return-value"></a>Dönüş Değeri

**_Get_doserrno** başarılı olursa, sıfır döndürür; başarısız olursa, bir hata kodu döndürür. *PValue* **null**ise, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlev **errno** ' ı **EINVAL** olarak ayarlar ve **EINVAL**döndürür.

## <a name="remarks"></a>Açıklamalar

**_Doserrno** genel makrosu, işlem yürütme başlamadan önce CRT başlatma sırasında sıfır olarak ayarlanır. Bu, işletim sistemi hatası döndüren herhangi bir sistem düzeyi işlev çağrısıyla döndürülen işletim sistemi hata değerine ayarlanır ve yürütme sırasında hiçbir şekilde sıfıra sıfırlanmaz. Bir işlev tarafından döndürülen hata değerini denetlemek için kod yazdığınızda, işlev çağrısından önce [_set_doserrno](set-doserrno.md) kullanarak her zaman **_doserrno** ' ı temizleyin. Başka bir işlev çağrısı **_doserrno**'nın üzerine yazabileceğinden, işlev çağrısından hemen sonra **_get_doserrno** kullanarak değeri denetleyin.

Taşınabilir hata kodları için **_get_doserrno** yerine [_get_errno](get-errno.md) önerilir.

**_Doserrno** 'nun olası değerleri errno. \<h > içinde tanımlanmıştır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_get_doserrno**|\<Stdlib. h >, \<cstdlib > (C++)|\<errno. h >, \<cerrno > (C++)|

**_get_doserrno** bir Microsoft uzantısıdır. Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[_set_doserrno](set-doserrno.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
