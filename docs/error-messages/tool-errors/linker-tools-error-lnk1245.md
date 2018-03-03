---
title: "Bağlayıcı araçları hatası LNK1245 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1245
dev_langs:
- C++
helpviewer_keywords:
- LNK1245
ms.assetid: 179c8165-ffbb-44cd-9f24-5250f29577cc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 142d88489748f30308395d64f3db78178a9b856f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1245"></a>Bağlayıcı Araçları Hatası LNK1245
Geçersiz alt sistemi 'alt sistemi belirtilen;' / SUBSYSTEM WINDOWS, WINDOWSCE veya KONSOL olmalıdır  
  
 [/ CLR](../../build/reference/clr-common-language-runtime-compilation.md) nesne derlemek için kullanılan ve aşağıdaki koşullardan biri doğru:  
  
-   Özel giriş noktası tanımlandı ([/Entry](../../build/reference/entry-entry-point-symbol.md)), bağlayıcı bir alt çıkarılamadı şekilde.  
  
-   Bir değer geçildi [/SUBSYSTEM ](../../build/reference/subsystem-specify-subsystem.md) /CLR nesneleri için geçerli değil bağlayıcı seçeneği.  
  
 Her iki durumlarda, çözümleme /SUBSYSTEM bağlayıcı seçeneği için geçerli bir değer belirtmek içindir.