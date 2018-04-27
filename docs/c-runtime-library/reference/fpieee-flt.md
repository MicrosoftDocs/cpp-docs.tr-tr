---
title: _fpieee_flt | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _fpieee_flt function
- exception handling, floating-point
- floating-point exception handling
- fpieee_flt function
ms.assetid: 2bc4801e-0eed-4e73-b518-215da8cc9740
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: da55d2940f38a90dfa5c69d71d394e865bb3b4c0
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="fpieeeflt"></a>_fpieee_flt

IEEE kayan nokta özel durumlar için kullanıcı tanımlı tuzak işleyiciyi çağırır.

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
Windows NT özel durum bilgileri yapısına yönelik işaretçinin.

*işleyici*<br/>
Kullanıcının IEEE tuzak işleyici yordamına yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Dönüş değerini **_fpieee_flt** tarafından döndürülen değer *işleyici*. IEEE filtre yordamı, bu nedenle, kullanılabilir bir yapılandırılmış özel durum işleme (SEH) mekanizması yan tümcesi dışında.

## <a name="remarks"></a>Açıklamalar

**_Fpieee_flt** işlevi IEEE kayan nokta özel durumlar için kullanıcı tanımlı tuzak işleyiciyi çağırır ve tüm ilgili bilgiler sağlar. Bu yordam, gerekli olduğunda, kendi IEEE özel durum işleyici çağırır SEH mekanizması içinde bir özel durum filtresi olarak görev yapar.

**_Fpıeee_record** Fpieee.h içinde tanımlanan yapısı, bir IEEE kayan nokta özel durum ilgili bilgiler içerir. Bu yapı kullanıcı tanımlı yakalama işleyicisi tarafından geçirilir **_fpieee_flt**.

|_Fpıeee_record alan|Açıklama|
|----------------------------|-----------------|
|**RoundingMode**<br/>**Duyarlılık**|Bunlar **imzasız** **int** alanları özel durum oluştu anda kayan nokta ortamı hakkında bilgi içerir.|
|**işlemi**|Bu **imzasız** **int** alan yakalama neden işlemi türünü belirtir. Bir karşılaştırma türündeyse (**_FpCodeCompare**), özel birini sağlayabilir **_FPIEEE_COMPARE_RESULT** değerleri (Fpieee.h içinde tanımlanan) **Result.Value** alan. Dönüştürme türü (**_FpCodeConvert**) yakalama bir kayan nokta dönüştürme işlemi sırasında oluştuğunu gösterir. Bakabilirsiniz **Operand1** ve **sonuç** türleri dönüştürme yapılmaya çalışılan türü belirlenemedi.|
|**operand1**<br/>**operand2**<br/>**Sonuç**|Bunlar **_FPIEEE_VALUE** yapıları belirtmek türlerini ve değerlerini işlenenler ve önerilen sonucu. Bu alanların her yapısını içerir:<br /><br /> **OperandValid** - yanıt veren değerinin geçerli olup olmadığını belirten bayrak.<br />**Biçim** -karşılık gelen değerin veri türü. Biçim türü, karşılık gelen değerle geçerli olmasa bile döndürdü.<br />**Değer** -sonuç veya işlenen veri değeri.|
|**Nedeni**<br/>**Etkinleştir**<br/>**Status**|**_FPIEEE_EXCEPTION_FLAGS** kayan nokta özel durum türü başına tek bit alanı içerir. Bu alanlar ve için sağlanan özel durumlar maskelemek için kullanılan bağımsız değişkenler arasındaki ilişkiyi yoktur [_controlfp](control87-controlfp-control87-2.md). Her bitin tam anlamını bağlama bağlıdır:<br /><br /> **Neden** -her bit ayarlamak gerçekleşmesine neden olan belirli bir özel durum belirtir.<br />**Etkinleştirme** -her bit ayarlamak belirli özel durum şu anda maskelenmemiş olduğunu gösterir.<br />**Durum** -her bit ayarlamak belirli özel durum şu anda beklemede olduğunu gösterir. Bu tarafından maskelenen çünkü oluşturuldu olmayan özel durumları içerir **_controlfp**.|

Bunları etkinleştirdiğinizde devre dışı bırakılmış özel durumları oluşturulur. Bu kullanırken tanımsız davranışlara neden olabilir **_fpieee_flt** bir özel durum filtresi olarak. Her zaman çağrısı [_clearfp](clear87-clearfp.md) kayan nokta özel durumları etkinleştirmeden önce.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fpieee_flt**|\<fpieee.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
