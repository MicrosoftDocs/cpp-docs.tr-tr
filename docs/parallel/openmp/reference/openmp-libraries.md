---
title: OpenMP kitaplıkları
ms.date: 10/24/2018
ms.assetid: f89abf97-67e3-4327-bc30-43f85b9533a2
ms.openlocfilehash: 75f772c953a2120a02f72d8bdfc73c1baaaef390
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50530344"
---
# <a name="openmp-libraries"></a>OpenMP kitaplıkları

Visual c++ OpenMP çalışma zamanı kitaplıklarının oluşturan .lib dosyaları açıklar.

Aşağıdaki kitaplıklar, Visual C++ OpenMP çalışma zamanı kitaplık işlevleri içerir.

|OpenMP çalışma zamanı kitaplığı|Özellikler|
|------------------------------|---------------------|
|VCOMP. LIB|Çok iş parçacıklı ve dinamik bağlantı (VCOMP için içeri aktarma kitaplığı. LIB).|
|VCOMPD. LIB|Çok iş parçacıklı ve dinamik bağlantı (VCOMPD için içeri aktarma kitaplığı. Kapak) (hata ayıklama)|

_DEBUG, bir derlemede tanımlı değilse ve `#include omp.h` VCOMPD, kaynak kodu verilmiştir. Varsayılan lib, LIB olacaktır. Aksi takdirde, VCOMP. LIB kullanılır.

Kullanabileceğiniz [/nodefaultlıb (kitaplıkları yoksay)](../../../build/reference/nodefaultlib-ignore-libraries.md) varsayılan LIB kaldırıp dilediğiniz lib ile açıkça bir bağlantı.

OpenMP DLL'leri Visual C++ yeniden dağıtılabilir dizinde bulunan ve OpenMP kullanan uygulamalar ile dağıtılması gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Kitaplık Başvurusu](openmp-library-reference.md)
