---
title: Yapılandırılmış özel durum işlemeyi C++ ile kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- C++ exception handling, mixed with SEH
- structured exception handling [C++], with C++ exception handling
ms.assetid: ec34b528-8c26-4429-b24a-6a68553aaa91
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 71ce64a067ed75c29d83913adababe2d97dba6f0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="using-structured-exception-handling-with-c"></a>Yapılandırılmış Özel Durum İşlemeyi C++ ile Kullanma
Yapılandırılmış özel durum işleme C ve C++ kaynak dosyalarını içeren works bu makalelerde açıklanan. Ancak, özellikle C++ için tasarlanmamıştır ve önerilmez. C++ özel durum işlemeyi kullanarak kodunuzun daha taşınabilir olduğundan emin olabilirsiniz. Ayrıca, C++ özel durum mekanizması işleme daha esnek ve herhangi bir tür özel durumlar işleyebilir olmamasıdır.  
  
 Microsoft C++ C++ özel durum işleme modeli ANSI C++ Standart göre şimdi destekler. Bu mekanizma yerel nesneleri yok etme yığını geriye doğru izleme sırasında otomatik olarak yönetir. Hataya dayanıklı C++ kodu yazma ve özel durum işleme uygulamak isterseniz, C++ özel durum işleme, yapılandırılmış özel durum işleme yerine kullanmanız önerilir. (C++ derleyicisi yapılandırılmış özel durum şu makalelerinde açıklandığı gibi yapıları işleme desteklerken, standart C Derleyici C++ özel durum söz dizimi işleme desteklemiyor unutmayın.) C++ özel durum işleme hakkında ayrıntılı bilgi için bkz: [C++ özel durum işleme](../cpp/cpp-exception-handling.md) ve *C++ başvuru el ile Açıklama* Mine Ellis ve çalışan Bjarne Stroustrup tarafından.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)