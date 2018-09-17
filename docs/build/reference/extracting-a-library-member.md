---
title: Kitaplık üyesini ayıklama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- Lib
dev_langs:
- C++
helpviewer_keywords:
- LIB [C++], extracting library members
- EXTRACT library manager option
- libraries, extracting members
- -EXTRACT library manager option
- extracting library members
- /EXTRACT library manager option
ms.assetid: a2c5c2a1-9b7e-489a-a9a4-1dec694e1fc5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9207a77868b3257d09f0d9efe38e4765cb8f4906
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45726524"
---
# <a name="extracting-a-library-member"></a>Kitaplık Üyesini Ayıklama

LIB, var olan bir kitaplık üyesi bir kopyasını içeren bir nesne (.obj) dosyası oluşturmak için kullanabilirsiniz. Üye bir kopyasını ayıklamak için aşağıdaki sözdizimini kullanın:

```
LIB library /EXTRACT:member /OUT:objectfile
```

Bu komut, adı verilen bir .obj dosyası oluşturur. *objectfile* bir kopyasını içeren bir `member` , bir *Kitaplığı*. `member` Adı küçük harfe duyarlıdır. Tek bir komutta yalnızca bir üye ayıklayabilirsiniz. / Out seçeneği gereklidir; Varsayılan çıkış adı yoktur. Bir dosya çağrılırsa *objectfile* belirtilen dizinde zaten var (veya dizin yok belirtilirse geçerli dizin *objectfile*), ayıklanan *objectfile*varolan dosyanın yerini alır.

## <a name="see-also"></a>Ayrıca Bkz.

[LIB Başvurusu](../../build/reference/lib-reference.md)