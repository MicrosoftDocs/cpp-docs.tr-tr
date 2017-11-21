---
title: "kısıtlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: restrict_cpp
dev_langs: C++
helpviewer_keywords:
- __declspec keyword [C++], restrict
- restrict __declspec keyword
ms.assetid: f39cf632-68d8-4362-a497-2d4c15693689
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9176336ac96d88a34d758fd55c09a3a938f371fb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="restrict"></a>restrict
**Microsoft özel**  
  
 İşlevi bildiriminde ya da işlevi diğer herhangi diğer işaretçilerle olmayacak bir nesne döndürür derleyici bildirir ve bir işaretçi türü döndüren tanımı uygulanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
__declspec(restrict) return_type f();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Derleyici yayılır `__declspec(restrict)`. Örneğin, CRT `malloc` ile işlevi donatılmış `__declspec(restrict)` ve bu nedenle, işaretçileri başlatıldı ile bellek konumlara `malloc` diğer olmaması için de kapsanan.  
  
 Derleyici işaretçinin aslında diğer olmadığını denetlemez. Bu program yapar olmayan diğer ad ile işaretli bir işaretçi emin olmak için geliştiricinin sorumluluğundadır `restrict __declspec` değiştiricisi.  
  
 Değişkenleri için benzer semantiği almak için bkz: [__restrict](../cpp/extension-restrict.md).  
  
## <a name="example"></a>Örnek  
 Bkz: [noalias](../cpp/noalias.md) kullanarak bir örnek için `restrict`.  
  
 C++ AMP parçası olan sınırla anahtar sözcük hakkında daha fazla bilgi için bkz: [sınırla (C++ AMP)](../cpp/restrict-cpp-amp.md).  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__declspec](../cpp/declspec.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)