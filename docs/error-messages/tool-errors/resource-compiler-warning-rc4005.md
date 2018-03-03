---
title: "Kaynak Derleyicisi uyarısı RC4005 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RC4005
dev_langs:
- C++
helpviewer_keywords:
- RC4005
ms.assetid: 71f03b4a-c9a9-415d-920f-bf2e58507f93
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8f27de973f0ff18493c182bdf1feb3f2812f39af
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-warning-rc4005"></a>Kaynak Derleyicisi Uyarısı RC4005
'tanımlayıcısı': makrosu yeniden tanımlama  
  
 Tanımlayıcı iki kez tanımlandı. Derleyici ikinci bir makro tanımı kullanılır.  
  
 Bu uyarı, komut satırında ve koduyla makro tanımlayarak kaynaklanabilir bir `#define` yönergesi. INCLUDE dosyalarından içeri makroları tarafından da oluşabilir.  
  
 Uyarı ortadan kaldırmak için tanımları birini kaldırın veya kullanmak bir `#undef` ikinci tanımı önce yönergesi.