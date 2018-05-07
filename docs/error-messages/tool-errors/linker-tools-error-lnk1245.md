---
title: Bağlayıcı araçları hatası LNK1245 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1245
dev_langs:
- C++
helpviewer_keywords:
- LNK1245
ms.assetid: 179c8165-ffbb-44cd-9f24-5250f29577cc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 47a1c2e5f7bf66946dcc5816d7a20fd485b59b45
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1245"></a>Bağlayıcı Araçları Hatası LNK1245
Geçersiz alt sistemi 'alt sistemi belirtilen;' / SUBSYSTEM WINDOWS, WINDOWSCE veya KONSOL olmalıdır  
  
 [/ CLR](../../build/reference/clr-common-language-runtime-compilation.md) nesne derlemek için kullanılan ve aşağıdaki koşullardan biri doğru:  
  
-   Özel giriş noktası tanımlandı ([/Entry](../../build/reference/entry-entry-point-symbol.md)), bağlayıcı bir alt çıkarılamadı şekilde.  
  
-   Bir değer geçildi [/SUBSYSTEM ](../../build/reference/subsystem-specify-subsystem.md) /CLR nesneleri için geçerli değil bağlayıcı seçeneği.  
  
 Her iki durumlarda, çözümleme /SUBSYSTEM bağlayıcı seçeneği için geçerli bir değer belirtmek içindir.