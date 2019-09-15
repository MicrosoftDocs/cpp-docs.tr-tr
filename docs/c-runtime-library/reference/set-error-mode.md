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
ms.openlocfilehash: 15a6d72a79f0498fb7d81094ed3595dea1cf444f
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948554"
---
# <a name="_set_error_mode"></a>_set_error_mode

, C çalışma zamanının programı sona erdirmek için bir hata iletisi yazdığı varsayılan olmayan bir konum belirlemesi için **__error_mode** değerini değiştirir.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

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

**__Error_mode**değerini ayarlayarak hata çıkış havuzunu denetler. Örneğin, çıktıyı standart bir hataya yönlendirebilir veya **MessageBox** API 'sini kullanabilirsiniz.

*Mode_val* parametresi aşağıdaki değerlerden birine ayarlanabilir.

|Parametre|Açıklama|
|---------------|-----------------|
|**_OUT_TO_DEFAULT**|Hata havuzu **__app_type**tarafından belirlendi.|
|**_OUT_TO_STDERR**|Hata havuzu standart bir hatadır.|
|**_OUT_TO_MSGBOX**|Hata havuzu bir ileti kutusudur.|
|**_REPORT_ERRMODE**|Geçerli **__error_mode** değerini bildirin.|

Listelenenlerin dışında bir değer geçirildiyse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, **_set_error_mode** **errno** ve **EINVAL** olarak ayarlar ve-1 döndürür.

**_Set_error_mode** , bir [onaylama](assert-macro-assert-wassert.md)ile kullanıldığında, iletişim kutusunda başarısız olan ifadeyi görüntüler ve ardından programı çalıştırmaya devam edebilmeniz için **yoksayma** düğmesini seçme seçeneğini sunar.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_set_error_mode**|\<Stdlib. h >|

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

[assert Makrosu, _assert, _wassert](assert-macro-assert-wassert.md)<br/>
