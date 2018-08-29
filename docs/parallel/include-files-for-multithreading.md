---
title: İçerme dosyaları için çoklu iş parçacığı kullanımı | Microsoft Docs
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
ms.openlocfilehash: ec531c2c0eeac14a617a3e0e3b450cf467808165
ms.sourcegitcommit: f7703076b850c717c33d72fb0755fbb2215c5ddc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/28/2018
ms.locfileid: "43130774"
---
# <a name="include-files-for-multithreading"></a>Çoklu İş Parçacığı Kullanımı için Dosyaları Ekleme
Standart içerme dosyaları kitaplıklarda uygulandığı gibi C çalışma zamanı kitaplık işlevleri tanımlayın. Kullanırsanız [tam iyileştirme](../build/reference/ox-full-optimization.md) (/ Ox) veya [fastcall çağırma kuralı](../build/reference/gd-gr-gv-gz-calling-convention.md) (/ Gr) derleyici seçeneği, varsayar tüm işlevler çağırma kaydı kullanılarak çağrılmalıdır. Çalışma zamanı kitaplık işlevleri C çağırma kuralı kullanılarak derlenmiş ve derleyicinin, bu işlevler için doğru dış başvuruları standart içerme dosyaları bildirimlerinde söyleyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[C ve Win32 ile Çoklu İş Parçacığı Kullanımı](multithreading-with-c-and-win32.md)