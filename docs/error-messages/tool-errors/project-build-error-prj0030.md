---
title: Proje derleme hatası PRJ0030 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0030
dev_langs:
- C++
helpviewer_keywords:
- PRJ0030
ms.assetid: c48b3727-e166-46e7-bcd7-3e5b2ac5c1d4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1bf1c9137f8c4ed0d80955eef38b07ea86204a5c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="project-build-error-prj0030"></a>Proje Derleme Hatası PRJ0030
Makro genişletme hata oluştu. Özyineleme aşıldı 32 düzeyleri için $(makrosu) değerlendirin.  
  
 Bu hata, makrolardaki özyineleme kaynaklanır. Örneğin, ayarlarsanız **Ara dizin** özelliği (bkz [genel özellik sayfası (Proje)](../../ide/general-property-page-project.md)) $(IntDir) için özyineleme sahip olur.  
  
 Bu hatayı gidermek için makroları veya özelliklerini tanımlamak için kullanılan makroları bakımından tanımlamayın.