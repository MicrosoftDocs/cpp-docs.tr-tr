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
ms.openlocfilehash: c81dd4bccb8b964e6665d95d1599aeb4044a80a9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="project-build-error-prj0030"></a>Proje Derleme Hatası PRJ0030
Makro genişletme hata oluştu. Özyineleme aşıldı 32 düzeyleri için $(makrosu) değerlendirin.  
  
 Bu hata, makrolardaki özyineleme kaynaklanır. Örneğin, ayarlarsanız **Ara dizin** özelliği (bkz [genel özellik sayfası (Proje)](../../ide/general-property-page-project.md)) $(IntDir) için özyineleme sahip olur.  
  
 Bu hatayı gidermek için makroları veya özelliklerini tanımlamak için kullanılan makroları bakımından tanımlamayın.