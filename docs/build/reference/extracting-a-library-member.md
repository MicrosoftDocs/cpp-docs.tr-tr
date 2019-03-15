---
title: Kitaplık Üyesini Ayıklama
ms.date: 11/04/2016
f1_keywords:
- Lib
helpviewer_keywords:
- LIB [C++], extracting library members
- EXTRACT library manager option
- libraries, extracting members
- -EXTRACT library manager option
- extracting library members
- /EXTRACT library manager option
ms.assetid: a2c5c2a1-9b7e-489a-a9a4-1dec694e1fc5
ms.openlocfilehash: 6c577300f747d6f546b7caa3c66bddd6a516e16b
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57818069"
---
# <a name="extracting-a-library-member"></a>Kitaplık Üyesini Ayıklama

LIB, var olan bir kitaplık üyesi bir kopyasını içeren bir nesne (.obj) dosyası oluşturmak için kullanabilirsiniz. Üye bir kopyasını ayıklamak için aşağıdaki sözdizimini kullanın:

```
LIB library /EXTRACT:member /OUT:objectfile
```

Bu komut, adı verilen bir .obj dosyası oluşturur. *objectfile* bir kopyasını içeren bir `member` , bir *Kitaplığı*. `member` Adı küçük harfe duyarlıdır. Tek bir komutta yalnızca bir üye ayıklayabilirsiniz. / Out seçeneği gereklidir; Varsayılan çıkış adı yoktur. Bir dosya çağrılırsa *objectfile* belirtilen dizinde zaten var (veya dizin yok belirtilirse geçerli dizin *objectfile*), ayıklanan *objectfile*varolan dosyanın yerini alır.

## <a name="see-also"></a>Ayrıca bkz.

[LIB Başvurusu](lib-reference.md)
