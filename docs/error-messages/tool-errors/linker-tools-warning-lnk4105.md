---
title: Bağlayıcı araçları uyarısı LNK4105 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4105
dev_langs:
- C++
helpviewer_keywords:
- LNK4105
ms.assetid: 6c7bebf4-4ea6-4533-a6ed-e563d43abbd7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4411421741cf8bf7c714a6322d58bd177e7e7270
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46024989"
---
# <a name="linker-tools-warning-lnk4105"></a>Bağlayıcı Araçları Uyarısı LNK4105

'seçeneği'; seçeneği ile belirtilen hiçbir bağımsız değişken seçeneği yoksayılıyor

Bu uyarı yalnızca oluşur, [/Libpath](../../build/reference/libpath-additional-libpath.md) seçeneği ayarlanır. Bu seçeneği ile hiçbir dizin belirtilirse, bağlayıcı seçeneğini yoksayar ve bu uyarı iletisi oluşturur.

Mevcut ortam kitaplık ayarları geçersiz kılmak gerekmiyorsa/Libpath seçenek bağlayıcı komut satırından kaldırın. Alternatif arama yolu kitaplıkları için kullanmak istiyorsanız, / Libpath seçeneği aşağıdaki alternatif yolu belirtin.

## <a name="example"></a>Örnek

```
link /libpath:c:\filepath\lib bar.obj
```

gerekli kitaplıkları aramak için bağlayıcı yönlendirmelisiniz `c:\filepath\lib` varsayılan konumlarda arama önce.