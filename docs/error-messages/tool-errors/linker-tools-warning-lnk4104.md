---
title: "Bağlayıcı araçları uyarısı LNK4104 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4104
dev_langs:
- C++
helpviewer_keywords:
- LNK4104
ms.assetid: ca6728db-d616-419a-a570-65e8445c6079
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b26286f375f54a20e1d3db534576f692179ade24
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4104"></a>Bağlayıcı Araçları Uyarısı LNK4104
dışarı aktarma simgesi 'simgesi' özel olmalıdır  
  
 `symbol` Şunlardan biri olabilir:  
  
-   `DllCanUnloadNow`  
  
-   `DllGetClassObject`  
  
-   `DllGetClassFactoryFromClassString`  
  
-   `DllGetDocumentation`  
  
-   `DllInitialize`  
  
-   `DllInstall`  
  
-   `DllRegisterServer`  
  
-   `DllRegisterServerEx`  
  
-   `DllRegisterServerExW`  
  
-   `DllUnload`  
  
-   `DllUnregisterServer`  
  
-   `RasCustomDeleteEntryNotify`  
  
-   `RasCustomDial`  
  
-   `RasCustomDialDlg`  
  
-   `RasCustomEntryDlg`  
  
 Bu uyarı bir DLL için içeri aktarma kitaplığı oluştururken yayılan ve yukarıdaki işlevleri biri, özel olarak modül tanım dosyasında belirtmeden verin. Genel olarak, bu işlevler yalnızca OLE tarafından kullanılmak üzere dışarı aktarılır. Kitaplığa yanlış bağlı bir program bunlara çağrı yaptığında içeri aktarma kitaplığı'nda yerleştirme olağan dışı davranış yol açabilir. PRIVATE anahtar sözcüğü hakkında daha fazla bilgi için bkz: [dışarı](../../build/reference/exports.md).