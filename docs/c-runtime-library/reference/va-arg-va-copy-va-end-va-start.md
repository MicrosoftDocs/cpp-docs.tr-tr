---
title: va_arg, va_copy, va_end, va_start | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- va_arg
- va_end
- va_copy
- va_start
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
apitype: DLLExport
f1_keywords:
- va_arg
- va_start
- va_list
- va_alist
- va_dcl
- va_copy
- va_end
dev_langs: C++
helpviewer_keywords:
- variable argument lists, accessing
- va_start macro
- va_arg macro
- va_end macro
- arguments [C++], argument lists
- va_list macro
- va_dcl macro
- va_alist macro
- va_copy macro
ms.assetid: a700dbbd-bfe5-4077-87b6-3a07af74a907
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4dc911bfd08781240eaaa73492b61278348bd790
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="vaarg-vacopy-vaend-vastart"></a>va_arg, va_copy, va_end, va_start
Değişken bağımsız değişken listeleri erişir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
type va_arg(  
   va_list arg_ptr,  
   type   
);
void va_copy(  
   va_list dest,  
   va_list src  
); // (ISO C99 and later)  
void va_end(  
   va_list arg_ptr   
);  
void va_start(  
   va_list arg_ptr,  
   prev_param   
); // (ANSI C89 and later)  
void va_start(  
   arg_ptr   
);  // (deprecated Pre-ANSI C89 standardization version)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `type`  
 Alınacak bağımsız değişken türü.  
  
 `arg_ptr`  
 Bağımsız değişken listesiyle işaretçi.  
  
 `dest`  
 Gelen başlatılması için bağımsız değişkenlerin listesini işaretçi`src`  
  
 `src`  
 Başlatılmış kopyalamak için bağımsız değişkenlerin listesini işaretçi `dest`.  
  
 `prev_param`  
 İlk isteğe bağlı bağımsız değişkeni önce gelen bir parametre.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `va_arg`Geçerli bağımsız değişkeni döndürür. `va_copy`, `va_start` ve `va_end` değer döndürmüyor.  
  
## <a name="remarks"></a>Açıklamalar  
 `va_arg`, `va_copy`, `va_end`, Ve `va_start` makroları işlev değişken sayıda bağımsız değişken alır, bir işlev bağımsız değişkenleri erişmek için taşınabilir bir yol sağlar. Makrolar iki sürümü vardır: STDARG içinde tanımlı makrolar. H ISO C99 standart uygun; VARARGS içinde tanımlı makrolar. H kullanım dışı bırakılmıştır, ancak standart ANSI C89 önce yazılmış kodun ile geriye dönük uyumluluk için korunur.  
  
 Bu makroları işlev gerekli bağımsız değişken sayısı isteğe bağlı bağımsız değişkenler tarafından izlenen, sabit sayıda alır varsayalım. Gerekli bağımsız işlevi için parametre normal olarak bildirilir ve parametre adları erişilebilir. İsteğe bağlı bağımsız değişkenler STDARG makrolarındaki erişilir. Y (veya VARARGS. H ANSI C89 standart önce yazılmış kodun için), hangi ilk isteğe bağlı bağımsız değişken bağımsız değişken listesinde bir işaretçi kümelerini listeden bağımsız değişkenleri alır ve bağımsız değişkeni işlem tamamlandığında, işaretçi sıfırlar.  
  
 STDARG içinde tanımlanan C Standart makroları. H, aşağıdaki gibi kullanılır:  
  
-   `va_start`Ayarlar `arg_ptr` işlevine geçirilen bağımsız değişken listesiyle ilk isteğe bağlı bağımsız değişkeni için. Bağımsız değişken `arg_ptr` olmalıdır `va_list` türü. Bağımsız değişken `prev_param` ilk isteğe bağlı bağımsız değişken bağımsız değişken listesinde hemen önce gelen gerekli parametre adı. Varsa `prev_param` bildirilen register depolama sınıfı ile makro davranışı tanımlanmadı. `va_start`önce kullanılmalıdır `va_arg` ilk kez kullanılır.  
  
-   `va_arg`bir değeri alır `type` tarafından verilen bir konumdan `arg_ptr`ve artışlarla `arg_ptr` boyutunu kullanarak bir sonraki bağımsız değişken listesinde işaret edecek şekilde `type` sonraki bağımsız değişken başladığı belirlemek için. `va_arg`olabilir bağımsız değişkenleri listesinden almak üzere işlevindeki herhangi kaç kez kullanılır.  
  
-   `va_copy`bağımsız değişkenler listesi kopyasını geçerli durumunda oluşturur. `src` Parametresi zaten başlatılmalı ile `va_start`; bunu ile güncelleştirilmemiş olabilir `va_arg` çağırır ancak ile sıfırlanmış gerekir değil `va_end`. Tarafından alınan sonraki bağımsız değişken `va_arg` gelen `dest` alınır sonraki bağımsız değişkeni ile aynı `src`.  
  
-   Tüm bağımsız değişkenler aldıktan sonra `va_end` işaretçisine sıfırlar **NULL**. `va_end`ile başlatılan her bağımsız değişken listesi üzerinde çağrılmalıdır `va_start` veya `va_copy` önce işlevi döndürür.  
  
> [!NOTE]
>  VARARGS makrolarındaki. H kullanım dışıdır ve olduğundan yalnızca geriye dönük uyumluluk ANSI C89 standart önce yazılmış kodun ile korunur. Diğer durumlarda, STDARGS makrolar kullanın. H.  
  
 Ne zaman bunlar derlenen kullanarak [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md), bu makroları kullanan programlar, yerel ve ortak dil çalışma zamanı (CLR) türü sistemleri arasındaki farklar nedeniyle beklenmeyen sonuçlar oluşturabilir. Bu program göz önünde bulundurun:  
  
```  
#include <stdio.h>  
#include <stdarg.h>  
  
void testit (int i, ...)  
{  
    va_list argptr;  
    va_start(argptr, i);  
  
    if (i == 0)  
    {  
        int n = va_arg(argptr, int);  
        printf("%d\n", n);  
    }  
    else  
    {  
        char *s = va_arg(argptr, char*);  
        printf("%s\n", s);  
    }  

    va_end(argptr);  
}  
  
int main()  
{  
    testit(0, 0xFFFFFFFF); // 1st problem: 0xffffffff is not an int  
    testit(1, NULL);       // 2nd problem: NULL is not a char*  
}  
```  
  
 Dikkat `testit` olmalıdır, ikinci parametre bekliyor bir `int` veya `char*`. 0xffffffff geçirilen bağımsız değişkenler (bir `unsigned int`değil bir `int`) ve `NULL` (gerçekte bir `int`değil bir `char*`). Program için yerel koda derlenmiş olduğunda bu çıkışı üretir:  
  
```Output  
-1  
  
(null)  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<stdio.h > ve \<stdarg.h >  
  
 **Kullanım dışı üstbilgisi:** \<varargs.h >  
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_va.c  
/* Compile with: cl /W3 /Tc crt_va.c  
 * The program below illustrates passing a variable  
 * number of arguments using the following macros:  
 *      va_start            va_arg              va_copy  
 *      va_end              va_list  
 */  
  
#include <stdio.h>  
#include <stdarg.h>  
#include <math.h>  
  
double deviation(int first, ...);  
  
int main( void )  
{  
    /* Call with 3 integers (-1 is used as terminator). */  
    printf("Deviation is: %f\n", deviation(2, 3, 4, -1 ));  
  
    /* Call with 4 integers. */  
    printf("Deviation is: %f\n", deviation(5, 7, 9, 11, -1));  
  
    /* Call with just -1 terminator. */  
    printf("Deviation is: %f\n", deviation(-1));  
}  
  
/* Returns the standard deviation of a variable list of integers. */  
double deviation(int first, ...)  
{  
    int count = 0, i = first;  
    double mean = 0.0, sum = 0.0;  
    va_list marker;  
    va_list copy;  
  
    va_start(marker, first);     /* Initialize variable arguments. */  
    va_copy(copy, marker);       /* Copy list for the second pass */  
    while (i != -1)  
    {  
        sum += i;  
        count++;  
        i = va_arg(marker, int);  
    }  
    va_end(marker);              /* Reset variable argument list. */  
    mean = sum ? (sum / count) : 0.0;  
  
    i = first;                  /* reset to calculate deviation */  
    sum = 0.0;  
    while (i != -1)  
    {  
        sum += (i - mean)*(i - mean);  
        i = va_arg(copy, int);  
    }  
    va_end(copy);               /* Reset copy of argument list. */  
    return count ? sqrt(sum / count) : 0.0;  
}  
  
```  
  
## <a name="output"></a>Çıkış  
  
```Output  
Deviation is: 0.816497  
Deviation is: 2.236068  
Deviation is: 0.000000  
  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağımsız değişken erişimi](../../c-runtime-library/argument-access.md)   
 [vfprintf, _vfprintf_l, vfwprintf, _vfwprintf_l](../../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)