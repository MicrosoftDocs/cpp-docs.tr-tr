---
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
ms.openlocfilehash: 874866627099eb5aeb318273db26a976e99bac7f
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439873"
---
# <a name="extracting-a-library-member"></a>Kitaplık Üyesini Ayıklama

Var olan bir kitaplığın bir üyesinin kopyasını içeren bir nesne (. obj) dosyası oluşturmak için LIB 'i kullanabilirsiniz. Üyenin bir kopyasını ayıklamak için aşağıdaki sözdizimini kullanın:

```
LIB library /EXTRACT:member /OUT:objectfile
```

Bu komut, bir *kitaplığın*`member` kopyasını içeren *objectfile* adlı bir. obj dosyası oluşturur. `member` adı büyük/küçük harfe duyarlıdır. Tek bir komutta yalnızca bir üye ayıklayabilirsiniz. /OUT seçeneği gereklidir; Varsayılan çıkış adı yoktur. Belirtilen dizinde (veya *objectfile*ile dizin belirtilmemişse) *objectfile* adlı bir dosya zaten varsa ayıklanan *objectfile* , var olan dosyanın yerini alır.

## <a name="see-also"></a>Ayrıca bkz.

[LIB Başvurusu](lib-reference.md)
