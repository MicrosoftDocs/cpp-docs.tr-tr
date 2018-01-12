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
ms.workload: cplusplus
ms.openlocfilehash: 231b58cb0c13d1a3f87e010a5100da564b0be806
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-warning-prj0041"></a>Proje Derleme Uyarısı PRJ0041
Eksik bulunamıyor bağımlılık 'dosya' dosya ' bağımlılığı'. Projenizi hala yapı, ancak bu dosya bulunana kadar güncel görüntülenmeye devam edebilir.  
  
 Bir dosya (kaynak veya.idl/.odl dosyası, örneğin, dosyaladığınız proje sistemi çözümlenemedi bir INCLUDE deyimi.  
  
 Proje sistemi önişlemci deyimleri (örneğin, #if) işlemez olduğundan, soruna neden olan deyim derleme parçası gerçekte olmayabilir.  
  
 Bu uyarıyı çözmek için tüm gereksiz kodda .rc dosyaları silin veya uygun bir ad yer tutucu dosyaları ekleyin.