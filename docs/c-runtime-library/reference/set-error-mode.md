---
title: _set_error_mode
ms.date: 11/04/2016
api_name:
- _set_error_mode
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
- set_error_mode
- _set_error_mode
helpviewer_keywords:
- _set_error_mode function
- set_error_mode function
ms.assetid: f0807be5-73d1-4a32-a701-3c9bdd139c5c
ms.openlocfilehash: c1bb617e0f3792f2ac41d59df13d184423d56a9e
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88562044"
---
# <a name="_set_error_mode"></a>_set_error_mode

C çalışma zamanının programı sona erdirmek için bir hata iletisi yazdığı varsayılan olmayan bir konumu belirlemesi için **__error_mode** değiştirir.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Söz dizimi

```C
int _set_error_mode(
   int mode_val
);
```

### <a name="parameters"></a>Parametreler

*mode_val*<br/>
Hata iletilerinin hedefi.

## <a name="return-value"></a>Dönüş Değeri

Eski ayarı döndürür veya bir hata oluşursa-1.

## <a name="remarks"></a>Açıklamalar

**__Error_mode**değerini ayarlayarak hata çıktı havuzunu denetler. Örneğin, çıktıyı standart bir hataya yönlendirebilir veya **MessageBox** API 'sini kullanabilirsiniz.

*Mode_val* parametresi aşağıdaki değerlerden birine ayarlanabilir.

|Değer|Açıklama|
|---------------|-----------------|
|**_OUT_TO_DEFAULT**|Hata havuzu **__app_type**tarafından belirlenir.|
|**_OUT_TO_STDERR**|Hata havuzu standart bir hatadır.|
|**_OUT_TO_MSGBOX**|Hata havuzu bir ileti kutusudur.|
|**_REPORT_ERRMODE**|Geçerli **__error_mode** değerini bildirin.|

Listelenenlerin dışında bir değer geçirildiyse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, **_set_error_mode** **errno** 'u **EINVAL** olarak ayarlar ve-1 döndürür.

Bir [onaylama](assert-macro-assert-wassert.md)ile birlikte kullanıldığında, **_set_error_mode** iletişim kutusunda başarısız olan ifadeyi görüntüler ve ardından programı çalıştırmaya devam edebilmeniz için **yoksayma** düğmesini seçme seçeneğini sunar.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_set_error_mode**|\<stdlib.h>|

## <a name="example"></a>Örnek

```C
// crt_set_error_mode.c
// compile with: /c
#include <stdlib.h>
#include <assert.h>

int main()
{
   _set_error_mode(_OUT_TO_STDERR);
   assert(2+2==5);
}
```

```Output
Assertion failed: 2+2==5, file crt_set_error_mode.c, line 8

This application has requested the Runtime to terminate it in an unusual way.
Please contact the application's support team for more information.
```

## <a name="see-also"></a>Ayrıca bkz.

[onaylama makrosu, _assert _wassert](assert-macro-assert-wassert.md)<br/>
