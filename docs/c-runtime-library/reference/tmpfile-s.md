---
title: tmpfile_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- tmpfile_s
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
f1_keywords:
- tmpfile_s
dev_langs:
- C++
helpviewer_keywords:
- temporary files
- tmpfile_s function
- temporary files, creating
ms.assetid: 50879c69-215e-425a-a2a3-8b5467121eae
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4d9ac079ce833f65a4a2add57bbc0be93c97902e
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="tmpfiles"></a>tmpfile_s
Geçici bir dosya oluşturur. Bir sürümüdür [tmpfile](../../c-runtime-library/reference/tmpfile.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
errno_t tmpfile_s(  
   FILE** pFilePtr  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [out] `pFilePtr`  
 Bir akış için oluşturulan işaretçi adresini depolamak için bir işaretçi adresi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, 0 döndürür hatasında bir hata kodu.  
  
### <a name="error-conditions"></a>Hata koşulları  
  
|`pFilePtr`|**Dönüş değeri**|**İçeriği**  `pFilePtr`|  
|----------------|----------------------|---------------------------------|  
|`NULL`|`EINVAL`|değiştirilmedi|  
  
 Yukarıdaki parametre doğrulama hatası oluşursa geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa `errno` ayarlanır `EINVAL` ve dönüş değeri `EINVAL`.  
  
## <a name="remarks"></a>Açıklamalar  
 `tmpfile_s` İşlevi geçici bir dosya oluşturur ve bu akışa bir işaretçi yerleştirir `pFilePtr` bağımsız değişkeni. Geçici dosya kök dizininde oluşturulur. Kök dışında bir dizinde geçici bir dosya oluşturmak için kullanın [tmpnam_s](../../c-runtime-library/reference/tmpnam-s-wtmpnam-s.md) veya [tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) birlikte [fopen](../../c-runtime-library/reference/fopen-wfopen.md).  
  
 Dosya açılamıyor, `tmpfile_s` Yazar `NULL` için `pFilePtr` parametresi. Program normalde veya sonlandırıldığında dosya kapalı olduğunda bu geçici dosya otomatik olarak silinir `_rmtmp` geçerli çalışma dizini değişmeyen varsayarak, adı verilir. Geçici dosya olarak açıldığında `w+b` (ikili okuma/yazma) modu.  
  
 Hata meydana gelebilir dener birden fazla `TMP_MAX_S` (STDIO bakın. H) aramaları `tmpfile_s.`  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`tmpfile_s`|\<stdio.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
> [!NOTE]
>  Bu örnek, Windows Vista üzerinde çalıştırmak için yönetici ayrıcalıkları gerektirir.  
  
```  
// crt_tmpfile_s.c  
// This program uses tmpfile_s to create a  
// temporary file, then deletes this file with _rmtmp.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char tempstring[] = "String to be written";  
   int  i;  
   errno_t err;  
  
   // Create temporary files.  
   for( i = 1; i <= 3; i++ )  
   {  
      err = tmpfile_s(&stream);  
      if( err )  
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