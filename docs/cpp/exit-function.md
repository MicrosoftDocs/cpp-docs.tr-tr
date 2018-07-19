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
ms.openlocfilehash: d08ac1375fa383543eaafb5b3ce49cd2bbfbc4da
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37941086"
---
# <a name="exit-function"></a>exit İşlevi
`exit` Standart içerme dosyasında bildirilen işlevde, \<stdlib.h >, bir C++ programını sonlandırır.  
  
 Bağımsız değişken olarak sağlanan değer `exit` programın dönüş kodu veya çıkış kodu olarak işletim sistemine döndürülür. Kural olarak, sıfır olan dönüş kodu programın başarıyla tamamlandığı anlamına gelir.  
  
> [!NOTE]
>  Exıt_faılure ve exıt_success, tanımlı sabitler kullanabileceğiniz \<stdlib.h >, başarı veya başarısızlık programınızın belirtmek için.  
  
 Veren bir **dönüş** deyimden `main` işlevini çağırmakla eşdeğerdir `exit` işlevi, bağımsız değişkeni dönüş değerine sahip.  
  
 Daha fazla bilgi için [çıkmak](../c-runtime-library/reference/exit-exit-exit.md) içinde *çalışma zamanı kitaplığı başvurusu*.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Program Sonlandırma](../cpp/program-termination.md)