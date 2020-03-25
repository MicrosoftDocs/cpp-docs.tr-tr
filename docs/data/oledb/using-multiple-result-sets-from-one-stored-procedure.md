---
title: Depolanmış Bir Yordamdan Birden Çok Sonuç Kümesi Kullanma
ms.date: 10/24/2018
helpviewer_keywords:
- stored procedures, returning result sets
- multiple result sets
ms.assetid: c450c12c-a76c-4ae4-9675-071a41eeac05
ms.openlocfilehash: 6163eb8bf18edfc3d205f1d012de0c64c5570693
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209293"
---
# <a name="using-multiple-result-sets-from-one-stored-procedure"></a>Depolanmış Bir Yordamdan Birden Çok Sonuç Kümesi Kullanma

Çoğu saklı yordam birden çok sonuç kümesi döndürür. Bu tür bir saklı yordam genellikle bir veya daha fazla select deyimi içerir. Tüketici, tüm sonuç kümelerini işlemek için bu dahil etmeyi göz önünde bulundurması gerekir.

## <a name="to-handle-multiple-result-sets"></a>Birden çok sonuç kümesini işlemek için

1. Şablon bağımsız değişkeni olarak `CMultipleResults` ve genellikle dinamik veya el ile bir erişimci olan `CCommand` bir sınıf oluşturun. Başka bir erişimci türü kullanıyorsanız, her satır kümesi için çıkış sütunlarını belirleyemeyebilirsiniz.

1. Saklı yordamı her zamanki gibi yürütün ve sütunları bağlayın (bkz. [verileri nasıl alabilirim?](../../data/oledb/fetching-data.md)).

1. Verileri kullanın.

1. `CCommand` sınıfında `GetNextResult` çağırın. Başka bir sonuç satır kümesi kullanılabiliyorsa, `GetNextResult` S_OK döndürür ve bir el ile erişimci kullanıyorsanız sütunlarınızı yeniden bağlamanız gerekir. `GetNextResult` bir hata döndürürse, kullanılabilir başka sonuç kümesi yoktur.

## <a name="see-also"></a>Ayrıca bkz.

[Saklı Yordamları Kullanma](../../data/oledb/using-stored-procedures.md)
