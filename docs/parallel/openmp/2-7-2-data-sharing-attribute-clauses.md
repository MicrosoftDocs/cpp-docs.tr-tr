---
title: 2.7.2 Veri Paylaşım Öznitelik Yan Tümceleri
ms.date: 11/04/2016
ms.assetid: 47347d3c-18bd-441f-99cf-7737564c417f
ms.openlocfilehash: 4c9209a4d627c6212087b621b223a3fb81b48ce3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50559659"
---
# <a name="272-data-sharing-attribute-clauses"></a>2.7.2 Veri Paylaşım Öznitelik Yan Tümceleri

Birkaç yönergeleri bölge süresi boyunca değişkenlerin paylaşım öznitelikleri kontrol etmesine yan tümceleri kabul edin. Paylaşım öznitelik yan tümceleri yalnızca yan tümcesi görünen yönerge sözcük kapsamını değişkenlerde geçerlidir. Aşağıdaki yan tümceleri tüm tüm yönergeler verilir. Belirli bir yönergesinde geçersiz bir yan tümce listesi yönergesiyle açıklanmıştır.

Bir değişken bir paralel olduğunda görünür veya iş paylaşımı yapısı karşılaşıldığında değişkeni bir paylaşım öznitelik yan tümcesinde belirtilen değil ise veya **threadprivate** yönergesi, ardından değişken paylaşılır. Dinamik kapsamını bir paralel bölgenin içinde bildirilen statik değişkenler paylaşılır. Yığın bellek ayrılmış (örneğin, kullanarak **malloc()** C veya C++ veya **yeni** c++ işleci) paylaşılır. (Bu bellek işaretçisi ancak, özel veya paylaşılan olabilir.) Dinamik kapsamını bir paralel bölgenin içinde bildirilen otomatik depolama süresine sahip değişkenleri özeldir.

Yan tümceleri çoğunu kabul bir *değişken listesi* bağımsız değişken görülebilir değişkenlerin virgülle ayrılmış listesidir. Bir değişken başvurulan bir şablondan türetilmiş bir tür veri paylaşım öznitelik yan tümce içeriyor ve bu değişken programdaki diğer başvuru vardır, tanımsız bir davranıştır.

Yönerge yan tümceleri içinde görüntülenen tüm değişkenleri görünür olmalıdır. Yan tümceleri yinelenen gerektiğinde, ancak birden fazla yan tümcesinde bir değişken her ikisinde de belirtilmesi dışında hiçbir değişken belirtilebilir bir **firstprivate** ve **lastprivate** yan tümcesi.

Aşağıdaki bölümlerde, veri paylaşım öznitelik yan tümceleri açıklanır:

- **özel**, [bölümü 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) sayfasında 25.

- **firstprivate**, [bölümü 2.7.2.2](../../parallel/openmp/2-7-2-2-firstprivate.md) üzerinde 26 sayfası.

- **lastprivate**, [bölümü 2.7.2.3](../../parallel/openmp/2-7-2-3-lastprivate.md) 27 sayfasında.

- **Paylaşılan**, [bölümü 2.7.2.4](../../parallel/openmp/2-7-2-4-shared.md) 27 sayfasında.

- **Varsayılan**, [bölümü 2.7.2.5](../../parallel/openmp/2-7-2-5-default.md) sayfasında 28.

- **azaltma**, [bölümü 2.7.2.6](../../parallel/openmp/2-7-2-6-reduction.md) sayfasında 28.

- **copyin**, [bölümü 2.7.2.7](../../parallel/openmp/2-7-2-7-copyin.md) sayfasında 31.

- **copyprivate**, [bölümü 2.7.2.8](../../parallel/openmp/2-7-2-8-copyprivate.md) sayfasında 32.