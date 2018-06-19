---
title: exit işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- Exit
dev_langs:
- C++
helpviewer_keywords:
- exit function
ms.assetid: 26ce439f-81e2-431c-9ff8-a09a96f32127
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5767f6b08b4adcd3d1a8d367c6286a746eeecec3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32412536"
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