---
title: Bağlayıcı Araçları Uyarısı LNK4222
ms.date: 11/04/2016
f1_keywords:
- LNK4222
helpviewer_keywords:
- LNK4222
ms.assetid: b7bb1794-41fb-4c83-b9b0-59c0d786a7da
ms.openlocfilehash: 52a4fee532eb9997dcf013f95246b27fdffc4c20
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50563104"
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