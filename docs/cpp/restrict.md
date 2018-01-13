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
ms.workload: cplusplus
ms.openlocfilehash: 24fa0dae15fb0d4dfab8d481c6626c7611295572
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)