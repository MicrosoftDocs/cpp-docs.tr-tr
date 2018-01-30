---
title: _set_SSE2_enable | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _set_SSE2_enable
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _set_SSE2_enable
- set_SSE2_enable
dev_langs:
- C++
helpviewer_keywords:
- _set_SSE2_enable function
- Streaming SIMD Extensions 2 instructions
- set_SSE2_enable function
ms.assetid: 55db895d-fc1e-475a-9110-b781a9bb51c5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 424bdd9eed44f35b21a78b97b8e418f6c8a3c985
ms.sourcegitcommit: 185e11ab93af56ffc650fe42fb5ccdf1683e3847
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2018
---
# <a name="setsse2enable"></a>_set_SSE2_enable
Etkinleştirir veya CRT matematik yordamları Streaming SIMD Extensions 2 (SSE2) yönergeleri kullanımını devre dışı bırakır. (Bu işlev x64 üzerinde kullanılabilir değil mimarileri SSE2 varsayılan olarak etkin olduğundan.)  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _set_SSE2_enable(  
   int flag  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `flag`  
 SSE2 uygulama etkinleştirmek için 1; SSE2 uygulama devre dışı bırakmak için 0'ı tıklatın. Varsayılan olarak, SSE2 uygulama destekleyen işlemcileri üzerinde etkin.  
  
## <a name="return-value"></a>Dönüş Değeri  
 SSE2 uygulama etkinse, sıfır olmayan; sıfır SSE2 uygulama devre dışı bırakılır.  
  
## <a name="remarks"></a>Açıklamalar  
 Aşağıdaki işlevleri kullanarak etkinleştirilebilir SSE2 uygulamaları olan `_set_SSE2_enable`:  
  
-   [atan](../../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)  
  
-   [ceil](../../c-runtime-library/reference/ceil-ceilf-ceill.md)  
  
-   [exp](../../c-runtime-library/reference/exp-expf.md)  
  
-   [Kat](../../c-runtime-library/reference/floor-floorf-floorl.md)  
  
-   [Günlük](../../c-runtime-library/reference/log-logf-log10-log10f.md)  
  
-   [log10](../../c-runtime-library/reference/log-logf-log10-log10f.md)  
  
-   [modf](../../c-runtime-library/reference/modf-modff-modfl.md)  
  
-   [POW](../../c-runtime-library/reference/pow-powf-powl.md)  
  
 Bu işlevlerin SSE2 uygulamaları biraz farklı varsayılan uygulamaları daha SSE2 Ara değerleri 64-bit kayan nokta sayıları ancak varsayılan uygulama ara değerleri 80 bit çünkü cevaplamak kayan nokta sayıları.  
  
> [!NOTE]
>  Kullanırsanız [/Oi (iç işlevler Oluştur)](../../build/reference/oi-generate-intrinsic-functions.md) Projeyi derlemek için derleyici seçeneği, görünebilir `_set_SSE2_enable` hiçbir etkisi olmaz. `/Oi` Derleyici seçeneği derleyici iç bilgileri CRT çağrılarını değiştirmek için kullanma yetkisi verir; Bu davranış etkisini geçersiz kılar `_set_SSE2_enable`. Garanti istiyorsanız `/Oi` geçersiz `_set_SSE2_enable`, kullanın `/Oi-` projenizi derleme için. Kapsıyor diğer derleyici anahtarları kullandığınızda bu iyi bir uygulama da olabilir `/Oi`.  
  
 SSE2 uygulama yalnızca tüm özel durumları maskelenmiş kullanılır. Kullanım [_control87, _controlfp](../../c-runtime-library/reference/control87-controlfp-control87-2.md) maskesi özel durumlar.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_set_SSE2_enable`|\<Math.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_set_SSE2_enable.c  
// processor: x86  
#include <math.h>  
#include <stdio.h>  
  
int main()  
{  
   int i = _set_SSE2_enable(1);  
  
   if (i)  
      printf("SSE2 enabled.\n");  
   else  
      printf("SSE2 not enabled; processor does not support SSE2.\n");  
}  
```  
  
 **Output**  
  
 `SSE2 enabled.`  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRT Kitaplık Özellikleri](../../c-runtime-library/crt-library-features.md)