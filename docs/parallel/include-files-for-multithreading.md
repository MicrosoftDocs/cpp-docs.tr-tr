---
title: Dosyaları dahil çoklu iş parçacığı kullanımı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- threading [C++], include files
- include files, multithreading
- multithreading [C++], include files
ms.assetid: 98d764f9-71f4-4da5-8f3a-8d2d26e96799
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 62b94f4a7a394b78cb7c6f23275709e4aeacc774
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33685807"
---
# <a name="include-files-for-multithreading"></a>Çoklu İş Parçacığı Kullanımı için Dosyaları Ekleme
Standart içerme dosyaları kitaplıklarda uygulanan gibi C çalışma zamanı kitaplığı işlevlerini bildirme. Kullanırsanız [tam iyileştirme](../build/reference/ox-full-optimization.md) (/ Ox) veya [fastcall arama kuralı](../build/reference/gd-gr-gv-gz-calling-convention.md) (/ Gr) derleyici seçeneği varsayar tüm işlevleri çağırma kayıt kullanılarak çağrılmalıdır. Çalışma Zamanı Kitaplığı işlevleri C çağırma kuralı kullanılarak derlendi ve bu işlevlerin doğru dış başvurular oluşturmak için derleyici dosyaları içeren standart bildirimler söyleyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C ve Win32 ile Çoklu İş Parçacığı Kullanımı](../parallel/multithreading-with-c-and-win32.md)