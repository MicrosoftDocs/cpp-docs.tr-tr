---
description: 'Daha fazla bilgi edinin: OpenMP kitaplığı başvurusu'
title: OpenMP Kitaplık Başvurusu
ms.date: 12/02/2019
ms.assetid: a25188c6-edde-43d0-84b5-780e797b08fc
ms.openlocfilehash: fa1f654835afef94b0e00f52bebb0b7300d205be
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342367"
---
# <a name="openmp-library-reference"></a>OpenMP Kitaplık Başvurusu

OpenMP API 'sinde kullanılan yapıların bağlantılarını sağlar.

OpenMP standardının Visual C++ uygulanması aşağıdaki yapıları içerir.

|Oluştur|Açıklama|
|---------------|-----------------|
|[Yönergeler](openmp-directives.md)|OpenMP API 'sinde kullanılan yönergelere bağlantılar sağlar.|
|[Yan tümceler](openmp-clauses.md)|OpenMP API 'sinde kullanılan yan tümceler için bağlantılar sağlar.|
|[İşlevler](openmp-functions.md)|OpenMP API 'sinde kullanılan işlevlere bağlantılar sağlar.|
|[Ortam değişkenleri](openmp-environment-variables.md)|OpenMP API 'sinde kullanılan ortam değişkenlerine bağlantılar sağlar.|

Visual C++ OpenMP çalışma zamanı kitaplığı işlevleri aşağıdaki kitaplıklarda bulunur.

|OpenMP çalışma zamanı kitaplığı|Özellikler|
|------------------------------|---------------------|
|VCOMP. LıB|Çok iş parçacıklı, dinamik bağlantı (VCOMP140.DLL için kitaplığı içeri aktarma).|
|Sanal bilgisayar kimliği. LıB|Çoklu iş parçacıklı, dinamik bağlantı (VCOMP140D.DLL için kitaplığı içeri aktarma) (hata ayıklama)|

_DEBUG derlemede tanımlanırsa ve `#include <omp.h>` kaynak kodunda, VCOMPD. LıB varsayılan lib, aksi durumda VCOMP olacaktır. LıB kullanılacak.

Varsayılan LIB 'i kaldırmak için [/nodefaultlib (kitaplıkları Yoksay)](../../../build/reference/nodefaultlib-ignore-libraries.md) kullanabilirsiniz ve seçtiğiniz LIB ile açıkça bağlantı oluşturabilirsiniz.

OpenMP dll 'Leri Visual C++ yeniden dağıtılabilir dizindir ve OpenMP kullanan uygulamalarla dağıtılması gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)
