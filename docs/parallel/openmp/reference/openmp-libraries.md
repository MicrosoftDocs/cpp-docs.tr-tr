---
title: OpenMP kitaplıkları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
dev_langs:
- C++
ms.assetid: f89abf97-67e3-4327-bc30-43f85b9533a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c9a4ccfefeaeb9446731027db44b849233bfefd6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46391221"
---
# <a name="openmp-libraries"></a>OpenMP Kitaplıkları

Visual c++ OpenMP çalışma zamanı kitaplıklarının oluşturan .lib dosyaları açıklar.

Aşağıdaki kitaplıklar, Visual C++ OpenMP çalışma zamanı kitaplık işlevleri içerir.

|OpenMP çalışma zamanı kitaplığı|Özellikler|
|------------------------------|---------------------|
|VCOMP. LIB|Çok iş parçacıklı ve dinamik bağlantı (VCOMP için içeri aktarma kitaplığı. LIB).|
|VCOMPD. LIB|Çok iş parçacıklı ve dinamik bağlantı (VCOMPD için içeri aktarma kitaplığı. Kapak) (hata ayıklama)|

_DEBUG, bir derlemede tanımlı değilse ve `#include omp.h` VCOMPD, kaynak kodu verilmiştir. Varsayılan lib, LIB olacaktır. Aksi takdirde, VCOMP. LIB kullanılır.

Kullanabileceğiniz [/nodefaultlıb (kitaplıkları yoksay)](../../../build/reference/nodefaultlib-ignore-libraries.md) varsayılan LIB kaldırıp dilediğiniz lib ile açıkça bir bağlantı.

OpenMP DLL'leri Visual C++ yeniden dağıtılabilir dizinde bulunan ve OpenMP kullanan uygulamalar ile dağıtılması gerekir.

## <a name="see-also"></a>Ayrıca Bkz.

[Kitaplık Başvurusu](../../../parallel/openmp/reference/openmp-library-reference.md)