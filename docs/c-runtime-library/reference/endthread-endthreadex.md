---
title: _endthread, _endthreadex | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _endthread
- _endthreadex
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
- _endthread
- endthreadex
- _endthreadex
- endthread
dev_langs:
- C++
helpviewer_keywords:
- _endthread function
- endthread function
- terminating threads
- endthreadex function
- _endthreadex function
- threading [C++], terminating threads
ms.assetid: 18a91f2f-659e-40b4-b266-ec12dcf2abf5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 794dc5c4bbaf9653c5b6bbb08ea3e0a60ca438c4
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="endthread-endthreadex"></a>_endthread, _endthreadex
Bir iş parçacığını sonlandırır; `_endthread` tarafından oluşturulan bir iş parçacığını sonlandırır `_beginthread` ve `_endthreadex` tarafından oluşturulan bir iş parçacığını sonlandırır `_beginthreadex`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void _endthread( void );  
void _endthreadex(   
   unsigned retval   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `retval`  
 İş parçacığı çıkış kodu.  
  
## <a name="remarks"></a>Açıklamalar  
 Çağırabilirsiniz `_endthread` veya `_endthreadex` açıkça bir iş parçacığı; sonlandırmak için ancak `_endthread` veya `_endthreadex` iş parçacığı bir parametre olarak geçirilen yordamı döndüğünde otomatik olarak çağrılır `_beginthread` veya `_beginthreadex`. Bir iş parçacığı çağrısıyla sonlandırma `endthread` veya `_endthreadex` iş parçacığı için ayrılan kaynakların doğru kurtarma sağlamaya yardımcı olur.  
  
> [!NOTE]
>  Libcmt.lib ile bağlantılı bir yürütülebilir dosya için Win32 çağırmayın [ExitThread](http://msdn.microsoft.com/library/windows/desktop/ms682659.aspx) API; Bu, ayrılan kaynakları geri kazanma çalışma zamanı sistem engeller. `_endthread` ve `_endthreadex` ayrılmış iş parçacığı kaynaklarını geri kazanmak ve ardından arama `ExitThread`.  
  
 `_endthread` iş parçacığı tutamacı otomatik olarak kapatılır. (Bu davranış Win32 farklıdır `ExitThread` API.) Bu nedenle, kullandığınızda `_beginthread` ve `_endthread`, açıkça iş parçacığı tutamacı Win32 çağırarak kapatmayın [CloseHandle](http://msdn.microsoft.com/library/windows/desktop/ms724211.aspx) API.  
  
 Win32 gibi `ExitThread` API, `_endthreadex` iş parçacığı tutamacı kapatmaz. Bu nedenle, kullandığınızda `_beginthreadex` ve `_endthreadex`, Win32 çağırarak iş parçacığı tutamacı kapatmalısınız `CloseHandle` API.  
  
> [!NOTE]
>  `_endthread` ve `_endthreadex` C++ Yıkıcılar bekleyen değil çağrılacak parçacığında neden.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|Gerekli başlık|  
|--------------|---------------------|  
|`_endthread`|\<Process.h >|  
|`_endthreadex`|\<Process.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Kitaplıklar  
 Birden çok iş parçacıklı sürümlerini [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [_beginthread](../../c-runtime-library/reference/beginthread-beginthreadex.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Süreç ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)   
 [_beginthread, _beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md)