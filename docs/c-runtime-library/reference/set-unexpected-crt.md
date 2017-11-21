---
title: set_unexpected (CRT) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: set_unexpected
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
f1_keywords: set_unexpected
dev_langs: C++
helpviewer_keywords:
- set_unexpected function
- unexpected function
- exception handling, termination
ms.assetid: ebcef032-4771-48e5-88aa-2a1ab8750aa6
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 82ef2df148abba6f482f9674a73d92e30d22ecdb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="setunexpected-crt"></a>set_unexpected (CRT)
Çağrılacak kendi sonlandırma işlev yükler `unexpected`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
unexpected_function set_unexpected(  
   unexpected_function unexpFunction   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `unexpFunction`  
 Değiştirmek için yazma bir işlev işaretçisi `unexpected` işlevi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Önceki sonlandırma işlevi için bir işaretçi kayıtlı tarafından döndürür `_set_unexpected` böylece önceki işlevi daha sonra geri yüklenebilir. Önceki bir işlev ayarlarsanız varsayılan davranışı geri dönüş değeri kullanılabilir; Bu değer NULL olabilir.  
  
## <a name="remarks"></a>Açıklamalar  
 `set_unexpected` İşlev yükler `unexpFunction` çağrılan işlev olarak `unexpected`. `unexpected`Geçerli C++ özel durum işleme uygulamasında kullanılmaz. `unexpected_function` Türü EH içinde tanımlanmıştır. Bir kullanıcı tanımlı beklenmeyen işlev işaretçisi olarak H `unexpFunction` döndüren `void`. Özel `unexpFunction` işlevi çağırıcısına döndürmemelidir.  
  
```  
typedef void ( *unexpected_function )( );  
```  
  
 Varsayılan olarak, `unexpected` çağrıları `terminate`. Kendi sonlandırma işlevi yazma ve arama bu varsayılan davranışı değiştirebilirsiniz `set_unexpected` işlevinizi bağımsız değişkeni olarak adı. `unexpected`bağımsız değişken olarak verilen son işlevi çağırır `set_unexpected`.  
  
 Bir çağrı tarafından yüklenen özel sonlandırma işlevi aksine `set_terminate`, bir özel durum içinden atılabilen `unexpFunction`.  
  
 Birden çok iş parçacıklı bir ortamda, beklenmeyen işlevleri her iş parçacığı için ayrı ayrı tutulur. Her yeni bir iş parçacığı beklenmeyen işlevini yüklemesi gerekir. Bu nedenle, her iş parçacığı beklenmeyen kendi işleme sorumlu olur.  
  
 C++ özel durum işleme, geçerli Microsoft uygulamasındaki `unexpected` çağrıları `terminate` varsayılan ve özel durum işleme çalışma zamanı kitaplığı tarafından hiçbir zaman çağrılır. Arama için belirli bir avantajı vardır `unexpected` yerine `terminate`.  
  
 Tek bir yoktur `set_unexpected` işleyicisi tüm dinamik olarak bağlı dll veya exe; bile çağırırsanız `set_unexpected` işleyiciniz başka tarafından değiştirilebilir veya bir işleyici değiştirerek bir başkası tarafından DLL veya EXE ayarlayın.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`set_unexpected`|\<EH.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel durum işleme rutinleri](../../c-runtime-library/exception-handling-routines.md)   
 [durdurma](../../c-runtime-library/reference/abort.md)   
 [_get_unexpected](../../c-runtime-library/reference/get-unexpected.md)   
 [set_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [sonlandırma](../../c-runtime-library/reference/terminate-crt.md)   
 [beklenmeyen](../../c-runtime-library/reference/unexpected-crt.md)