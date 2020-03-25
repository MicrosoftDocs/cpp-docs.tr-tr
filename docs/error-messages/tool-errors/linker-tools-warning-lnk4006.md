---
title: Bağlayıcı Araçları Uyarısı LNK4006
ms.date: 11/04/2016
f1_keywords:
- LNK4006
helpviewer_keywords:
- LNK4006
ms.assetid: 3a637d17-1676-4ea6-bd8b-290137d28d3b
ms.openlocfilehash: d949ba259de8e131f6191e757119b4c42effc3d4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194323"
---
# <a name="linker-tools-warning-lnk4006"></a>Bağlayıcı Araçları Uyarısı LNK4006

sembol nesnede zaten tanımlandı; İkinci tanım yoksayıldı

Kendi kendine düzenlenmiş biçimde görünen verilen `symbol`, çarptıklandı. Bu uyarıyla karşılaşıldığında `symbol` iki kez eklenir, ancak yalnızca ilk formu kullanılacaktır.

İki içeri aktarmayı bir tane ile birleştirmeye çalışırsanız bu uyarıyı alabilirsiniz.

C çalışma zamanı kitaplığını yeniden oluşturuyorsanız bu iletiyi yoksayabilirsiniz.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümleri kullanarak düzeltilmesi için

1. Verilen `symbol`, [/GY](../../build/reference/gy-enable-function-level-linking.md)ile derlenerek oluşturulmuş bir paketlenmiş işlev olabilir. Bu sembol birden fazla dosyaya dahil edildi ancak derlemeler arasında değiştirildi. `symbol`içeren tüm dosyaları yeniden derleyin.

1. Verilen `symbol` farklı kitaplıklarda iki üye nesnesi içinde farklı tanımlanmış olabilir.

1. Mutlak, her tanımda farklı bir değer ile iki kez tanımlanmış olabilir.

1. Kitaplıklar birleştirilirken hata iletisi alınmışsa `symbol`, eklenen kitaplıkta zaten var.
