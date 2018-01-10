---
title: memcpy, wmemcpy | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- memcpy
- wmemcpy
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
- wmemcpy
- memcpy
dev_langs: C++
helpviewer_keywords:
- wmemcpy function
- memcpy function
ms.assetid: 34abb90b-bffb-46dc-a2f3-a5e9940839d6
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 312e4a63803f3661799c6ad832fdfee22af876c9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="memcpy-wmemcpy"></a>memcpy, wmemcpy
Arabellekler arasında kopyaları bayt sayısı. Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [memcpy_s, wmemcpy_s](../../c-runtime-library/reference/memcpy-s-wmemcpy-s.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void *memcpy(  
   void *dest,  
   const void *src,  
   size_t count   
);  
wchar_t *wmemcpy(  
   wchar_t *dest,  
   const wchar_t *src,  
   size_t count  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dest`  
 Yeni bir arabellek.  
  
 `src`  
 Kopyalanacak arabelleği.  
  
 `count`  
 Kopyalamak için karakter sayısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Değeri `dest`.  
  
## <a name="remarks"></a>Açıklamalar  
 `memcpy`kopya `count` baytlar `src` için `dest`; `wmemcpy` kopyaları `count` geniş karakterler (iki bayt cinsinden). Kaynak ve hedef çakışma varsa, davranışını `memcpy` tanımlanmadı. Kullanım `memmove` çakışan bölgeler işlemek için.  
  
> [!IMPORTANT]
>  Kaynak arabelleği daha büyük veya boyut hedef arabelleği aynı olduğundan emin olun. Daha fazla bilgi için bkz: [önleme arabellek taşmasına neden](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
> [!IMPORTANT]
>  Çok fazla sayıda arabellek taşmaları ve böylece olası güvenlik açıkları, yanlış kullanımı için izlenen olduğundan `memcpy`, bu işlev "Engellenenler" işlevleri arasında güvenlik geliştirme yaşam döngüsü (SDL) tarafından listelenir.  Bazı VC ++ kitaplığı sınıfları kullanmaya devam gözlemleyebilirsiniz `memcpy`.  Ayrıca, VC ++ derleyici iyileştirici bazen için çağrı yayar gözlemleyebilirsiniz `memcpy`.  Visual C++ ürün SDL işlem uygun olarak geliştirilen ve böylece bu Engellenenler işlevi kullanımını yakından değerlendirildikten.  Kitaplık durumunda çağrıları dikkatle arabellek taşmaları bu çağrılar izin verilmiyor emin olmak için scrutinized, bunu kullanın.  Derleyicinin söz konusu olduğunda, bazen belirli kod düzenleri desenini için aynı tanınır `memcpy`ve bu nedenle işlevi çağrısı ile değiştirilir.  Böyle durumlarda, kullanımını `memcpy` özgün daha fazla güvenli değildir yönergeleri olabilirdi; bunlar yalnızca performans olarak ayarlanmış bir çağrı için iyileştirilmiş `memcpy` işlevi.  "Safe" CRT işlevleri kullanımını (bunlar yalnızca yapın, güvenilmez olarak daha zor) güvenliği garanti etmez gibi "Engellenenler" işlevleri kullanımını (yalnızca ihtiyaç güvenliği sağlamak için büyük scrutiny) tehlike garanti etmez.  
>   
>  Çünkü `memcpy` VC ++ derleyici ve kitaplıkları kullanımı bu nedenle dikkatli bir şekilde scrutinized, aksi takdirde SDL ile uyumlu olan kod içinde bu Çağrılara izin verilir.  `memcpy`uygulamanın kaynak kodunda sunulan çağrıları SDL ile uyumlu için kullanan güvenlik uzmanları tarafından gözden aynıdır.  
  
 `memcpy` Ve `wmemcpy` işlevleri yalnızca kullanım dışı varsa sabiti `_CRT_SECURE_DEPRECATE_MEMORY` olan işlevler de kullanım dışı sırayla ekleme deyimi önce tanımlanan, aşağıdaki örnekteki gibi:  
  
```  
#define _CRT_SECURE_DEPRECATE_MEMORY  
#include <memory.h>  
```  
  
 veya  
  
```  
#define _CRT_SECURE_DEPRECATE_MEMORY  
#include <wchar.h>  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`memcpy`|\<Memory.h > veya \<string.h >|  
|`wmemcpy`|\<wchar.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
 Bkz: [memmove](../../c-runtime-library/reference/memmove-wmemmove.md) nasıl kullanılacağına ilişkin bir örnek için `memcpy`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ara bellek düzenlemesi](../../c-runtime-library/buffer-manipulation.md)   
 [_memccpy](../../c-runtime-library/reference/memccpy.md)   
 [memchr'e, wmemchr](../../c-runtime-library/reference/memchr-wmemchr.md)   
 [memcmp, wmemcmp](../../c-runtime-library/reference/memcmp-wmemcmp.md)   
 [memmove, wmemmove](../../c-runtime-library/reference/memmove-wmemmove.md)   
 [memset, wmemset](../../c-runtime-library/reference/memset-wmemset.md)   
 [strcpy_s, wcscpy_s, _mbscpy_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)   
 [strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](../../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)