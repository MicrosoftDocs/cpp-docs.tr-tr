---
title: "exit işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: Exit
dev_langs: C++
helpviewer_keywords: exit function
ms.assetid: 26ce439f-81e2-431c-9ff8-a09a96f32127
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b9e0d6a7f903d4af39698b2d98c005cbf64515eb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="exit-function"></a>exit İşlevi
**Çıkmak** standart içerme dosyası STDLIB bildirilen işlevi. H, C++ programı sonlandırır.  
  
 Bağımsız değişken olarak sağlanan değer **çıkmak** işletim sistemi programın dönüş kodu veya çıkış kodu olarak döndürülür. Kural olarak, sıfır olan dönüş kodu programın başarıyla tamamlandığı anlamına gelir.  
  
> [!NOTE]
>  Programınızın başarılı veya başarısız olduğunu göstermek için STDLIB.H'de tanımlanan `EXIT_FAILURE` ve `EXIT_SUCCESS` sabitlerini kullanabilirsiniz.  
  
 Sertifika veren bir `return` from deyimi **ana** işlevi çağırmak için eşdeğerdir **çıkmak** işlevi bağımsız değişken olarak dönüş değerine sahip.  
  
 Daha fazla bilgi için bkz: [çıkmak](../c-runtime-library/reference/exit-exit-exit.md) içinde *çalışma zamanı kitaplığı başvurusu*.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Program Sonlandırma](../cpp/program-termination.md)