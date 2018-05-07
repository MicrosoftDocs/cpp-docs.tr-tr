---
title: Proje derleme uyarısı PRJ0041 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0041
dev_langs:
- C++
helpviewer_keywords:
- PRJ0041
ms.assetid: dc9f4cf9-6bd5-4222-89e8-7802a59bb96b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6e845967b0a7116d6edade98b571de5bc1bcd9a1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="project-build-warning-prj0041"></a>Proje Derleme Uyarısı PRJ0041
Eksik bulunamıyor bağımlılık 'dosya' dosya ' bağımlılığı'. Projenizi hala yapı, ancak bu dosya bulunana kadar güncel görüntülenmeye devam edebilir.  
  
 Bir dosya (kaynak veya.idl/.odl dosyası, örneğin, dosyaladığınız proje sistemi çözümlenemedi bir INCLUDE deyimi.  
  
 Proje sistemi önişlemci deyimleri (örneğin, #if) işlemez olduğundan, soruna neden olan deyim derleme parçası gerçekte olmayabilir.  
  
 Bu uyarıyı çözmek için tüm gereksiz kodda .rc dosyaları silin veya uygun bir ad yer tutucu dosyaları ekleyin.