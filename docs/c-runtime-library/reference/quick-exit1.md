---
title: quick_exit1 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- quick_exit
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
- quick_exit
- process/quick_exit
- stdlib/quick_exit
dev_langs:
- C++
helpviewer_keywords:
- quick_exit function
ms.assetid: ecfbdae6-01c4-45fa-aaeb-b368e1de2a9c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 30c8ae3290ac4b15247b88b0b2201634e42b560b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="quickexit"></a>quick_exit
Normal program sonlandırma oluşmasına neden olur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
__declspec(noreturn) void quick_exit(  
    int status  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 durum  
 Ana bilgisayar ortamına geçirmek için durum kodu.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `quick_exit` İşlevi çağırıcısına döndüremiyor.  
  
## <a name="remarks"></a>Açıklamalar  
 `quick_exit` İşlevi normal program sonlandırma neden olur. Tarafından kaydedilen hiçbir işlevleri çağıran `atexit`, `_onexit` veya sinyal tarafından kaydedilen işleyicileri `signal` işlevi. Davranış ise tanımsız `quick_exit` birden çok kez veya yoksa adlı `exit` işlevi olarak da adlandırılır.  
  
 `quick_exit` İşlev çağrısı, son giren ilk çıkar (LIFO) sırası, tarafından kaydedilen işlevleri `at_quick_exit`, zaten çağrılır bu işlevler için işlev kayıtlı dışında.  Davranış ise tanımlanmamış bir [longjmp](../../c-runtime-library/reference/longjmp.md) işlevi çağrısında sonlandırmak kayıtlı bir işlevi çağrısı sırasında çağrı yapılır.  
  
 Kayıtlı işlevleri çağrıldıktan sonra `quick_exit` çağırır `_Exit` kullanarak `status` denetim konak ortamına geçirmek için değer.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`quick_exit`|\<Process.h > veya \<stdlib.h >|  
  
 Uyumluluğu hakkında daha fazla bilgi için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Süreç ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)   
 [Durdurma](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [_exec, _wexec işlevleri](../../c-runtime-library/exec-wexec-functions.md)   
 [Çıkış, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_onexit, _onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [_spawn, _wspawn işlevleri](../../c-runtime-library/spawn-wspawn-functions.md)   
 [system, _wsystem](../../c-runtime-library/reference/system-wsystem.md)