---
title: _purecall | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _purecall
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
- ntoskrnl.exe
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- purecall
- _purecall
dev_langs: C++
helpviewer_keywords:
- _purecall function
- purecall function
ms.assetid: 56135d9b-3403-4e22-822d-e714523801cc
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8ef2670188374dc7af5fa34c76df73c3d261efc4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="purecall"></a>_purecall
Varsayılan saf sanal işlev çağrısı hata işleyicisi. Derleyici saf sanal üye işlevi çağrıldığında, bu işlev çağrısı için kod oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
extern "C" int __cdecl _purecall();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `_purecall` Microsoft Visual C++ Derleyici Microsoft'a özgü uygulama ayrıntılarını işlevdir. Bu işlev kodunuz tarafından doğrudan çağrılması amaçlanmamıştır ve ortak üstbilgi bildirim vardır. C çalışma zamanı kitaplığı ortak verilmesini olduğundan burada belgelenmiştir.  
  
 Hiçbir uygulama içerdiğinden saf sanal işlevi çağrısı bir hatadır. Derleyici çağırmak için kod oluşturur `_purecall` saf sanal işlevi çağrıldığında hata işleyici işlevi. Varsayılan olarak, `_purecall` program sonlandırır. Sonlandırma önce `_purecall` işlevi çağıran bir `_purecall_handler` bir işlem için ayarlanmışsa işlev. Saf sanal işlev çağrısı, bunları hata ayıklama veya Raporlama amaçları için yakalamak için kendi hata işleyici işlevi yükleyebilirsiniz. Kendi hata işleyicisini kullanmak için olan bir işlev oluşturun `_purecall_handler` imza, ardından [_set_purecall_handler](../../c-runtime-library/reference/get-purecall-handler-set-purecall-handler.md) geçerli işleyici yapma.  
  
## <a name="requirements"></a>Gereksinimler  
 `_purecall` İşlevi bir üstbilgi bildirimi sahip değil. `_purecall_handler` Typedef tanımlanmış \<stdlib.h >.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Alfabetik işlev başvurusu](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [_get_purecall_handler, _set_purecall_handler](../../c-runtime-library/reference/get-purecall-handler-set-purecall-handler.md)