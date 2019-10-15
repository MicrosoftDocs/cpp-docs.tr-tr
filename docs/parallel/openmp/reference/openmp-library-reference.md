---
title: OpenMP Kitaplık Başvurusu
ms.date: 07/30/2019
ms.assetid: a25188c6-edde-43d0-84b5-780e797b08fc
ms.openlocfilehash: c63ae5ba7f04d8ee6bd02418792804373fa71e6b
ms.sourcegitcommit: 170f5de63b0fec8e38c252b6afdc08343f4243a6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72348218"
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
|VCOMP. LıB|Çoklu iş parçacıklı, dinamik bağlantı (VCOMP için içeri aktarma kitaplığı). LIB).|
|Sanal bilgisayar kimliği. LıB|Çoklu iş parçacıklı, dinamik bağlantı (VCOMPD için kitaplık içeri aktarma. Kapak) (hata ayıklama)|

_Hata ayıklama bir derlemede tanımlıysa ve `#include <omp.h>` kaynak kodda ise, VCOMPD. LıB varsayılan lib, aksi durumda VCOMP olacaktır. LıB kullanılacak.

Varsayılan LIB 'i kaldırmak için [/nodefaultlib (kitaplıkları Yoksay)](../../../build/reference/nodefaultlib-ignore-libraries.md) kullanabilirsiniz ve seçtiğiniz LIB ile açıkça bağlantı oluşturabilirsiniz.

OpenMP dll 'Leri, Visual C++ yeniden dağıtılabilir dizindir ve OpenMP kullanan uygulamalarla dağıtılmalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)
