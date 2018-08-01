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
ms.openlocfilehash: c23f18a04010ba62d3651344464ff1668b2127d9
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39405077"
---
# <a name="additional-startup-considerations"></a>Ek Başlatma Konuları
C++'da, nesne oluşturma ve yıkma işlemleri için kullanıcı kodunun yürütülmesi gerekebilir. Bu nedenle, girişten önce hangi başlatmalar anlamak önemlidir `main` ve hangi den çıkıştan sonra `main`. (Oluşturulması ve yıkılması nesnelerin hakkında ayrıntılı bilgi için bkz. [oluşturucular](../cpp/constructors-cpp.md) ve [yok ediciler](../cpp/destructors-cpp.md).)  
  
 Aşağıdaki başlatmalar giriş yapılmadan önce gerçekleşmesi `main`:  
  
-   Statik verilerin varsayılan olarak sıfıra başlatılması. Açık başlatıcıları olmayan tüm statik veriler, çalışma zamanı başlatması dahil diğer herhangi bir kod yürütülmeden önce sıfır olarak ayarlanır. Yine de statik veri üyelerinin açıkça tanımlanması gerekir.  
  
-   Çeviri biçiminde genel statik nesnelerin başlatılması. Girişten önce ya da oluşabilir `main` veya herhangi bir işlevin veya nesnenin çeviri biriminde nesnenin ilk kullanımından önce.  
  
 **Microsoft'a özgü**  
  
 Microsoft C++'da genel statik nesneler girişten önce başlatılır `main`.  
  
 **END Microsoft özgü**  
  
 Karşılıklı olarak bağımlı, ancak çeviri birimleri bakımından farklı olan genel statik nesneler yanlış davranışlara neden olabilir.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Başlatma ve Sonlandırma](../cpp/startup-and-termination-cpp.md)