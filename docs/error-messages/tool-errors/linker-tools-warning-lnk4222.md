---
title: Bağlayıcı araçları uyarısı LNK4222 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4222
dev_langs:
- C++
helpviewer_keywords:
- LNK4222
ms.assetid: b7bb1794-41fb-4c83-b9b0-59c0d786a7da
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: abc4f85fbc361b37d9325f9d395a1c34e1eeed2e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106948"
---
# <a name="linker-tools-warning-lnk4222"></a>Bağlayıcı Araçları Uyarısı LNK4222

dışarı aktarılan Sembol 'symbol' sembolüne sıra atanmamalıdır

Aşağıdaki simgeleri sıra tarafından verilebilir:

- `DllCanUnloadNow`

- `DllGetClassObject`

- `DllGetClassFactoryFromClassString`

- `DllInstall`

- `DllRegisterServer`

- `DllRegisterServerEx`

- `DllUnregisterServer`

Bu işlevlerin her zaman adıyla bulunan kullanarak `GetProcAddress`. Bağlayıcı bu konuda uyaran daha büyük bir görüntüde neden olabileceğinden dışarı aktarma türüdür. Bu durum, sıralı dışarı aktarmalar aralığını nispeten daha az sayıda dışarı aktarma ile büyük olması durumunda gerçekleşebilir. Örneğin,

```
EXPORTS
   DllGetClassObject   @1
   MyOtherAPI      @100
```

100 ile bunların 98 dışa aktarma adres tablosunda (2-99) yalnızca filler yuvası gerektirir. Diğer yandan

```
EXPORTS
   DllGetClassObject
   MyOtherAPI      @100
```

iki yuvası gerektirir. (Ayrıca ile aktarabilirsiniz olduğunu unutmayın [/dışarı aktarma](../../build/reference/export-exports-a-function.md) bağlayıcı seçeneği.)