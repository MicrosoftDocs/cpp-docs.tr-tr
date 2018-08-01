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
ms.openlocfilehash: ce4272ecfee4b3d02d8bf79f7816200a392c9735
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404834"
---
# <a name="exit-function"></a>exit İşlevi
**Çıkmak** standart içerme dosyasında bildirilen işlevde, \<stdlib.h >, bir C++ programını sonlandırır.  
  
 Bağımsız değişken olarak sağlanan değer **çıkmak** programın dönüş kodu veya çıkış kodu olarak işletim sistemine döndürülür. Kural olarak, sıfır olan dönüş kodu programın başarıyla tamamlandığı anlamına gelir.  
  
> [!NOTE]
>  Exıt_faılure ve exıt_success, tanımlı sabitler kullanabileceğiniz \<stdlib.h >, başarı veya başarısızlık programınızın belirtmek için.  
  
 Veren bir **dönüş** deyimden `main` işlevini çağırmakla eşdeğerdir **çıkmak** işlevi, bağımsız değişkeni dönüş değerine sahip.  
  
 Daha fazla bilgi için [çıkmak](../c-runtime-library/reference/exit-exit-exit.md) içinde *çalışma zamanı kitaplığı başvurusu*.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Program Sonlandırma](../cpp/program-termination.md)