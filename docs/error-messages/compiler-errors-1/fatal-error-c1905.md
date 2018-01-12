---
title: "Önemli hata C1905 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1905
dev_langs: C++
helpviewer_keywords: C1905
ms.assetid: fefc6769-477f-45a2-9878-6f0a5f42472c
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e5ad4a22e73650db98ef1bf1fbd3fff214f5f754
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1905"></a>Önemli hata C1905
Ön uç ve arka uç uyumlu değil (aynı işlemci hedeflemesi gerekir)  
  
 .Obj dosya x86, ARM, gibi bir işlemci hedefleyen bir derleyici ön uç (C1.dll) tarafından oluşturulan bu hata oluşur veya [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], ancak farklı bir işlemci hedefleyen bir arka uç tarafından (C2.dll) okuyun.  
  
 Bu sorunu gidermek için eşleşen ön uç ve arka uç kullandığınızdan emin olun. Visual Studio'da oluşturulan projeleri için varsayılan değer budur. Bu hata, proje dosyası düzenlenmesi ve derleyici araçları için farklı yollar kullanılan ortaya çıkabilir. Yolun derleyici araçları için özellikle ayarlamadıysanız, Visual Studio yüklemenizin bozuk olduğunda bu hata oluşabilir. Örneğin, derleyici .dll dosyaları bir konumdan diğerine kopyaladığınız. Kullanım **programlar ve Özellikler** onarmak veya Visual Studio yeniden yüklemek için Windows Denetim Masası'nda.