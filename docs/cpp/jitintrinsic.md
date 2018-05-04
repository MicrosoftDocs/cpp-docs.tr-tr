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
ms.openlocfilehash: 71cd88882ea104275e4c1a43ccf05494a859d303
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="jitintrinsic"></a>jitintrinsic
İşlevi 64 bit ortak dil çalışma zamanı için önemli olarak işaretler. Bu, Microsoft tarafından sağlanan kitaplıklardaki belirli işlevlerde kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
__declspec(jitintrinsic)  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `jitintrinsic`, işlev imzasına bir MODOPT (<xref:System.Runtime.CompilerServices.IsJitIntrinsic>) ekler.  
  
 Beklenmedik sonuçlar ortaya çıkabileceği için kullanıcıların bu `__declspec` değiştiricisini kullanması önerilmez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__declspec](../cpp/declspec.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)