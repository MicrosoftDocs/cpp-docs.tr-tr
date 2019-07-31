---
title: OpenMP Kitaplık Başvurusu
ms.date: 07/30/2019
ms.assetid: a25188c6-edde-43d0-84b5-780e797b08fc
ms.openlocfilehash: c78c2677741714ab48d49a4443ad753369ec4500
ms.sourcegitcommit: 725e86dabe2901175ecc63261c3bf05802dddff4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/31/2019
ms.locfileid: "68682586"
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
|VCOMP. LIB|Çoklu iş parçacıklı, dinamik bağlantı (VCOMP için içeri aktarma kitaplığı). LIB).|
|SANAL BİLGİSAYAR KİMLİĞİ. LIB|Çoklu iş parçacıklı, dinamik bağlantı (VCOMPD için kitaplık içeri aktarma. Kapak) (hata ayıklama)|

_Hata ayıklama bir derlemede tanımlıysa ve `#include omp.h` kaynak kodunda ise, vcompd. LıB varsayılan lib, aksi durumda VCOMP olacaktır. LıB kullanılacak.

Varsayılan LIB 'i kaldırmak için [/nodefaultlib (kitaplıkları Yoksay)](../../../build/reference/nodefaultlib-ignore-libraries.md) kullanabilirsiniz ve seçtiğiniz LIB ile açıkça bağlantı oluşturabilirsiniz.

OpenMP dll 'Leri, Visual C++ yeniden dağıtılabilir dizindir ve OpenMP kullanan uygulamalarla dağıtılmalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)