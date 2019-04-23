---
title: OpenMP Kitaplık Başvurusu
ms.date: 03/20/2019
ms.assetid: a25188c6-edde-43d0-84b5-780e797b08fc
ms.openlocfilehash: 6f4bbeca54bff1fc44a3576362edca9c30926d5a
ms.sourcegitcommit: 14b292596bc9b9b883a9c58cd3e366b282a1f7b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60124700"
---
# <a name="openmp-library-reference"></a>OpenMP Kitaplık Başvurusu

OpenMP API çağrısında kullanılan yapıları bağlantılar sağlar.

Visual C++ uygulaması OpenMP standart aşağıdaki yapıları içerir.

|Oluştur|Açıklama|
|---------------|-----------------|
|[Yönergeler](openmp-directives.md)|OpenMP API çağrısında kullanılan yönergelere bağlantılar sağlar.|
|[Yan Tümceler](openmp-directives.md)|Yan tümceleri OpenMP API çağrısında kullanılan bağlantılar sağlar.|
|[İşlevler](openmp-functions.md)|OpenMP API çağrısında kullanılan işlevlere bağlantılar sağlar.|
|[Ortam Değişkenleri](openmp-environment-variables.md)|OpenMP API çağrısında kullanılan ortam değişkenlerini bağlantılar sağlar.|

Görsel C++ OpenMP çalışma zamanı kitaplık işlevleri şu kitaplıklarda bulunur.

|OpenMP çalışma zamanı kitaplığı|Özellikler|
|------------------------------|---------------------|
|VCOMP. LIB|Çok iş parçacıklı ve dinamik bağlantı (VCOMP için içeri aktarma kitaplığı. LIB).|
|VCOMPD.LIB|Çok iş parçacıklı ve dinamik bağlantı (VCOMPD için içeri aktarma kitaplığı. Kapak) (hata ayıklama)|

_DEBUG, bir derlemede tanımlı değilse ve `#include omp.h` VCOMPD, kaynak kodu verilmiştir. LIB varsayılan LIB, aksi takdirde, VCOMP olacaktır. LIB kullanılır.

Kullanabileceğiniz [/nodefaultlıb (kitaplıkları yoksay)](../../../build/reference/nodefaultlib-ignore-libraries.md) varsayılan LIB kaldırıp dilediğiniz lib ile açıkça bir bağlantı.

OpenMP DLL'leri Visual C++ yeniden dağıtılabilir dizinde bulunan ve OpenMP kullanan uygulamalar ile dağıtılması gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)