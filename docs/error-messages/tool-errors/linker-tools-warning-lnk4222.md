---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları uyarısı LNK4222'
title: Bağlayıcı Araçları Uyarısı LNK4222
ms.date: 11/04/2016
f1_keywords:
- LNK4222
helpviewer_keywords:
- LNK4222
ms.assetid: b7bb1794-41fb-4c83-b9b0-59c0d786a7da
ms.openlocfilehash: 215dd04339b783d558b05140bb7dd08c5936d5e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222614"
---
# <a name="linker-tools-warning-lnk4222"></a>Bağlayıcı Araçları Uyarısı LNK4222

' symbol ' içe aktarılmış simgesine sıra atanmamalıdır

Aşağıdaki semboller sıra sayısına göre aktarılmamalıdır:

- `DllCanUnloadNow`

- `DllGetClassObject`

- `DllGetClassFactoryFromClassString`

- `DllInstall`

- `DllRegisterServer`

- `DllRegisterServerEx`

- `DllUnregisterServer`

Bu işlevler, kullanılarak her zaman adına göre bulunur `GetProcAddress` . Bağlayıcı, bu tür bir dışarı aktarma hakkında sizi uyarır çünkü daha büyük bir görüntüyle sonuçlanabilir. Bu durum, sıra dışarı aktarmaların aralığı nispeten daha az dışarı aktarma ile büyükse meydana gelebilir. Örneğin,

```
EXPORTS
   DllGetClassObject   @1
   MyOtherAPI      @100
```

, dışa aktarma adresi tablosunda 98 (2-99), yalnızca filler ile 100 yuva gerektirir. Gel gelelim

```
EXPORTS
   DllGetClassObject
   MyOtherAPI      @100
```

iki yuva gerekecektir. ( [/Export](../../build/reference/export-exports-a-function.md) bağlayıcı seçeneğiyle de verebilin farkında olun.)
