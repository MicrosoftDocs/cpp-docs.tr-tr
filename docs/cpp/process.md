---
title: "işlem | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- process_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], process
- process __declspec keyword
ms.assetid: 60eecc2f-4eef-4567-b9db-aaed34733023
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2c50948d613a40a03d0249e1930943ef61c855b9
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="process"></a>process
Yönetilen uygulama işleminizde, belirli genel değişkenin, statik üye değişkeninin veya işlemde tüm uygulama etki alanlarında paylaşılan statik yerel değişkenin tek bir kopyasının olması gerektiğini belirtir. Bu öncelikle ile derleme yapılırken kullanılmak üzere tasarlanmıştır **/CLR: pure**, artık kullanım dışıdır ve derleyici gelecek bir sürümünde kaldırılacak. İle derleme yapılırken **/CLR**, genel ve statik değişkenlerdir varsayılan işlem başına (kullanmasına gerek kalmamasını `__declspec(process)`.  
  
 Yalnızca bir genel değişken, bir statik üye değişkeni veya özgün türün statik bir yerel değişkeni `__declspec(process)` ile işaretlenebilir.  
  
  
 `process` ile derleme yapılırken yalnızca geçerlidir [/CLR](../build/reference/clr-common-language-runtime-compilation.md).  
  
 Her uygulama etki genel değişkeni kendi kopyasına sahip olmasını istiyorsanız, kullanmak [appdomain](../cpp/appdomain.md).  
  
 Bkz: [uygulama etki alanları ve Visual C++](../dotnet/application-domains-and-visual-cpp.md) daha fazla bilgi için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__declspec](../cpp/declspec.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)