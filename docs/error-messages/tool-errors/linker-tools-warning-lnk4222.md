---
title: Bağlayıcı Araçları Uyarısı LNK4222
ms.date: 11/04/2016
f1_keywords:
- LNK4222
helpviewer_keywords:
- LNK4222
ms.assetid: b7bb1794-41fb-4c83-b9b0-59c0d786a7da
ms.openlocfilehash: f74379861ad04142fd78a8e307af165072c9cadd
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80183039"
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

Bu işlevler `GetProcAddress`kullanılarak her zaman ada göre bulunur. Bağlayıcı, bu tür bir dışarı aktarma hakkında sizi uyarır çünkü daha büyük bir görüntüyle sonuçlanabilir. Bu durum, sıra dışarı aktarmaların aralığı nispeten daha az dışarı aktarma ile büyükse meydana gelebilir. Örneğin,

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
