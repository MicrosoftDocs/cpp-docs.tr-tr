---
title: ___setlc_active_func, ___unguarded_readlc_active_add_func | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- ___setlc_active_func
- ___unguarded_readlc_active_add_func
apilocation:
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr110.dll
- msvcr80.dll
- msvcr120.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- ___unguarded_readlc_active_add_func
- ___setlc_active_func
dev_langs:
- C++
helpviewer_keywords:
- ___setlc_active_func
- ___unguarded_readlc_active_add_func
ms.assetid: 605ec4e3-81e5-4ece-935a-f434768cc702
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 532aac2e47a402ae04ba4d4bf4fcb133c997bd31
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="setlcactivefunc-unguardedreadlcactiveaddfunc"></a>___setlc_active_func, ___unguarded_readlc_active_add_func
KULLANIMDAN KALKTI. CRT yalnızca ikili uyumluluğu korumak için bu iç işlevler dışa aktarır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
int ___setlc_active_func(void);  
int * ___unguarded_readlc_active_add_func(void);  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Döndürülen değer önemli değildir.  
  
## <a name="remarks"></a>Açıklamalar  
 Ancak iç CRT işlevleri `___setlc_active_func` ve `___unguarded_readlc_active_add_func` kullanımdan kalkmıştır ve artık kullanılmayan, bunlar ikili uyumluluğu korumak için CRT kitaplık tarafından verilir. Özgün amacı `___setlc_active_func` şu anda etkin çağrı sayısı döndürülecek olan `setlocale` işlevi. Özgün amacı `___unguarded_readlc_active_add_func` kilitleme olmadan yerel başvurulan işlevlerin sayısını döndürmek için oluştu.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`___setlc_active_func`, `___unguarded_readlc_active_add_func`|yok|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)