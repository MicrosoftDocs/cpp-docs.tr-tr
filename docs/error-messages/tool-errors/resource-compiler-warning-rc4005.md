---
title: Kaynak Derleyicisi uyarısı RC4005 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC4005
dev_langs:
- C++
helpviewer_keywords:
- RC4005
ms.assetid: 71f03b4a-c9a9-415d-920f-bf2e58507f93
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 724764e443d4ab999c1df1247e9f5572ebdb2078
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33322490"
---
# <a name="resource-compiler-warning-rc4005"></a>Kaynak Derleyicisi Uyarısı RC4005
'tanımlayıcısı': makrosu yeniden tanımlama  
  
 Tanımlayıcı iki kez tanımlandı. Derleyici ikinci bir makro tanımı kullanılır.  
  
 Bu uyarı, komut satırında ve koduyla makro tanımlayarak kaynaklanabilir bir `#define` yönergesi. INCLUDE dosyalarından içeri makroları tarafından da oluşabilir.  
  
 Uyarı ortadan kaldırmak için tanımları birini kaldırın veya kullanmak bir `#undef` ikinci tanımı önce yönergesi.