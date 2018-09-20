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
ms.openlocfilehash: 64ba6ec639151ca659e3bd075f691176ef4edbdd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46422330"
---
# <a name="include-files-for-multithreading"></a>Çoklu İş Parçacığı Kullanımı için Dosyaları Ekleme

Standart içerme dosyaları kitaplıklarda uygulandığı gibi C çalışma zamanı kitaplık işlevleri tanımlayın. Kullanırsanız [tam iyileştirme](../build/reference/ox-full-optimization.md) (/ Ox) veya [fastcall çağırma kuralı](../build/reference/gd-gr-gv-gz-calling-convention.md) (/ Gr) derleyici seçeneği, varsayar tüm işlevler çağırma kaydı kullanılarak çağrılmalıdır. Çalışma zamanı kitaplık işlevleri C çağırma kuralı kullanılarak derlenmiş ve derleyicinin, bu işlevler için doğru dış başvuruları standart içerme dosyaları bildirimlerinde söyleyin.

## <a name="see-also"></a>Ayrıca Bkz.

[C ve Win32 ile Çoklu İş Parçacığı Kullanımı](multithreading-with-c-and-win32.md)