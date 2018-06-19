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
ms.openlocfilehash: 359af4c4d3b1079b2d56f108bff0ee1488ea71f9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302155"
---
# <a name="linker-tools-warning-lnk4222"></a>Bağlayıcı Araçları Uyarısı LNK4222
dışarı aktarılan simgesi 'simgesi' sıra atanmamalıdır  
  
 Aşağıdaki simgeler sıra tarafından verilebilir:  
  
-   `DllCanUnloadNow`  
  
-   `DllGetClassObject`  
  
-   `DllGetClassFactoryFromClassString`  
  
-   `DllInstall`  
  
-   `DllRegisterServer`  
  
-   `DllRegisterServerEx`  
  
-   `DllUnregisterServer`  
  
 Bu işlevlerin her zaman adıyla bulunan kullanarak `GetProcAddress`. Bağlayıcı bu hakkında sizi uyarır verme türüdür daha büyük bir resim neden. Sıralı dışarı aralığını nispeten az dışarı aktarma ile büyük olduğunda bu durum oluşabilir. Örneğin,  
  
```  
EXPORTS  
   DllGetClassObject   @1  
   MyOtherAPI      @100  
```  
  
 (2-99) yalnızca dolgu bunların 98 dışa aktarma adres tablosundaki 100 yuvası gerektirir. Gel gelelim  
  
```  
EXPORTS  
   DllGetClassObject  
   MyOtherAPI      @100  
```  
  
 iki yuvası gerektirir. (Ayrıca ile dışa aktarabilirsiniz olduğunu unutmayın [/dışarı aktarma](../../build/reference/export-exports-a-function.md) bağlayıcı seçeneği.)