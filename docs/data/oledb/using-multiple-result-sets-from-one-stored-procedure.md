---
title: Saklı yordamı bir birden çok sonuç kümesi kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- stored procedures, returning result sets
- multiple result sets
ms.assetid: c450c12c-a76c-4ae4-9675-071a41eeac05
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 70fab2751e216ca90dbe09e31c88f9aa80aa7b90
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49808270"
---
# <a name="using-multiple-result-sets-from-one-stored-procedure"></a>Depolanmış Bir Yordamdan Birden Çok Sonuç Kümesi Kullanma

En saklı yordamlar, birden çok sonuç kümesi döndürür. Saklı bir yordam genellikle bir veya daha çok select deyimi. Tüketici tüm sonuç kümelerindeki işlemek için bu ekleme göz önünde bulundurmanız gerekir.  
  
## <a name="to-handle-multiple-result-sets"></a>Birden çok sonuç kümesini işlemek için  
  
1. Oluşturma bir `CCommand` sınıfıyla `CMultipleResults` şablon bağımsız değişkeni olarak ve genellikle bir dinamik veya el ile erişimci seçtiğiniz erişimcisi. Başka türde bir erişimci kullanırsanız, her satır kümesi için çıkış sütunları belirlemek mümkün olmayabilir.  
  
1. Saklı yordamı zamanki yürütmek ve sütunları bağlayın (bkz [nasıl yaparım veri getirme?](../../data/oledb/fetching-data.md)).  
  
1. Verileri kullanın.  
  
1. Çağrı `GetNextResult` üzerinde `CCommand` sınıfı. Başka bir sonuç satır kümesi kullanılabiliyorsa, `GetNextResult` S_OK döndürür ve el ile erişimci kullanıyorsanız sütunlarınızı yeniden. Varsa `GetNextResult` hata verir kullanılabilir başka hiçbir sonuç kümesi vardır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[Saklı Yordamları Kullanma](../../data/oledb/using-stored-procedures.md)