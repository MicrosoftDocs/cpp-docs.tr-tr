---
title: "Bağlayıcı araçları uyarısı LNK4104 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4104
dev_langs: C++
helpviewer_keywords: LNK4104
ms.assetid: ca6728db-d616-419a-a570-65e8445c6079
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6d049ef8663798236250977e90d12c2971dec443
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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