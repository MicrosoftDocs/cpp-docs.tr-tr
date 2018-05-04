---
title: Ek başlatma konuları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- program startup [C++]
- startup code
- initializing before main
ms.assetid: 0e942aa6-8342-447c-b068-8980ed7622bd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c05ce0fa1a80de8f5ab8b9335bbab22628f3f158
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="additional-startup-considerations"></a>Ek Başlatma Konuları
C++'da, nesne oluşturma ve yıkma işlemleri için kullanıcı kodunun yürütülmesi gerekebilir. Bu nedenle, hangi başlatmaları girişine önce gerçekleşir anlamak önemlidir **ana** ve hangi Yıkıcılar çıkın sonra çağrılan **ana**. (Yapım ve nesneleri yok etme hakkında ayrıntılı bilgi için bkz: [oluşturucular](../cpp/constructors-cpp.md) ve [Yıkıcılar](../cpp/destructors-cpp.md).)  
  
 Aşağıdaki başlatmaları girişine önce gerçekleşmesi **ana**:  
  
-   Statik verilerin varsayılan olarak sıfıra başlatılması. Açık başlatıcıları olmayan tüm statik veriler, çalışma zamanı başlatması dahil diğer herhangi bir kod yürütülmeden önce sıfır olarak ayarlanır. Yine de statik veri üyelerinin açıkça tanımlanması gerekir.  
  
-   Çeviri biçiminde genel statik nesnelerin başlatılması. Bu girişine önce ya da oluşabilir **ana** veya herhangi bir işlev veya nesnenin çeviri birim nesnesinde ilk kez kullanıyorsanız önce.  
  
 **Microsoft özel**  
  
 Microsoft C++'da, genel statik nesneler girişine önce başlatılmış **ana**.  
  
 **SON Microsoft özel**  
  
 Karşılıklı olarak bağımlı, ancak çeviri birimleri bakımından farklı olan genel statik nesneler yanlış davranışlara neden olabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başlatma ve Sonlandırma](../cpp/startup-and-termination-cpp.md)