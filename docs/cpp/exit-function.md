---
title: "exit işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- Exit
dev_langs:
- C++
helpviewer_keywords:
- exit function
ms.assetid: 26ce439f-81e2-431c-9ff8-a09a96f32127
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ee6a34a70465904e6725f42e68eb4a00c03a1661
ms.sourcegitcommit: 9a0a287d6940591523af959ebdac5affa36220da
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="exit-function"></a>exit İşlevi
**Çıkmak** işlevi, standart INCLUDE dosyasında bildirilen \<stdlib.h >, C++ programı sonlandırır.  
  
 Bağımsız değişken olarak sağlanan değer **çıkmak** işletim sistemi programın dönüş kodu veya çıkış kodu olarak döndürülür. Kural olarak, sıfır olan dönüş kodu programın başarıyla tamamlandığı anlamına gelir.  
  
> [!NOTE]
>  Sabitler kullanabilirsiniz `EXIT_FAILURE` ve `EXIT_SUCCESS`, içinde tanımlı \<stdlib.h >, başarı veya başarısızlık programınızın belirtmek için.  
  
 Sertifika veren bir `return` from deyimi **ana** işlevi çağırmak için eşdeğerdir **çıkmak** işlevi bağımsız değişken olarak dönüş değerine sahip.  
  
 Daha fazla bilgi için bkz: [çıkmak](../c-runtime-library/reference/exit-exit-exit.md) içinde *çalışma zamanı kitaplığı başvurusu*.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Program Sonlandırma](../cpp/program-termination.md)