---
title: "Saklı yordamı birinden birden çok sonuç kümesi kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- stored procedures, returning result sets
- multiple result sets
ms.assetid: c450c12c-a76c-4ae4-9675-071a41eeac05
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 787c2123981f894eb4b6ba088cfcef774b6ed6f8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="using-multiple-result-sets-from-one-stored-procedure"></a>Depolanmış Bir Yordamdan Birden Çok Sonuç Kümesi Kullanma
Çoğu depolanmış yordam birden çok sonuç kümesi döndürür. Bir veya daha çok select deyimi bu tür bir saklı yordam genellikle bir içerir. Tüketici tüm sonuç kümelerini işlemek için bunu göz önüne almanız gerekir.  
  
### <a name="to-handle-multiple-result-sets"></a>Birden çok sonuç kümesini işlemek için  
  
1.  Oluşturma bir `CCommand` ile sınıf `CMultipleResults` şablon bağımsız değişken olarak ve tercih ettiğiniz erişimcisi. Genellikle, dinamik ya da el ile erişimci budur. Başka bir tür erişimci kullanırsanız, her satır için çıktı sütunlarını belirlemek mümkün olmayabilir.  
  
2.  Saklı yordam her zamanki gibi yürütün ve sütunları bağlayın (bkz [nasıl yedeklerim Fetch Data?](../../data/oledb/fetching-data.md)).  
  
3.  Verileri kullanın.  
  
4.  Çağrı `GetNextResult` üzerinde `CCommand` sınıfı. Başka bir sonuç satır kümesi olup olmadığını `GetNextResult` S_OK verir ve el ile erişimci kullanıyorsanız, sütunları yeniden bağlamanız. Varsa `GetNextResult` bir hata döndürür bulunmaktadır başka sonuç kümesi kullanılabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Saklı yordamları kullanma](../../data/oledb/using-stored-procedures.md)