---
title: "Önemli hata C1854 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1854
dev_langs: C++
helpviewer_keywords: C1854
ms.assetid: 8c21a9cc-1737-475c-9e57-8725cd8937c1
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d35a3aae8f52f28e8775e09d23355e931420bfee
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="fatal-error-c1854"></a>Önemli hata C1854
  
> önceden derlenmiş üst bilgi nesne dosyasına oluşturulması sırasında oluşturulmuş bilgi üzerine yazılamıyor: '*filename*'  
  
Belirttiğiniz [/Yu (önceden derlenmiş üst bilgi dosyasını kullanma)](../../build/reference/yu-use-precompiled-header-file.md) belirttikten sonra seçeneği [/Yc (önceden derlenmiş üst bilgi dosyası oluştur)](../../build/reference/yc-create-precompiled-header-file.md) seçeneği aynı dosya için.  
  
Bu sorunu gidermek için genel olarak, yalnızca bir dosya kullanarak derlenecek projenizi kümesindeki **/Yc** seçeneği ve kullanarak derlemek için tüm dosyaları ayarlamak **/Yu** seçeneği. Kullanımı hakkında ayrıntılı bilgi için **/Yc** seçeneği ve Visual Studio IDE içinde ayarlama nasıl [/Yc (önceden derlenmiş üst bilgi dosyası oluştur)](../../build/reference/yc-create-precompiled-header-file.md). Önceden derlenmiş başlıkları kullanma ile ilgili daha fazla bilgi için bkz: [önceden derlenmiş üst bilgi dosyaları oluşturma](../../build/reference/creating-precompiled-header-files.md).  
