---
title: _fpieee_flt
ms.date: 04/05/2018
api_name:
- _fpieee_flt
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
- fpieee_flt
- _fpieee_flt
helpviewer_keywords:
- _fpieee_flt function
- exception handling, floating-point
- floating-point exception handling
- fpieee_flt function
ms.assetid: 2bc4801e-0eed-4e73-b518-215da8cc9740
ms.openlocfilehash: 8835a3184300f1c56f1123a09aa48cd34a387c87
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957023"
---
# <a name="_fpieee_flt"></a>_fpieee_flt

IEEE kayan nokta özel durumları için Kullanıcı tanımlı bir tuzak işleyicisi çağırır.

## <a name="syntax"></a>Sözdizimi

```C
int _fpieee_flt(
   unsigned long excCode,
   struct _EXCEPTION_POINTERS *excInfo,
   int handler(_FPIEEE_RECORD *)
);
```

### <a name="parameters"></a>Parametreler

*Tüketim kodu*<br/>
Özel durum kodu.

*excInfo*<br/>
Windows NT özel durum bilgileri yapısına yönelik işaretçi.

*Iy*<br/>
Kullanıcının IEEE tuzak-işleyici yordamına yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

**_Fpieee_flt** dönüş değeri *işleyici*tarafından döndürülen değerdir. Bu nedenle, IEEE filtresi yordamı yapılandırılmış bir özel durum işleme (SEH) mekanizmasının except yan tümcesinde kullanılabilir.

## <a name="remarks"></a>Açıklamalar

**_Fpieee_flt** IşLEVI, IEEE kayan nokta özel durumları için Kullanıcı tanımlı bir tuzak işleyicisi çağırır ve ilgili tüm bilgileri sağlar. Bu yordam, gerektiğinde kendi IEEE özel durum işleyicinizi çağıran SEH mekanizmasında özel durum filtresi görevi görür.

Fpieee. h içinde tanımlanan **_Fpieee_record** yapısı, bir IEEE kayan nokta özel durumu ile ilgili bilgiler içerir. Bu yapı, **_fpieee_flt**tarafından Kullanıcı tanımlı tuzak işleyicisine geçirilir.

|_FPIEEE_RECORD alanı|Açıklama|
|----------------------------|-----------------|
|**RoundingMode**<br/>**Duyarlılık**|Bu **imzasız** **int** alanları, özel durumun gerçekleştiği sırada kayan nokta ortamı hakkında bilgiler içerir.|
|**İşlem**|Bu **işaretsiz** **int** alanı, tuzağa neden olan işlem türünü gösterir. Tür bir karşılaştırma ( **_Fpcodecompare**) Ise, **Result. Value** alanındaki özel **_Fpieee_compare_result** değerlerinden birini (fpieee. h içinde tanımlandığı gibi) sağlayabilirsiniz. Dönüştürme türü ( **_Fpcodeconvert**), bir kayan nokta dönüştürme işlemi sırasında yakalamanın oluştuğunu belirtir. Denenen dönüştürme türünü öğrenmek için **Operand1** ve **sonuç** türlerine bakabilirsiniz.|
|**Operand1**<br/>**İşlenen2**<br/>**Sonuç**|Bu **_Fpieee_value** yapıları, önerilen sonucun ve işlenenlerinin türlerini ve değerlerini gösterir. Her yapı şu alanları içerir:<br /><br /> Yanıt veren değerin geçerli olup olmadığını belirten **ılandvalid** -Flag.<br />**Biçim** -karşılık gelen değerin veri türü. Biçim türü, karşılık gelen değer geçerli olmasa bile döndürülebilir.<br />**Değer** -sonuç veya işlenen veri değeri.|
|**Nedeni**<br/>**Enable**<br/>**Status**|**_Fpieee_exception_flags** kayan nokta özel durumu türü başına bir bit alanı içeriyor. Bu alanlar ve [_controlfp](control87-controlfp-control87-2.md)için sağlanan özel durumları maskelemek için kullanılan bağımsız değişkenler arasında bir yazışmalar vardır. Her bitin tam anlamı bağlama göre değişir:<br /><br /> **Neden** -her küme biti, oluşturulan özel durumu gösterir.<br />**Etkinleştir** -her küme bit, belirli bir özel durumun maskelenmemiş olduğunu gösterir.<br />**Durum** -her küme biti, belirli bir özel durumun şu anda beklemede olduğunu gösterir. Bu, **_controlfp**tarafından maskelendikleri için, desteklenmeyen özel durumları içerir.|

Devre dışı bırakılan bekleyen özel durumlar, bunları etkinleştirdiğinizde tetiklenir. Bu, özel durum filtresi olarak **_fpieee_flt** kullanılırken tanımsız davranışa neden olabilir. Kayan nokta özel durumlarını etkinleştirmeden önce her zaman [_clearfp](clear87-clearfp.md) 'yi çağırın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fpieee_flt**|\<fpieee. h >|

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
