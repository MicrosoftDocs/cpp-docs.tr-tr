---
title: STUB
ms.date: 11/04/2016
f1_keywords:
- STUB
helpviewer_keywords:
- STUB .def file statement
ms.assetid: 0a3b9643-19ed-47e9-8173-ee16bc8ed056
ms.openlocfilehash: 95f8e1584bdd87f23e87c27418c0debca5c3181a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50533724"
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