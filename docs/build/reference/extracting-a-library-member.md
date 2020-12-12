---
description: 'Daha fazla bilgi edinin: bir kitaplık üyesini ayıklama'
title: Kitaplık Üyesini Ayıklama
ms.date: 11/04/2016
helpviewer_keywords:
- LIB [C++], extracting library members
- EXTRACT library manager option
- libraries, extracting members
- -EXTRACT library manager option
- extracting library members
- /EXTRACT library manager option
ms.assetid: a2c5c2a1-9b7e-489a-a9a4-1dec694e1fc5
ms.openlocfilehash: 8797db6baa08fc36cf288f5b23d73ff730edd973
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192323"
---
# <a name="extracting-a-library-member"></a>Kitaplık Üyesini Ayıklama

Var olan bir kitaplığın bir üyesinin kopyasını içeren bir nesne (. obj) dosyası oluşturmak için LIB 'i kullanabilirsiniz. Üyenin bir kopyasını ayıklamak için aşağıdaki sözdizimini kullanın:

```
LIB library /EXTRACT:member /OUT:objectfile
```

Bu komut, bir kitaplığın bir kopyasını içeren *objectfile* adlı bir. obj dosyası oluşturur `member` .  `member`Ad büyük/küçük harfe duyarlıdır. Tek bir komutta yalnızca bir üye ayıklayabilirsiniz. /OUT seçeneği gereklidir; Varsayılan çıkış adı yoktur. Belirtilen dizinde (veya *objectfile* ile dizin belirtilmemişse) *objectfile* adlı bir dosya zaten varsa ayıklanan *objectfile* , var olan dosyanın yerini alır.

## <a name="see-also"></a>Ayrıca bkz.

[LıB başvurusu](lib-reference.md)
