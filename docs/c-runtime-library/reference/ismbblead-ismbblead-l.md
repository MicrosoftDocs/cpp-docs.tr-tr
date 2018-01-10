---
title: _ismbblead, _ismbblead_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ismbblead_l
- _ismbblead
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- ismbblead_l
- istlead
- _ismbblead
- _ismbblead_l
- ismbblead
- _istlead
dev_langs: C++
helpviewer_keywords:
- _ismbblead_l function
- ismbblead function
- _ismbblead function
- istlead function
- ismbblead_l function
- _istlead function
ms.assetid: 2abc6f75-ed5c-472e-bfd0-e905a1835ccf
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: acba6047239ee9c63e05666a4bdc685cf40527c3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ismbblead-ismbbleadl"></a>_ismbblead, _ismbblead_l
Birden çok baytlı karakter baytı olup olmadığını belirlemek için bir karakter sınar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _ismbblead(  
   unsigned int c   
);  
int _ismbblead_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `c`  
 Sınanacak tamsayı.  
  
 `locale`  
 Kullanılacak yerel ayar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Sıfır olmayan bir değer döndürür tamsayı `c` birden çok baytlı karakter ilk olarak bayttır.  
  
## <a name="remarks"></a>Açıklamalar  
 Birden çok baytlı karakterler sondaki bayt tarafından izlenen baytı oluşur. Sağlama bayt belirli bir karakter kümesi için belirli bir aralıkta olma yoluyla ayırt edilir. Örneğin, kod sayfası 932 yalnızca, sağlama bayt cinsinden 0x81 - 0x9F ve 0xE0 - 0xFC aralığı.  
  
 `_ismbblead`Geçerli yerel ayar için yerel ayara bağımlı davranışı kullanır. `_ismbblead_l`Bunun yerine geçirilen yerel ayar kullanır ancak bu aynıdır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_istlead`|Her zaman false döndürür|`_ismbblead`|Her zaman false döndürür|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|  
|-------------|---------------------|---------------------|  
|`_ismbblead`|\<Mbctype.h > veya \<mbstring.h >|\<CType.h >, * \<lımıts.h >, \<stdlib.h >|  
|`_ismbblead_l`|\<Mbctype.h > veya \<mbstring.h >|\<CType.h >, * \<lımıts.h >, \<stdlib.h >|  
  
 \*İçin test durumları için bildirim sabitleri.  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bayt sınıflandırması](../../c-runtime-library/byte-classification.md)   
 [_ismbb Yordamları](../../c-runtime-library/ismbb-routines.md)