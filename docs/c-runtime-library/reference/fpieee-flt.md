---
title: _fpieee_flt | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _fpieee_flt
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
dev_langs: C++
helpviewer_keywords:
- _fpieee_flt function
- exception handling, floating-point
- floating-point exception handling
- fpieee_flt function
ms.assetid: 2bc4801e-0eed-4e73-b518-215da8cc9740
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f2e3f91d2baca3829538d199ce000d56a7be24d4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="fpieeeflt"></a>_fpieee_flt
IEEE kayan nokta özel durumlar için kullanıcı tanımlı tuzak işleyiciyi çağırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _fpieee_flt(   
   unsigned long excCode,  
   struct _EXCEPTION_POINTERS *excInfo,  
   int handler(_FPIEEE_RECORD *)   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `excCode`  
 Özel durum kodu.  
  
 `excInfo`  
 Windows NT özel durum bilgileri yapısına yönelik işaretçinin.  
  
 `handler`  
 Kullanıcının IEEE tuzak işleyici yordamına yönelik işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Dönüş değerini `_fpieee_flt` tarafından döndürülen değer `handler`. IEEE filtre yordamı, bu nedenle, kullanılabilir bir yapılandırılmış özel durum işleme (SEH) mekanizması yan tümcesi dışında.  
  
## <a name="remarks"></a>Açıklamalar  
 `_fpieee_flt` İşlevi IEEE kayan nokta özel durumlar için kullanıcı tanımlı tuzak işleyiciyi çağırır ve tüm ilgili bilgiler sağlar. Bu yordam, gerekli olduğunda, kendi IEEE özel durum işleyici çağırır SEH mekanizması içinde bir özel durum filtresi olarak görev yapar.  
  
 `_FPIEEE_RECORD` Fpieee.h içinde tanımlanan yapısı, bir IEEE kayan nokta özel durum ilgili bilgiler içerir. Bu yapı kullanıcı tanımlı yakalama işleyicisi tarafından geçirilir `_fpieee_flt`.  
  
|_Fpıeee_record alan|Açıklama|  
|----------------------------|-----------------|  
|`unsigned int RoundingMode`, `unsigned int Precision`|Bu alanların özel durum oluştu anda kayan nokta ortamı hakkında bilgi içerir.|  
|`unsigned int Operation`|Yakalamanın neden işlemi türünü belirtir. Bir karşılaştırma türündeyse (`_FpCodeCompare`), özel birini sağlayabilir `_FPIEEE_COMPARE_RESULT` değerleri (Fpieee.h içinde tanımlanan) `Result.Value` alan. Dönüştürme türü (`_FpCodeConvert`) yakalama bir kayan nokta dönüştürme işlemi sırasında oluştuğunu gösterir. Bakabilirsiniz `Operand1` ve `Result` türleri dönüştürme yapılmaya çalışılan türü belirlenemedi.|  
|`_FPIEEE_VALUE Operand1`, `_FPIEEE_VALUE Operand2`, `_FPIEEE_VALUE Result`|Bu yapıları türleri ve önerilen sonuç ve işlenen değerlerini belirtin:<br /><br /> `OperandValid`Yanıt veren değerinin geçerli olup olmadığını belirten bayrak.<br /><br /> `Format`Karşılık gelen değerin veri türü. Biçim türü, karşılık gelen değerle geçerli olmasa bile döndürdü.<br /><br /> `Value`Sonuç veya işlenen veri değeri.|  
|`_FPIEEE_EXCEPTION_FLAGS Cause`, `_FPIEEE_EXCEPTION_FLAGS Enable`, `_FPIEEE_EXCEPTION_FLAGS Status`|Kayan nokta özel durum türünü her bir bit alan _FPIEEE_EXCEPTION_FLAGS içerir.<br /><br /> Bu alanlar ve için sağlanan özel durumlar maskelemek için kullanılan bağımsız değişkenler arasındaki ilişkiyi yoktur [_controlfp](../../c-runtime-library/reference/control87-controlfp-control87-2.md).<br /><br /> Her bitin tam anlamını bağlama bağlıdır:<br /><br /> `Cause`Her bit ayarlamak gerçekleşmesine neden olan belirli bir özel durum belirtir.<br /><br /> `Enable`Her bit ayarlamak belirli özel durum şu anda maskelenmemiş olduğunu gösterir.<br /><br /> `Status`Her bit ayarlamak belirli özel durum şu anda beklemede olduğunu gösterir. Bu tarafından maskelenen çünkü oluşturuldu olmayan özel durumları içerir `_controlfp`.|  
  
 Bunları etkinleştirdiğinizde devre dışı bırakılmış özel durumları oluşturulur. Bu kullanırken tanımsız davranışlara neden olabilir `_fpieee_flt` bir özel durum filtresi olarak. Her zaman çağrısı [_clearfp](../../c-runtime-library/reference/clear87-clearfp.md) kayan nokta özel durumları etkinleştirmeden önce.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|Gerekli başlık|  
|--------------|---------------------|  
|`_fpieee_flt`|\<fpieee.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)   
 [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)   
 [_controlfp_s](../../c-runtime-library/reference/controlfp-s.md)