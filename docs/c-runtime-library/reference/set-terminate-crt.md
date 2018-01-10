---
title: set_terminate (CRT) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: set_terminate
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
f1_keywords: set_terminate
dev_langs: C++
helpviewer_keywords:
- set_terminate function
- terminate function
- exception handling, termination
ms.assetid: 3ff1456a-7898-44bc-9266-a328a80b6006
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 099cb340f821f04c3a5f84ccef7e3e9649482cd6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="setterminate-crt"></a>set_terminate (CRT)
Kendi sonlandırma yordamı çağrılacak yükler `terminate`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
terminate_function set_terminate(  
   terminate_function termFunction  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `termFunction`  
 Yazdığınız Sonlandır işlev işaretçisi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Tarafından kaydedilen önceki işlevi için bir işaretçi döndüren `set_terminate` böylece önceki işlevi daha sonra geri yüklenebilir. Önceki bir işlev ayarlarsanız varsayılan davranışı geri dönüş değeri kullanılabilir; Bu değer NULL olabilir.  
  
## <a name="remarks"></a>Açıklamalar  
 `set_terminate` İşlev yükler `termFunction` çağrılan işlev olarak `terminate`. `set_terminate`C++ özel durum işleme ile kullanılır ve özel durum önce programınızdaki herhangi bir noktada çağrılabilir. `terminate`çağrıları `abort` varsayılan olarak. Kendi sonlandırma işlevi yazma ve arama bu varsayılan ayarı değiştirebilirsiniz `set_terminate` işlevinizi bağımsız değişkeni olarak adı. `terminate`bağımsız değişken olarak verilen son işlevi çağırır `set_terminate`. Temizleme görevleri herhangi gerçekleştirme istenen sonra `termFunction` program çıkmalıdır. (Çağırıcısına döndürürse), mevcut değilse, `abort` olarak adlandırılır.  
  
 Birden çok iş parçacıklı bir ortamda, sonlandırma işlevleri her iş parçacığı için ayrı olarak korunur. Her yeni bir iş parçacığı kendi Sonlandır işlevi yüklemeniz gerekir. Bu nedenle, her iş parçacığının kendi sonlandırma işleme sorumlu olduğu.  
  
 `terminate_function` Türü EH içinde tanımlanmıştır. Bir sonlandırma kullanıcı tanımlı işlev işaretçisi olarak H `termFunction` döndüren `void`. Özel işlevinizi `termFunction` bağımsız değişkenler almayan ve çağırıcısına vermemelidir. Aşması durumunda `abort` olarak adlandırılır. Bir özel durum içinden durum oluşturulabilir değil `termFunction`.  
  
```  
typedef void ( *terminate_function )( );  
```  
  
> [!NOTE]
>  `set_terminate` İşlevi yalnızca hata ayıklayıcı dışında çalışır.  
  
 Tek bir yoktur `set_terminate` işleyicisi tüm dinamik olarak bağlı dll veya exe; bile çağırırsanız `set_terminate` işleyiciniz başka tarafından değiştirilebilir veya başka bir DLL veya EXE tarafından ayarlanan bir işleyici değiştirme.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`set_terminate`|\<EH.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [sonlandırmak](../../c-runtime-library/reference/terminate-crt.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel durum işleme rutinleri](../../c-runtime-library/exception-handling-routines.md)   
 [durdurma](../../c-runtime-library/reference/abort.md)   
 [_get_terminate](../../c-runtime-library/reference/get-terminate.md)   
 [set_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [sonlandırma](../../c-runtime-library/reference/terminate-crt.md)   
 [beklenmeyen](../../c-runtime-library/reference/unexpected-crt.md)