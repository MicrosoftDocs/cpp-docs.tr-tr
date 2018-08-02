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
ms.openlocfilehash: b41646dbde21f68c2cc23dfbcf977d9f5ad06c1e
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39467499"
---
# <a name="safebuffers"></a>safebuffers
**Microsoft'a özgü**  
  
 Derleyiciye bir işlev için arabellek taşması güvenlik denetimlerini eklememesini bildirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
__declspec( safebuffers )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **/GS** derleyici seçeneği, derleyicinin yığın üzerinde güvenlik denetimleri ekleyerek arabellek taşmaları için test etmek neden olur. Güvenlik denetimleri için uygun olan veri yapılarının türleri açıklanan [/GS (arabellek güvenlik denetimi)](../build/reference/gs-buffer-security-check.md). Arabellek Taşması algılama hakkında daha fazla bilgi için bkz: [derleyici güvenlik denetimleri ayrıntılı olarak](http://go.microsoft.com/fwlink/p/?linkid=7260) MSDN Web sitesinde.  
  
 Uzman düzeyde el ile kod incelemesi veya harici analiz, işlevde arabellek taşması görülmediğini belirleyebilir. Bu durumda, uygulayarak bir işlev için güvenlik denetimlerini gözardı edebileceğini **__declspec(safebuffers)** işlev bildirimine anahtar sözcüğü.  
  
> [!CAUTION]
>  Arabellek güvenlik denetimleri, önemli bir güvenlik koruması sağlar ve performans üzerinde göz ardı edilebilir bir etki oluşturur. Bu nedenle, işlev performansının kritik bir önem arz ettiği ve işlevin güvenli olduğunun bilindiği nadir durumlar haricinde bunları engellememenizi öneririz.  
  
## <a name="inline-functions"></a>Satır İçi İşlevler  
 A *birincil işlevi* kullanabileceğiniz bir [inlining'i](inline-functions-cpp.md) bir kopyasını eklemek için anahtar sözcüğü bir *ikincil işlevi*. Varsa **__declspec(safebuffers)** anahtar sözcüğü, bir işleve uygulanırsa, arabellek taşması algılama bu işlev için engellenir. Ancak, satır içi kullanım etkiler **__declspec(safebuffers)** aşağıdaki yollarla anahtar sözcüğü.  
  
 Varsayalım **/GS** her iki işlev için derleyici seçeneği belirtildi, ancak birincil işlevi belirtir **__declspec(safebuffers)** anahtar sözcüğü. İkincil işlevdeki veri yapıları, bunu güvenlik denetimleri için uygun hale getirir ve işlev bu denetimleri engellemez. Bu durumda:  
  
-   Belirtin [__forceinline](inline-functions-cpp.md) işlevi derleyici iyileştirmelerine bakılmaksızın satır içi derleyiciye zorlamak için ikincil işlevde anahtar sözcüğü.  
  
-   İkincil işlev güvenlik denetimleri için uygun olduğundan, belirtmesine rağmen güvenlik denetimleri de birincil işleve uygulanan **__declspec(safebuffers)** anahtar sözcüğü.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod nasıl kullanılacağını gösterir **__declspec(safebuffers)** anahtar sözcüğü.  
  
```cpp 
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
  
 **END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [__declspec](../cpp/declspec.md)   
 [anahtar sözcükler](../cpp/keywords-cpp.md)   
 [Satır içi, __inline, \__forceinline](inline-functions-cpp.md)   
 [strict_gs_check](../preprocessor/strict-gs-check.md)