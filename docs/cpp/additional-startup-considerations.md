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
ms.workload: cplusplus
ms.openlocfilehash: 57b1de8fbbdb3d969dca8e84e57e18b81749d944
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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