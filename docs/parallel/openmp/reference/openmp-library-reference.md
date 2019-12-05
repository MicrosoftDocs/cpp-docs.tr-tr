---
title: OpenMP Kitaplık Başvurusu
ms.date: 12/02/2019
ms.assetid: a25188c6-edde-43d0-84b5-780e797b08fc
ms.openlocfilehash: b61eb356b782b3cd17557827734a706e0761a2a8
ms.sourcegitcommit: 8762a3f9b5476b4dee03f0ee8064ea606550986e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/04/2019
ms.locfileid: "74810745"
---
# <a name="openmp-library-reference"></a>OpenMP Kitaplık Başvurusu

OpenMP API 'sinde kullanılan yapıların bağlantılarını sağlar.

OpenMP standardının C++ görsel uygulanması aşağıdaki yapıları içerir.

|Oluştur|Açıklama|
|---------------|-----------------|
|[Yönergeler](openmp-directives.md)|OpenMP API 'sinde kullanılan yönergelere bağlantılar sağlar.|
|[Yan Tümceler](openmp-clauses.md)|OpenMP API 'sinde kullanılan yan tümceler için bağlantılar sağlar.|
|[İşlevler](openmp-functions.md)|OpenMP API 'sinde kullanılan işlevlere bağlantılar sağlar.|
|[Ortam Değişkenleri](openmp-environment-variables.md)|OpenMP API 'sinde kullanılan ortam değişkenlerine bağlantılar sağlar.|

Görsel C++ OpenMP çalışma zamanı kitaplığı işlevleri aşağıdaki kitaplıklarda bulunur.

|OpenMP çalışma zamanı kitaplığı|Özellikler|
|------------------------------|---------------------|
|VCOMP. LıB|Çok iş parçacıklı, dinamik bağlantı (VCOMP140 için kitaplığı içeri aktarma. DLL).|
|Sanal bilgisayar kimliği. LıB|Çok iş parçacıklı, dinamik bağlantı (VCOMP140D için kitaplığı içeri aktarma. DLL) (hata ayıklama)|

_DEBUG derlemede tanımlıysa ve `#include <omp.h>` kaynak kodda ise, VCOMPD. LıB varsayılan lib, aksi durumda VCOMP olacaktır. LıB kullanılacak.

Varsayılan LIB 'i kaldırmak için [/nodefaultlib (kitaplıkları Yoksay)](../../../build/reference/nodefaultlib-ignore-libraries.md) kullanabilirsiniz ve seçtiğiniz LIB ile açıkça bağlantı oluşturabilirsiniz.

OpenMP dll 'Leri, Visual C++ yeniden dağıtılabilir dizindir ve OpenMP kullanan uygulamalarla dağıtılmalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)
