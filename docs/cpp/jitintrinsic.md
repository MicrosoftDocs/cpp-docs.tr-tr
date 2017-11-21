---
title: jitintrinsic | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- jitintrinsic
- jitintrinsic_cpp
dev_langs: C++
helpviewer_keywords:
- __declspec keyword [C++], jitintrinsic
- jitintrinsic __declspec modifier
ms.assetid: 23dbe416-7ef6-442b-b16d-9a81aab04fa6
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 69e0350df240d4748a91b1400c1811209b9dfdd1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Anahtar sözcükler](../cpp/keywords-cpp.md)