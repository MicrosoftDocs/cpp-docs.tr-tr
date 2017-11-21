---
title: _setjmp3 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _setjmp3
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
dev_langs: C++
helpviewer_keywords:
- _setjmp3 function
- setjmp3 function
ms.assetid: 6129c2f3-8bac-4fdb-a827-44e1eebba500
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ba68e059224d2d15046730a9ee0058e3114d52ed
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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