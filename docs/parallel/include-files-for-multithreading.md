---
title: "Dosyaları dahil çoklu iş parçacığı kullanımı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- threading [C++], include files
- include files, multithreading
- multithreading [C++], include files
ms.assetid: 98d764f9-71f4-4da5-8f3a-8d2d26e96799
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bcc8282680588585335eaa2c876128d2c2cf23a3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="include-files-for-multithreading"></a>Çoklu İş Parçacığı Kullanımı için Dosyaları Ekleme
Standart içerme dosyaları kitaplıklarda uygulanan gibi C çalışma zamanı kitaplığı işlevlerini bildirme. Kullanırsanız [tam iyileştirme](../build/reference/ox-full-optimization.md) (/ Ox) veya [fastcall arama kuralı](../build/reference/gd-gr-gv-gz-calling-convention.md) (/ Gr) derleyici seçeneği varsayar tüm işlevleri çağırma kayıt kullanılarak çağrılmalıdır. Çalışma Zamanı Kitaplığı işlevleri C çağırma kuralı kullanılarak derlendi ve bu işlevlerin doğru dış başvurular oluşturmak için derleyici dosyaları içeren standart bildirimler söyleyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C ve Win32 ile çoklu iş parçacığı kullanımı](../parallel/multithreading-with-c-and-win32.md)