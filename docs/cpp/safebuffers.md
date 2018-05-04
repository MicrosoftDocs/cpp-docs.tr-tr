---
title: safebuffers | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- safebuffers_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword (C++), safebuffers
- safebuffers __declspec keyword
ms.assetid: 0b0dce14-4523-44d2-8070-5dd0fdabc618
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fbfc9317b5ed7c63e9c70b081c3f241b86a65e5f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="safebuffers"></a>safebuffers
**Microsoft özel**  
  
 Derleyiciye bir işlev için arabellek taşması güvenlik denetimlerini eklememesini bildirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
__declspec( safebuffers )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **/GS** derleyici seçeneği yığında güvenlik denetimleri ekleyerek arabellek aşırı çalıştırmaları için test etmek derleyicinin neden olur. Güvenlik denetimleri için uygun veri yapılarını türlerini açıklanan [/GS (arabellek güvenlik denetimi)](../build/reference/gs-buffer-security-check.md). Arabellek Taşması algılama hakkında daha fazla bilgi için bkz: [içinde derleyici güvenlik derinliği denetler](http://go.microsoft.com/fwlink/p/?linkid=7260) MSDN Web sitesinde.  
  
 Uzman düzeyde el ile kod incelemesi veya harici analiz, işlevde arabellek taşması görülmediğini belirleyebilir. Uygulayarak bir işlev için güvenlik denetimleri bu durumda, gizleyebilirsiniz `__declspec(safebuffers)` işlev bildirimi anahtar sözcük.  
  
> [!CAUTION]
>  Arabellek güvenlik denetimleri, önemli bir güvenlik koruması sağlar ve performans üzerinde göz ardı edilebilir bir etki oluşturur. Bu nedenle, işlev performansının kritik bir önem arz ettiği ve işlevin güvenli olduğunun bilindiği nadir durumlar haricinde bunları engellememenizi öneririz.  
  
## <a name="inline-functions"></a>Satır İçi İşlevler  
 A *birincil işlev* kullanabileceğiniz bir [satır içi kullanım](inline-functions-cpp.md) bir kopyasını eklemek için anahtar sözcüğü bir *ikincil işlevi*. Varsa `__declspec(safebuffers)` anahtar sözcüğü bir işleve uygulandığında, arabellek taşması algılama o işlev için gizlenen. Ancak, satır içi kullanım etkiler `__declspec(safebuffers)` aşağıdaki yollarla anahtar sözcüğü.  
  
 Varsayalım **/GS** derleyici seçeneği hem işlevleri için belirtilen, ancak birincil işlevini belirten `__declspec(safebuffers)` anahtar sözcüğü. İkincil işlevdeki veri yapıları, bunu güvenlik denetimleri için uygun hale getirir ve işlev bu denetimleri engellemez. Bu durumda:  
  
-   Belirtin [__forceinline](inline-functions-cpp.md) derleyici iyileştirmelerini bağımsız olarak işlev satır içi derleyiciye zorlamak için ikincil işlevi on anahtar sözcüğü.  
  
-   İkincil işlevi güvenlik denetimleri için uygun olduğundan, belirtir olsa bile güvenlik denetimleri de birincil işlevi uygulanır `__declspec(safebuffers)` anahtar sözcüğü.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kodu nasıl kullanılacağını gösterir `__declspec(safebuffers)` anahtar sözcüğü.  
  
```  
// compile with: /c /GS  
typedef struct {  
    int x[20];  
} BUFFER;  
static int checkBuffers() {  
    BUFFER cb;  
    // Use the buffer...  
    return 0;  
};  
static __declspec(safebuffers)   
    int noCheckBuffers() {  
    BUFFER ncb;  
    // Use the buffer...  
    return 0;  
}  
int wmain() {  
    checkBuffers();  
    noCheckBuffers();  
    return 0;  
}  
```  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__declspec](../cpp/declspec.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)   
 [Satır içi, __inline, \__forceinline](inline-functions-cpp.md)   
 [strict_gs_check](../preprocessor/strict-gs-check.md)