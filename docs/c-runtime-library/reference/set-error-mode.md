---
title: _set_error_mode
ms.date: 11/04/2016
apiname:
- _set_error_mode
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
- set_error_mode
- _set_error_mode
helpviewer_keywords:
- _set_error_mode function
- set_error_mode function
ms.assetid: f0807be5-73d1-4a32-a701-3c9bdd139c5c
ms.openlocfilehash: 8c95ed45423b791a688f05ea30f48e188826a797
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50502316"
---
# <a name="seterrormode"></a>_set_error_mode

Değiştirir **__error_mode** nereye yazdığını programın sonlandırılması bir hata için bir hata iletisi C çalışma zamanı varsayılan dışındaki bir konumu belirlemek için.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _set_error_mode(
   int mode_val
);
```

### <a name="parameters"></a>Parametreler

*mode_val*<br/>
Hedef hata iletileri.

## <a name="return-value"></a>Dönüş Değeri

Bir hata oluşursa eski bir ayar veya -1 döndürür.

## <a name="remarks"></a>Açıklamalar

Hata çıkış havuzu değerini ayarlayarak denetimleri **__error_mode**. Örneğin, standart hata çıktıyı yönlendirin veya kullanın **MessageBox** API.

*Mode_val* parametre aşağıdaki değerlerden biri olarak ayarlanabilir.

|Parametre|Açıklama|
|---------------|-----------------|
|**_OUT_TO_DEFAULT**|Hata havuz tarafından belirlenir **__app_type**.|
|**_OUT_TO_STDERR**|Hata havuz standart bir hatadır.|
|**_OUT_TO_MSGBOX**|Hata havuz, bir ileti kutusudur.|
|**_REPORT_ERRMODE**|Geçerli rapor **__error_mode** değeri.|

Bu listedeki dışında bir değer geçtiyse, geçersiz parametre açıklandığı gibi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **_set_error_mode** ayarlar **errno** için **EINVAL** ve -1 döndürür.

Birlikte kullanıldığında bir [assert](assert-macro-assert-wassert.md), **_set_error_mode** başarısız ifade iletişim kutusunda görüntüler ve seçme seçeneği sunar **Yoksay** destesinin düğmesi program çalışmaya devam eder.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_set_error_mode**|\<stdlib.h >|

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
