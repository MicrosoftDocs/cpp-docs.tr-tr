---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları uyarısı LNK4006'
title: Bağlayıcı Araçları Uyarısı LNK4006
ms.date: 11/04/2016
f1_keywords:
- LNK4006
helpviewer_keywords:
- LNK4006
ms.assetid: 3a637d17-1676-4ea6-bd8b-290137d28d3b
ms.openlocfilehash: 526b3f380ef7e05448280094f360c145d7f21c04
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332012"
---
# <a name="linker-tools-warning-lnk4006"></a>Bağlayıcı Araçları Uyarısı LNK4006

sembol nesnede zaten tanımlandı; İkinci tanım yoksayıldı

`symbol`Kendi kendine düzenlenmiş biçimiyle gösterildiği gibi, tanımlanmıştı. Bu uyarıyla karşılaşıldığında, `symbol` iki kez eklenir, ancak yalnızca ilk formu kullanılacaktır.

İki içeri aktarmayı bir tane ile birleştirmeye çalışırsanız bu uyarıyı alabilirsiniz.

C çalışma zamanı kitaplığını yeniden oluşturuyorsanız bu iletiyi yoksayabilirsiniz.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümleri kullanarak düzeltilmesi için

1. Verilen, `symbol` [/GY](../../build/reference/gy-enable-function-level-linking.md)ile derlenerek oluşturulmuş paketlenmiş bir işlev olabilir. Bu sembol birden fazla dosyaya dahil edildi ancak derlemeler arasında değiştirildi. İçeren tüm dosyaları yeniden derleyin `symbol` .

1. Verilen, `symbol` farklı kitaplıklarda iki üye nesnesi içinde farklı tanımlanmış olabilir.

1. Mutlak, her tanımda farklı bir değer ile iki kez tanımlanmış olabilir.

1. Kitaplıklar birleştirilirken hata iletisi alınmışsa, `symbol` eklenen kitaplıkta zaten var.
