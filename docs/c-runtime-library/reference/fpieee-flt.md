---
title: _fpieee_flt
ms.date: 04/05/2018
apiname:
- _fpieee_flt
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
- fpieee_flt
- _fpieee_flt
helpviewer_keywords:
- _fpieee_flt function
- exception handling, floating-point
- floating-point exception handling
- fpieee_flt function
ms.assetid: 2bc4801e-0eed-4e73-b518-215da8cc9740
ms.openlocfilehash: 9a49ec403b1cb95407b0a366accf1d9374d9cb22
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50458623"
---
# <a name="fpieeeflt"></a>_fpieee_flt

IEEE kayan nokta özel durumları için bir kullanıcı tanımlı yakalama işleyici çağırır.

## <a name="syntax"></a>Sözdizimi

```C
int _fpieee_flt(
   unsigned long excCode,
   struct _EXCEPTION_POINTERS *excInfo,
   int handler(_FPIEEE_RECORD *)
);
```

### <a name="parameters"></a>Parametreler

*excCode*<br/>
Özel durum kodu.

*excInfo*<br/>
Windows NT özel durum bilgileri yapısına yönelik işaretçi.

*İşleyici*<br/>
Kullanıcının IEEE yakalama işleyici rutinini işaretçisi.

## <a name="return-value"></a>Dönüş Değeri

Dönüş değeri **_fpieee_flt** tarafından döndürülen değer *işleyici*. IEEE filtre yordamı, bu nedenle, kullanılabilir bir yapılandırılmış özel durum işleme (SEH) mekanizmasını yan tümcesi dışında.

## <a name="remarks"></a>Açıklamalar

**_Fpieee_flt** işlevi IEEE kayan nokta özel durumları için bir kullanıcı tanımlı yakalama işleyicisine çağırır ve tüm ilgili bilgiler sağlar. Bu yordam, gerektiğinde kendi IEEE özel durum işleyici çağırır SEH mekanizması içinde bir özel durum filtresi olarak görev yapar.

**_Fpıeee_record** Fpieee.h içinde tanımlanan yapısı, bir IEEE kayan nokta özel durumuyla ilgili bilgileri içerir. Bu yapı tarafından kullanıcı tanımlı yakalama işleyicisine geçirilir **_fpieee_flt**.

|_Fpıeee_record alan|Açıklama|
|----------------------------|-----------------|
|**RoundingMode**<br/>**Duyarlık**|Bunlar **işaretsiz** **int** alanları oluşan özel durum zaman kayan nokta ortamı hakkında bilgi içerir.|
|**İşlemi**|Bu **işaretsiz** **int** alan yakalama nedeniyle işlem türünü belirtir. Türü bir karşılaştırma ise (**_FpCodeCompare**), özel sağlayabilirsiniz **_FPIEEE_COMPARE_RESULT** değerleri (Fpieee.h içinde tanımlandığı şekilde) **Result.Value** alan. Dönüştürme türü (**_FpCodeConvert**) yakalama bir kayan nokta dönüştürme işlemi sırasında oluştuğunu gösterir. Bakabilirsiniz **işlenen1** ve **sonucu** denenen bir dönüştürme türünü belirlemek için türleri.|
|**İşlenen1**<br/>**İşlenen2**<br/>**Sonuç**|Bunlar **_FPIEEE_VALUE** türlerini ve değerlerini önerilen sonucu işlenenler ve yapıları gösterir. Her yapı, bu alanları içerir:<br /><br /> **OperandValid** - yanıt veren değerinin geçerli olup olmadığını belirten bayrak.<br />**Biçim** -ilgili değerin veri türü. Buna karşılık gelen değer, geçerli olmasa bile biçim türü döndürdü.<br />**Değer** -sonuç ya da işlenen veri değeri.|
|**Nedeni**<br/>**Enable**<br/>**Status**|**_FPIEEE_EXCEPTION_FLAGS** kayan nokta özel durum türüne göre bir bit alanı içerir. Bu alanlar ve sağlanan özel durumlarını maskelemek için kullanılan bağımsız değişkenler arasındaki ilişkiyi yoktur [_controlfp](control87-controlfp-control87-2.md). Her bitin tam anlamı bağlam üzerinde bağlıdır:<br /><br /> **Neden** -her set bit gerçekleşmesine neden olan belirli özel durum belirtir.<br />**Etkinleştirme** -her set bit belirli özel durum şu anda maskelenmemiş belirtir.<br />**Durum** -her set bit belirli özel durum şu anda beklemede olduğunu gösterir. Bu tarafından maskelenen çünkü gündeme gelmiş değil özel durumları içerir **_controlfp**.|

Bunları etkinleştirmek, devre dışı bırakılmış bekleyen özel durumlar harekete geçirilir. Bu kullanırken tanımsız davranışlara neden olabilir **_fpieee_flt** özel durum filtresi olarak. Her zaman çağrı [_clearfp](clear87-clearfp.md) kayan nokta özel durumlarını etkinleştirmeden önce.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fpieee_flt**|\<fpieee.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_fpieee.c
// This program demonstrates the implementation of
// a user-defined floating-point exception handler using the
// _fpieee_flt function.

#include <fpieee.h>
#include <excpt.h>
#include <float.h>
#include <stddef.h>

int fpieee_handler( _FPIEEE_RECORD * );

int fpieee_handler( _FPIEEE_RECORD *pieee )
{
   // user-defined ieee trap handler routine:
   // there is one handler for all
   // IEEE exceptions

   // Assume the user wants all invalid
   // operations to return 0.

   if ((pieee->Cause.InvalidOperation) &&
       (pieee->Result.Format == _FpFormatFp32))
   {
        pieee->Result.Value.Fp32Value = 0.0F;

        return EXCEPTION_CONTINUE_EXECUTION;
   }
   else
      return EXCEPTION_EXECUTE_HANDLER;
}

#define _EXC_MASK    \
    _EM_UNDERFLOW  + \
    _EM_OVERFLOW   + \
    _EM_ZERODIVIDE + \
    _EM_INEXACT

int main( void )
{
   // ...

   __try {
      // unmask invalid operation exception
      _controlfp_s(NULL, _EXC_MASK, _MCW_EM);

      // code that may generate
      // fp exceptions goes here
   }
   __except ( _fpieee_flt( GetExceptionCode(),
                GetExceptionInformation(),
                fpieee_handler ) ){

      // code that gets control

      // if fpieee_handler returns
      // EXCEPTION_EXECUTE_HANDLER goes here

   }

   // ...
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[_control87, _controlfp, \__control87_2](control87-controlfp-control87-2.md)<br/>
[_controlfp_s](controlfp-s.md)<br/>
