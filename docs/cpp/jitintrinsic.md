---
title: jitintrinsic | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- jitintrinsic
- jitintrinsic_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], jitintrinsic
- jitintrinsic __declspec modifier
ms.assetid: 23dbe416-7ef6-442b-b16d-9a81aab04fa6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f0b114089567de06a71f15b69c556e08d1e4e9c6
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404086"
---
# <a name="jitintrinsic"></a>jitintrinsic
İşlevi 64 bit ortak dil çalışma zamanı için önemli olarak işaretler. Bu, Microsoft tarafından sağlanan kitaplıklardaki belirli işlevlerde kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
__declspec(jitintrinsic)  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **jitintrinsic** bir MODOPT ekler (<xref:System.Runtime.CompilerServices.IsJitIntrinsic>) bir işlev imzası.  
  
 Kullanıcılar bu kullanarak önerilmez **__declspec** değiştiricisi, beklenmedik sonuçlar oluşabilir.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [__declspec](../cpp/declspec.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)