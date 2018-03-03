---
title: _setjmp3 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _setjmp3
apilocation:
- msvcrt.dll
- msvcr90.dll
- msvcr110.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- setjmp3
- _setjmp3
dev_langs:
- C++
helpviewer_keywords:
- _setjmp3 function
- setjmp3 function
ms.assetid: 6129c2f3-8bac-4fdb-a827-44e1eebba500
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 72bc1e833ddaa72979e25274b7328d8987f62763
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="setjmp3"></a>_setjmp3
İç CRT işlevi. Yeni bir uyarlamasını `setjmp` işlevi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _setjmp3(  
   OUT jmp_buf env,  
   int count,  
   (optional parameters)  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [out]`env`  
 Durum bilgilerini depolamak için arabellek adresi.  
  
 [in]`count`  
 Ek sayısı `DWORD`depolanan bilgilerin s `optional parameters`.  
  
 [in]`optional parameters`  
 Tarafından ek veriler gönderilir `setjmp` iç. İlk `DWORD` ek veri bırakma ve bir kalıcı döndürmek için kullanılan bir işlev işaretçisi durumu kaydedeceksiniz. İkinci `DWORD` geri yüklenmesi deneyin düzeydir. Daha fazla veri genel veri dizisinde kaydedilir `jmp_buf`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Her zaman 0 döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev bir C++ programı kullanmayın. C++ desteklemiyor iç bir işlevdir. Nasıl kullanılacağı hakkında daha fazla bilgi için `setjmp`, bkz: [setjmp/longjmp kullanma](../cpp/using-setjmp-longjmp.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Alfabetik işlev başvurusu](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [setjmp](../c-runtime-library/reference/setjmp.md)