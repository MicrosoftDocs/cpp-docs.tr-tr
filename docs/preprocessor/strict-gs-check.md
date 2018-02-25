---
title: strict_gs_check | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- strict_gs_check
- strict_gs_check_CPP
dev_langs:
- C++
helpviewer_keywords:
- strict_gs_check pragma
ms.assetid: decfec81-c916-42e0-a07f-8cc26df6a7ce
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 76b06f33626dfa237c81e6a23f343bb25ffb7c78
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="strictgscheck"></a>strict_gs_check
Bu pragma artırılmış güvenlik denetimi sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#pragma strict_gs_check([push,] on )   
#pragma strict_gs_check([push,] off )   
#pragma strict_gs_check(pop)  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Yığın tabanlı arabellek taşmasının bazı kategorilerini algılamaya yardımcı olması için, derleyiciye işlev yığınına rasgele bir tanımlama bilgisi eklemesini bildirir. Varsayılan olarak, /GS (Arabellek Güvenlik Denetimi) derleyici seçeneği tüm işlevler için bir tanımlama bilgisi eklemez. Daha fazla bilgi için bkz: [/GS (arabellek güvenlik denetimi)](../build/reference/gs-buffer-security-check.md).  
  
 Strict_gs_check 'i etkinleştirmek için /GS (Arabellek Güvenlik Denetimi) ile derlemeniz gerekir.  
  
 Bu pragmayı, zarar verme olasılığı bulunan verilerin gördüğü kod modüllerinde kullanın. Bu pragma çok agresiftir ve bu savunmayı gerektirmeyen işlevlere uygulanır. Ancak sonuç uygulamasının performansı üzerindeki etkisini en aza indirmek için optimize edilmiştir.  
  
 Bu pragmayı kullansanız bile, güvenli kod yazmak için çaba göstermelisiniz. Diğer bir deyişle, kodunuzu hiçbir arabellek taşmaları sahip olduğundan emin olun. strict_gs_check, uygulama kodunuzda kalır arabellek taşmaları korunmasına.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kodda, bir diziyi yerel bir diziye kopyaladığımızda arabellek taşması oluşur. Bu kodu /GS ile derlerseniz, dizi veri türü bir işaretçi olduğu için yığına hiçbir tanımlama bilgisi eklenmez. Strict_gs_check pragmasını eklemek, yığın tanımlama bilgisini işlev yığınına zorlar.  
  
```cpp  
// pragma_strict_gs_check.cpp  
// compile with: /c  
  
#pragma strict_gs_check(on)  
  
void ** ReverseArray(void **pData,  
                     size_t cData)  
{  
    // *** This buffer is subject to being overrun!! ***  
    void *pReversed[20];  
  
    // Reverse the array into a temporary buffer  
    for (size_t j = 0, i = cData; i ; --i, ++j)  
        // *** Possible buffer overrun!! ***  
            pReversed[j] = pData[i];   
  
    // Copy temporary buffer back into input/output buffer  
    for (size_t i = 0; i < cData ; ++i)   
        pData[i] = pReversed[i];  
  
    return pData;  
}  
  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pragma yönergeleri ve __Pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [/GS (Arabellek Güvenlik Denetimi)](../build/reference/gs-buffer-security-check.md)