---
title: Bağlayıcı araçları uyarısı LNK4006 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4006
dev_langs:
- C++
helpviewer_keywords:
- LNK4006
ms.assetid: 3a637d17-1676-4ea6-bd8b-290137d28d3b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c992369d7bb3d9a3571e23c42a64bf936d5ae383
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46017618"
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