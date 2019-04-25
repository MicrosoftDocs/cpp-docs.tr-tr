---
title: Bağlayıcı Araçları Uyarısı LNK4006
ms.date: 11/04/2016
f1_keywords:
- LNK4006
helpviewer_keywords:
- LNK4006
ms.assetid: 3a637d17-1676-4ea6-bd8b-290137d28d3b
ms.openlocfilehash: c81c93a6df8c7eef809f243e3dc56164ea548371
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187147"
---
# <a name="linker-tools-warning-lnk4006"></a>Bağlayıcı Araçları Uyarısı LNK4006

nesnesinde zaten tanımlanmış sembol; İkinci tanımlama yoksayıldı

Verilen `symbol`, düzenlenmiş hâli içinde görüntülenen, birden çok kez tanımlanmış. Bu uyarıyla karşılaşıldığında `symbol` iki kez eklenir ancak yalnızca ilk hâli kullanılır.

İki alma libs birleştirmek çalışırsanız, bu uyarı alabilirsiniz.

C çalışma zamanı kitaplığı yeniden, bu iletiyi yoksayabilirsiniz.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümleri kullanarak düzeltmek için

1. Verilen `symbol` ile derleme tarafından oluşturulan bir paket işlevi olabilir [/Gy](../../build/reference/gy-enable-function-level-linking.md). Bu sembol birden fazla dosyasında bulunan ancak derlemeler arasında değiştirildi. İçeren tüm dosyaları derleyin `symbol`.

1. Verilen `symbol` farklı farklı kitaplıklarındaki iki üye nesneleri olarak tanımlanmış olabilir.

1. Mutlak iki kez, her tanımındaki farklı bir değerle tanımlanmış olabilir.

1. Kitaplıklar birleştirilirken hata iletisini aldığında, `symbol` eklenmesini Kitaplığı'nda zaten mevcut.