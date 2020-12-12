---
description: 'Hakkında daha fazla bilgi edinin: bir saklı yordamdan birden çok sonuç kümesi kullanma'
title: Depolanmış Bir Yordamdan Birden Çok Sonuç Kümesi Kullanma
ms.date: 10/24/2018
helpviewer_keywords:
- stored procedures, returning result sets
- multiple result sets
ms.assetid: c450c12c-a76c-4ae4-9675-071a41eeac05
ms.openlocfilehash: 8e6b7a51635caf9ddfd86dddcad0e2a3f94bb7dd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319124"
---
# <a name="using-multiple-result-sets-from-one-stored-procedure"></a>Depolanmış Bir Yordamdan Birden Çok Sonuç Kümesi Kullanma

Çoğu saklı yordam birden çok sonuç kümesi döndürür. Bu tür bir saklı yordam genellikle bir veya daha fazla select deyimi içerir. Tüketici, tüm sonuç kümelerini işlemek için bu dahil etmeyi göz önünde bulundurması gerekir.

## <a name="to-handle-multiple-result-sets"></a>Birden çok sonuç kümesini işlemek için

1. `CCommand` `CMultipleResults` Şablon bağımsız değişkeni olarak ve tercih ettiğiniz erişimciyle, genellikle dinamik veya el ile bir erişimci olan bir sınıf oluşturun. Başka bir erişimci türü kullanıyorsanız, her satır kümesi için çıkış sütunlarını belirleyemeyebilirsiniz.

1. Saklı yordamı her zamanki gibi yürütün ve sütunları bağlayın (bkz. [verileri nasıl alabilirim?](../../data/oledb/fetching-data.md)).

1. Verileri kullanın.

1. `GetNextResult` `CCommand` Sınıfında çağırın. Başka bir sonuç satır kümesi kullanılabiliyorsa, `GetNextResult` s_ok döndürür ve el ile erişimci kullanıyorsanız sütunlarınızı yeniden bağlamanız gerekir. `GetNextResult`Bir hata döndürürse, kullanılabilir başka sonuç kümesi yoktur.

## <a name="see-also"></a>Ayrıca bkz.

[Saklı yordamları kullanma](../../data/oledb/using-stored-procedures.md)
