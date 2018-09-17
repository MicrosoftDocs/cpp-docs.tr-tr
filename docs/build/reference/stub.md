---
title: SAPLAMA | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- STUB
dev_langs:
- C++
helpviewer_keywords:
- STUB .def file statement
ms.assetid: 0a3b9643-19ed-47e9-8173-ee16bc8ed056
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 151d7b425a7f397a05e3a06e9d94489a0c76f899
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725120"
---
# <a name="stub"></a>STUB

Sanal cihaz sürücüsü (VxD) oluşturan bir modül tanım dosyası içinde kullanıldığında (WINNT içinde tanımlanan. bir IMAGE_DOS_HEADER yapı içeren bir dosya adı belirtmenizi sağlar H) sanal cihaz sürücüsü (VxD) yerine varsayılan başlık kullanılacak.

```
STUB:filename
```

## <a name="remarks"></a>Açıklamalar

Belirtmek için bir eşdeğer yol *filename* ile [/SAPLAMA](../../build/reference/stub-ms-dos-stub-file-name.md) bağlayıcı seçeneği.

SAPLAMA modül tanım dosyası içinde yalnızca bir VxD derlerken geçerlidir.

## <a name="see-also"></a>Ayrıca Bkz.

[Modül Tanımlama Deyimleri Kuralları](../../build/reference/rules-for-module-definition-statements.md)