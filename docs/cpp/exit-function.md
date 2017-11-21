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
ms.openlocfilehash: e4a1ee1a533309dfedce139efc7c6db1f41653a6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="exit-function"></a>exit İşlevi
**Çıkmak** standart içerme dosyası STDLIB bildirilen işlevi. H, C++ programı sonlandırır.  
  
 Bağımsız değişken olarak sağlanan değer **çıkmak** işletim sistemi programın dönüş kodu veya çıkış kodu olarak döndürülür. Kural olarak, sıfır olan dönüş kodu programın başarıyla tamamlandığı anlamına gelir.  
  
> [!NOTE]
>  Programınızın başarılı veya başarısız olduğunu göstermek için STDLIB.H'de tanımlanan `EXIT_FAILURE` ve `EXIT_SUCCESS` sabitlerini kullanabilirsiniz.  
  
 Sertifika veren bir `return` from deyimi **ana** işlevi çağırmak için eşdeğerdir **çıkmak** işlevi bağımsız değişken olarak dönüş değerine sahip.  
  
 Daha fazla bilgi için bkz: [çıkmak](../c-runtime-library/reference/exit-exit-exit.md) içinde *çalışma zamanı kitaplığı başvurusu*.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Program sonlandırma](../cpp/program-termination.md)