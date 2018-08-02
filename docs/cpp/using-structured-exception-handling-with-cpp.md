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
ms.openlocfilehash: 363dd00cd5f4e177ea32a109cf5f56a1f3c6cb29
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461731"
---
# <a name="using-structured-exception-handling-with-c"></a>Yapılandırılmış Özel Durum İşlemeyi C++ ile Kullanma
Yapılandırılmış özel durum işleme, hem C hem de C++ kaynak dosyalarını içeren works aşağıdaki makalelerde açıklanan. Ancak, özellikle C++ için tasarlanmamıştır ve önerilmez. C++ özel durum işlemeyi kullanarak kodunuzun daha taşınabilir olduğundan emin olabilirsiniz. Ayrıca, C++ özel durum işleme mekanizmasını daha esnek ve herhangi bir türde özel durumları işleyebilir olmamasıdır.  
  
 Microsoft C++, C++ özel durum işleme modeli, ANSI C++ Standard'ı temel artık desteklemektedir. Bu mekanizma, yerel nesnelerin yok edilmesi yığın bırakma sırasında otomatik olarak işler. Hataya dayanıklı C++ kod yazıyorsanız ve özel durum işleme uygulamak istiyorsanız, C++ özel durum işleme, yapılandırılmış özel durum işleme yerine kullanmanız önerilir. (C++ Derleyici yapılandırılmış özel durum aşağıdaki makalelerde açıklanan yapıları işleme desteklese de, standart C Derleyici C++ özel durum söz dizimi işleme desteklemediğini unutmayın.) C++ özel durum işleme hakkında ayrıntılı bilgi için bkz: [C++ özel durum işleme](../cpp/cpp-exception-handling.md) ve *Annotated C++ Reference Manual* Margaret Ellis ve Bjarne Stroustrup tarafından.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)