---
title: tmpfile | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: tmpfile
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords: tmpfile
dev_langs: C++
helpviewer_keywords:
- temporary files
- tmpfile function
- temporary files, creating
ms.assetid: c4a4dc24-70da-438d-ae4e-98352d88e375
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b4e6600eda1bae67edaa531d5af05033d1448d8a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="tmpfile"></a>tmpfile
Geçici bir dosya oluşturur. Daha güvenli bir sürümü olmadığından bu işlev kullanım dışıdır; bkz: [tmpfile_s](../../c-runtime-library/reference/tmpfile-s.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
FILE *tmpfile( void );  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, `tmpfile` akış işaretçi döndürür. Aksi takdirde, döndürür bir `NULL` işaretçi.  
  
## <a name="remarks"></a>Açıklamalar  
 `tmpfile` İşlevi geçici bir dosya oluşturur ve bu akışa bir işaretçi döndürür. Geçici dosya kök dizininde oluşturulur. Kök dışında bir dizinde geçici bir dosya oluşturmak için kullanın [tmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) veya [tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) birlikte [fopen](../../c-runtime-library/reference/fopen-wfopen.md).  
  
 Dosya açılamıyor, `tmpfile` döndüren bir `NULL` işaretçi. Program normalde veya sonlandırıldığında dosya kapalı olduğunda bu geçici dosya otomatik olarak silinir `_rmtmp` geçerli çalışma dizini değişmeyen varsayarak, adı verilir. Geçici dosya olarak açıldığında `w+b` (ikili okuma/yazma) modu.  
  
 Birden çok TMP_MAX çalışırsanız hatası meydana gelebilir (STDIO bakın. H) aramaları `tmpfile`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`tmpfile`|\<stdio.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
> [!NOTE]
>  Bu örnek, Windows Vista üzerinde çalıştırmak için yönetici ayrıcalıkları gerektirir.  
  
```  
// crt_tmpfile.c  
// compile with: /W3  
// This program uses tmpfile to create a  
// temporary file, then deletes this file with _rmtmp.  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   int  i;  
  
   // Create temporary files.  
   for( i = 1; i <= 3; i++ )  
   {  
      if( (stream = tmpfile()) == NULL ) // C4996  
      // Note: tmpfile is deprecated; consider using tmpfile_s instead  
         perror( "Could not open new temporary file\n" );  
      else  
         printf( "Temporary file %d was created\n", i );  
   }  
  
   // Remove temporary files.  
   printf( "%d temporary files deleted\n", _rmtmp() );  
}  
```  
  
```Output  
Temporary file 1 was created  
Temporary file 2 was created  
Temporary file 3 was created  
3 temporary files deleted  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış g/ç](../../c-runtime-library/stream-i-o.md)   
 [_rmtmp](../../c-runtime-library/reference/rmtmp.md)   
 [_tempnam, _wtempnam, tmpnam, _wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)