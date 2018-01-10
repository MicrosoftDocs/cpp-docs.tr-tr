---
title: "Yapılandırılmış özel durum işlemeyi C++ ile kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- C++ exception handling, mixed with SEH
- structured exception handling [C++], with C++ exception handling
ms.assetid: ec34b528-8c26-4429-b24a-6a68553aaa91
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: db5d067a391512d56a2d01ce3052ac3fab061f28
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="using-structured-exception-handling-with-c"></a>Yapılandırılmış Özel Durum İşlemeyi C++ ile Kullanma
Yapılandırılmış özel durum işleme C ve C++ kaynak dosyalarını içeren works bu makalelerde açıklanan. Ancak, özellikle C++ için tasarlanmamıştır ve önerilmez. C++ özel durum işlemeyi kullanarak kodunuzun daha taşınabilir olduğundan emin olabilirsiniz. Ayrıca, C++ özel durum mekanizması işleme daha esnek ve herhangi bir tür özel durumlar işleyebilir olmamasıdır.  
  
 Microsoft C++ C++ özel durum işleme modeli ANSI C++ Standart göre şimdi destekler. Bu mekanizma yerel nesneleri yok etme yığını geriye doğru izleme sırasında otomatik olarak yönetir. Hataya dayanıklı C++ kodu yazma ve özel durum işleme uygulamak isterseniz, C++ özel durum işleme, yapılandırılmış özel durum işleme yerine kullanmanız önerilir. (C++ derleyicisi yapılandırılmış özel durum şu makalelerinde açıklandığı gibi yapıları işleme desteklerken, standart C Derleyici C++ özel durum söz dizimi işleme desteklemiyor unutmayın.) C++ özel durum işleme hakkında ayrıntılı bilgi için bkz: [C++ özel durum işleme](../cpp/cpp-exception-handling.md) ve *C++ başvuru el ile Açıklama* Mine Ellis ve çalışan Bjarne Stroustrup tarafından.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)