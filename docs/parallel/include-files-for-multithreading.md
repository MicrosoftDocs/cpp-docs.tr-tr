---
title: Çoklu İş Parçacığı Kullanımı için Dosyaları Ekleme
ms.date: 11/04/2016
helpviewer_keywords:
- threading [C++], include files
- include files, multithreading
- multithreading [C++], include files
ms.assetid: 98d764f9-71f4-4da5-8f3a-8d2d26e96799
ms.openlocfilehash: cf7a5ff7e42ffbcf57027014411e089722df16fe
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50591938"
---
# <a name="include-files-for-multithreading"></a>Çoklu İş Parçacığı Kullanımı için Dosyaları Ekleme

Standart içerme dosyaları kitaplıklarda uygulandığı gibi C çalışma zamanı kitaplık işlevleri tanımlayın. Kullanırsanız [tam iyileştirme](../build/reference/ox-full-optimization.md) (/ Ox) veya [fastcall çağırma kuralı](../build/reference/gd-gr-gv-gz-calling-convention.md) (/ Gr) derleyici seçeneği, varsayar tüm işlevler çağırma kaydı kullanılarak çağrılmalıdır. Çalışma zamanı kitaplık işlevleri C çağırma kuralı kullanılarak derlenmiş ve derleyicinin, bu işlevler için doğru dış başvuruları standart içerme dosyaları bildirimlerinde söyleyin.

## <a name="see-also"></a>Ayrıca Bkz.

[C ve Win32 ile Çoklu İş Parçacığı Kullanımı](multithreading-with-c-and-win32.md)