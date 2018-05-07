---
title: Önemli hata C1905 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1905
dev_langs:
- C++
helpviewer_keywords:
- C1905
ms.assetid: fefc6769-477f-45a2-9878-6f0a5f42472c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d15bf00432cab6900c252d85cd642c414bdbbb22
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1905"></a>Önemli hata C1905
Ön uç ve arka uç uyumlu değil (aynı işlemci hedeflemesi gerekir)  
  
 .Obj dosya x86, ARM, gibi bir işlemci hedefleyen bir derleyici ön uç (C1.dll) tarafından oluşturulan bu hata oluşur veya [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], ancak farklı bir işlemci hedefleyen bir arka uç tarafından (C2.dll) okuyun.  
  
 Bu sorunu gidermek için eşleşen ön uç ve arka uç kullandığınızdan emin olun. Visual Studio'da oluşturulan projeleri için varsayılan değer budur. Bu hata, proje dosyası düzenlenmesi ve derleyici araçları için farklı yollar kullanılan ortaya çıkabilir. Yolun derleyici araçları için özellikle ayarlamadıysanız, Visual Studio yüklemenizin bozuk olduğunda bu hata oluşabilir. Örneğin, derleyici .dll dosyaları bir konumdan diğerine kopyaladığınız. Kullanım **programlar ve Özellikler** onarmak veya Visual Studio yeniden yüklemek için Windows Denetim Masası'nda.