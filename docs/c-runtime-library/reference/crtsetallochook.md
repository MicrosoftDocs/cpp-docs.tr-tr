---
title: _CrtSetAllocHook | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _CrtSetAllocHook
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
- _CrtSetAllocHook
- CrtSetAllocHook
dev_langs: C++
helpviewer_keywords:
- _CrtSetAllocHook function
- CrtSetAllocHook function
ms.assetid: 405df37b-2fd1-42c8-83bc-90887f17f29d
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ac777b2e2a7ca791821be52b68f136998c33d243
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="crtsetallochook"></a>_CrtSetAllocHook
Bir istemci tarafından tanımlanan ayırma işlevi C çalışma zamanı hata ayıklama bellek ayırma işlemine (yalnızca hata ayıklama sürümü) takma tarafından yükler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
_CRT_ALLOC_HOOK _CrtSetAllocHook(  
   _CRT_ALLOC_HOOK allocHook   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `allocHook`  
 C çalışma zamanı hata ayıklama bellek ayırma işlemine kanca için yeni istemci tarafından tanımlanan ayırma işlev.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Önceden tanımlanmış ayırma kanca işlevi döndürür veya `NULL` varsa `allocHook` olan `NULL`.  
  
## <a name="remarks"></a>Açıklamalar  
 `_CrtSetAllocHook`bir uygulamanın kendi ayırma işlevini C çalışma zamanı hata ayıklama kitaplığı bellek ayırma işlemine olanak sağlar. Sonuç olarak, ayırmak için bir hata ayıklama ayırma işlevi her çağrısı yeniden ayırmak veya bir uygulamanın kanca işlevi çağrısı bir bellek bloğu Tetikleyicileri boşaltın. `_CrtSetAllocHook`bir uygulamanın uygulama yetersiz bellek gibi durumlarda nasıl işlediğini test etmek için kolay bir yöntem ayırma desenleri ve daha sonraki analizler için ayırma bilgileri günlüğe kaydetmek için Fırsat inceleyin olanağı sağlar. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar `_CrtSetAllocHook` ön işleme sırasında kaldırılır.  
  
 `_CrtSetAllocHook` İşlevi yükler belirtilen yeni istemci tarafından tanımlanan ayırma işlevi `allocHook` ve önceden tanımlanmış kanca işlevi döndürür. Aşağıdaki örnek, bir istemci tarafından tanımlanan atama kanca nasıl örneklenmiş olmalıdır gösterir:  
  
```  
int YourAllocHook( int allocType, void *userData, size_t size, int   
blockType, long requestNumber, const unsigned char *filename, int   
lineNumber);  
```  
  
 `allocType` Bağımsız değişkeni ayırma işlemi türünü belirtir `(_HOOK_ALLOC`, `_HOOK_REALLOC`, ve `_HOOK_FREE`) ayırma 's kanca işlevi çağrısında tetiklendi. Tetikleyici ayırma türü olduğunda `_HOOK_FREE`, `userData` hakkında boşaltılacak bellek bloğu kullanıcı veri bölümü bir işaretçidir. Ancak, tetikleyici ayırma türü olduğunda `_HOOK_ALLOC` veya `_HOOK_REALLOC`, `userData` olan `NULL` bellek bloğu henüz tahsis değil çünkü.  
  
 `size`blok boyutu belleğin bayt cinsinden belirtir `blockType` bellek bloğu türünü gösterir `requestNumber` bellek bloğu nesne ayırma sipariş sayısı ve kullanılabilir durumdaysa `filename` ve `lineNumber` kaynak dosya adı belirtin ve Tetikleyici ayırma işlemi başlatıldığı satır numarası.  
  
 Kanca işlevini işlemeyi bitirdikten sonra ana C çalışma zamanı ayırma işlemini nasıl devam edileceği belirten bir Boole değeri döndürmelidir. Kanca işlevi olarak kanca işlevi hiçbir zaman çağırıldıktan sonra kanca işlevini döndürmelidir devam etmek için ana ayırma işlemini istediği zaman `TRUE`. Bu, özgün tetikleme ayırma işlemi çalıştırılmasına neden olur. Bu uygulamayı kullanarak kanca işlevini toplayın ve geçerli ayırma işlemi veya hata ayıklama yığınını durumunu engellemeden daha sonraki analizler için ayırma bilgilerini kaydedin.  
  
 Kanca işlevi olarak tetikleme ayırma işlemi çağrıldı ve başarısız olduysa kanca işlevini döndürmelidir devam etmek için ana ayırma işlemini istediği zaman `FALSE`. Bu uygulamayı kullanarak kanca işlevi çok çeşitli bellek koşullarını benzetimini ve uygulama her durumda nasıl işlediğini test etmek için yığın durumları hata ayıklama.  
  
 Kanca işlevini temizlemek için geçirmek `NULL` için `_CrtSetAllocHook`.  
  
 Hakkında daha fazla bilgi için `_CrtSetAllocHook` diğer bellek yönetimi işlevleri veya kendi istemci tanımlı kanca işlevlerini yazma nasıl kullanılabilir [hata ayıklama kanca işlevi yazma](/visualstudio/debugger/debug-hook-function-writing).  
  
> [!NOTE]
>  `_CrtSetAllocHook`altında desteklenmiyor `/clr:pure`. **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_CrtSetAllocHook`|\<crtdbg.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="libraries"></a>Kitaplıklar  
 Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.  
  
## <a name="example"></a>Örnek  
 Nasıl kullanılacağına ilişkin bir örnek için `_CrtSetAllocHook`, bkz: [crt_dbg2](http://msdn.microsoft.com/en-us/21e1346a-6a17-4f57-b275-c76813089167).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)   
 [_CrtGetAllocHook](../../c-runtime-library/reference/crtgetallochook.md)