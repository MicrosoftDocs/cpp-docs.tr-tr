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
ms.openlocfilehash: 71bff42495c4b6b7bf4016f0f08e7127c2b278ac
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46075182"
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