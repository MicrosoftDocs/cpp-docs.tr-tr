---
title: _set_abort_behavior | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _set_abort_behavior
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
- _set_abort_behavior
- set_abort_behavior
dev_langs: C++
helpviewer_keywords:
- aborting programs
- _set_abort_behavior function
- set_abort_behavior function
ms.assetid: 43918766-e4ba-4b1f-80e8-1a4a910cd452
caps.latest.revision: "26"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: edf31ccddfb9ab2eaa6de226ff4ec7eb09869438
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="setabortbehavior"></a>_set_abort_behavior
Bir program anormal olduğunda gerçekleştirilecek eylemi belirtir.  
  
> [!NOTE]
>  Kullanmayın `abort` kapatmak için işlevi bir [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] uygulamayı dışındaki test veya senaryoları hata ayıklama. Kapatmak için programlı veya UI yolu bir [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] göre uygulama verilmez [Windows 8 uygulama sertifika gereksinimleri](http://go.microsoft.com/fwlink/?LinkId=262889). Daha fazla bilgi için bkz: [uygulama yaşam döngüsü (Windows mağazası uygulamaları)](http://go.microsoft.com/fwlink/?LinkId=262853).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
unsigned int _set_abort_behavior(  
   unsigned int flags,  
   unsigned int mask  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in]`flags`  
 Yeni değeri `abort` bayrakları.  
  
 [in]`mask`  
 İçin maske `abort` ayarlamak için BITS işaretler.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bayrakları eski değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 Var olan iki `abort` bayrakları: `_WRITE_ABORT_MSG` ve `_CALL_REPORTFAULT`. `_WRITE_ABORT_MSG`bir program anormal olduğunda yararlı kısa mesaj yazdırılan olup olmadığını belirler. İleti durumları uygulama çağırdı `abort` işlevi. İleti yazdırmak için varsayılan davranıştır. `_CALL_REPORTFAULT`, varsa, otomatik olarak bir Watson kilitlenme döküm oluşturulur ve ne zaman rapor belirtir `abort` olarak adlandırılır. Varsayılan olarak, kilitlenme döküm raporlama olmayan hata ayıklama derlemelerinde etkindir.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_set_abort_behavior`|\<stdlib.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
  
```C  
// crt_set_abort_behavior.c  
// compile with: /TC  
#include <stdlib.h>  
  
int main()  
{  
   printf("Suppressing the abort message. If successful, this message"  
          " will be the only output.\n");  
   // Suppress the abort message  
   _set_abort_behavior( 0, _WRITE_ABORT_MSG);  
   abort();  
}  
```  
  
```Output  
Suppressing the abort message. If successful, this message will be the only output.  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [durdurma](../../c-runtime-library/reference/abort.md)