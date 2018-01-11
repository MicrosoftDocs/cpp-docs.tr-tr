---
title: offsetof makrosu | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
f1_keywords: offsetof
dev_langs: C++
helpviewer_keywords:
- structure members, offset
- offsetof macro
ms.assetid: f3b4eb16-a882-4d38-afc9-eebd976a7352
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d99947615f2f24116f3d9b64e94daba60c848ec4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="offsetof-macro"></a>offsetof makrosu
Uzaklık üyenin üst yapısını baştan alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      size_t offsetof(  
   structName,  
   memberName   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *structName*  
 Ana veri yapısı adı.  
  
 `memberName`  
 Uzaklık belirlemek için ana veri yapısı üye adı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `offsetof`uzaklık belirtilen üye bayt cinsinden üst veri yapısını baştan döndürür. Bit alanları için tanımlı değil.  
  
## <a name="remarks"></a>Açıklamalar  
 `offsetof` Makrosu bayt cinsinden uzaklık döndürür `memberName` tarafından belirtilen yapısı başından itibaren *structName* türünde bir değer olarak `size_t`. Türleriyle belirtebilirsiniz `struct` anahtar sözcüğü.  
  
> [!NOTE]
>  `offsetof`bir işlev değil ve C prototipi kullanarak açıklanan olamaz.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`offsetof`|\<stddef.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bellek Ayırma](../../c-runtime-library/memory-allocation.md)