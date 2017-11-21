---
title: "Proje derleme uyarısı PRJ0041 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: PRJ0041
dev_langs: C++
helpviewer_keywords: PRJ0041
ms.assetid: dc9f4cf9-6bd5-4222-89e8-7802a59bb96b
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e5a9d5fb5350e4ae6b33fc167aae14b1361291e9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="project-build-warning-prj0041"></a>Proje Derleme Uyarısı PRJ0041
Eksik bulunamıyor bağımlılık 'dosya' dosya ' bağımlılığı'. Projenizi hala yapı, ancak bu dosya bulunana kadar güncel görüntülenmeye devam edebilir.  
  
 Bir dosya (kaynak veya.idl/.odl dosyası, örneğin, dosyaladığınız proje sistemi çözümlenemedi bir INCLUDE deyimi.  
  
 Proje sistemi önişlemci deyimleri (örneğin, #if) işlemez olduğundan, soruna neden olan deyim derleme parçası gerçekte olmayabilir.  
  
 Bu uyarıyı çözmek için tüm gereksiz kodda .rc dosyaları silin veya uygun bir ad yer tutucu dosyaları ekleyin.