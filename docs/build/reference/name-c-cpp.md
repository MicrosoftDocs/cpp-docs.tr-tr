---
title: AD (C/C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- name
dev_langs:
- C++
helpviewer_keywords:
- NAME .def file statement
ms.assetid: 5c9b6bd8-9275-46a5-afba-f17a5936dc26
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bc37a96e50c6cd5bae2cc60661db04f3b92d162b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45715760"
---
# <a name="name-cc"></a>NAME (C/C++)

Ana çıkış dosyası adını belirtir.

```
NAME [application][BASE=address]
```

## <a name="remarks"></a>Açıklamalar

Çıkış dosyası adı belirtmek için eşdeğer bir yöntem, [/OUT](../../build/reference/out-output-file-name.md) bağlayıcı seçeneği ve temel adresi ayarlamak için eşdeğer bir yolu olan [/BASE](../../build/reference/base-base-address.md) bağlayıcı seçeneği. Her ikisi de belirtilirse, / OUT geçersiz kılar, **adı**.

Bir DLL yapılandırdıysanız, adı yalnızca DLL adı etkiler.

## <a name="see-also"></a>Ayrıca Bkz.

[Modül Tanımlama Deyimleri Kuralları](../../build/reference/rules-for-module-definition-statements.md)