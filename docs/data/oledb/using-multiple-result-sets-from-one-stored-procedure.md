---
title: Depolanmış Bir Yordamdan Birden Çok Sonuç Kümesi Kullanma
ms.date: 10/24/2018
helpviewer_keywords:
- stored procedures, returning result sets
- multiple result sets
ms.assetid: c450c12c-a76c-4ae4-9675-071a41eeac05
ms.openlocfilehash: 69e5c956d897e217501cbac9b9b93db868731221
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403054"
---
# <a name="using-multiple-result-sets-from-one-stored-procedure"></a>Depolanmış Bir Yordamdan Birden Çok Sonuç Kümesi Kullanma

En saklı yordamlar, birden çok sonuç kümesi döndürür. Saklı bir yordam genellikle bir veya daha çok select deyimi. Tüketici tüm sonuç kümelerindeki işlemek için bu ekleme göz önünde bulundurmanız gerekir.

## <a name="to-handle-multiple-result-sets"></a>Birden çok sonuç kümesini işlemek için

1. Oluşturma bir `CCommand` sınıfıyla `CMultipleResults` şablon bağımsız değişkeni olarak ve genellikle bir dinamik veya el ile erişimci seçtiğiniz erişimcisi. Başka türde bir erişimci kullanırsanız, her satır kümesi için çıkış sütunları belirlemek mümkün olmayabilir.

1. Saklı yordamı zamanki yürütmek ve sütunları bağlayın (bkz [nasıl yaparım veri getirme?](../../data/oledb/fetching-data.md)).

1. Verileri kullanın.

1. Çağrı `GetNextResult` üzerinde `CCommand` sınıfı. Başka bir sonuç satır kümesi kullanılabiliyorsa, `GetNextResult` S_OK döndürür ve el ile erişimci kullanıyorsanız sütunlarınızı yeniden. Varsa `GetNextResult` hata verir kullanılabilir başka hiçbir sonuç kümesi vardır.

## <a name="see-also"></a>Ayrıca bkz.

[Saklı Yordamları Kullanma](../../data/oledb/using-stored-procedures.md)