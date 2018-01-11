---
title: "Proje derleme hatası PRJ0030 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: PRJ0030
dev_langs: C++
helpviewer_keywords: PRJ0030
ms.assetid: c48b3727-e166-46e7-bcd7-3e5b2ac5c1d4
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b6fe537dd8e6705fd5e30929a2480eb1d9ef9119
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-error-prj0030"></a>Proje Derleme Hatası PRJ0030
Makro genişletme hata oluştu. Özyineleme aşıldı 32 düzeyleri için $(makrosu) değerlendirin.  
  
 Bu hata, makrolardaki özyineleme kaynaklanır. Örneğin, ayarlarsanız **Ara dizin** özelliği (bkz [genel özellik sayfası (Proje)](../../ide/general-property-page-project.md)) $(IntDir) için özyineleme sahip olur.  
  
 Bu hatayı gidermek için makroları veya özelliklerini tanımlamak için kullanılan makroları bakımından tanımlamayın.