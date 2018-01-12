---
title: "Bağlayıcı araçları uyarısı LNK4222 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4222
dev_langs: C++
helpviewer_keywords: LNK4222
ms.assetid: b7bb1794-41fb-4c83-b9b0-59c0d786a7da
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2a54c452a5df6f99260d6d01fbf4bb9f2f17b955
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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