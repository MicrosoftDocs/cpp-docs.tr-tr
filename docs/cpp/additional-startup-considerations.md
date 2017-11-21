---
title: "Ek başlatma konuları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- program startup [C++]
- startup code
- initializing before main
ms.assetid: 0e942aa6-8342-447c-b068-8980ed7622bd
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 13471dae28bec066ebe8aeec785a1a060c7f975f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Başlatma ve sonlandırma](../cpp/startup-and-termination-cpp.md)