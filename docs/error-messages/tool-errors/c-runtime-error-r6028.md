---
title: C Çalışma Zamanı Hatası R6028
ms.date: 11/04/2016
f1_keywords:
- R6028
helpviewer_keywords:
- R6028
ms.assetid: 81e99079-4388-4244-a4f7-4641c508871c
ms.openlocfilehash: 1c165b7c9351e34ef6316962cd90663f2b6152ab
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80197138"
---
# <a name="c-runtime-error-r6028"></a>C Çalışma Zamanı Hatası R6028

yığın başlatılamıyor

> [!NOTE]
> Bir uygulamayı çalıştırırken bu hata iletisiyle karşılaşırsanız, bir iç bellek sorunu olduğundan uygulama kapatıldı. Bu hatanın birçok olası nedeni vardır, ancak genellikle son derece düşük bellek koşulunun, programdaki bir hatanın veya arızalı donanım sürücüleriyle ilgili olması nedeniyle oluşur.
>
> Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:
>
> - Çalışan diğer uygulamaları kapatın veya belleği boşaltmak için bilgisayarınızı yeniden başlatın.
> - Programı onarmak ya da yeniden yüklemek için **Denetim Masası** 'ndaki **uygulamalar ve Özellikler** veya **Programlar ve Özellikler** sayfasını kullanın.
> - Uygulama, başka bir uygulama veya sürücünün son yüklemesi öncesinde çalışıyorsa, yeni uygulamayı veya sürücüyü kaldırmak için **Denetim Masası** 'ndaki **uygulamalar ve Özellikler** veya **Programlar ve Özellikler** sayfasını kullanın ve uygulamanızı yeniden deneyin.
> - Yazılım ve sürücü güncelleştirmeleri için **Denetim Masası** 'ndaki Donanım satıcınızın Web sitesini veya **Windows Update** denetleyin.
> - Uygulamanın güncelleştirilmiş bir sürümünü denetleyin. Sorun devam ederse uygulama satıcısına başvurun.

**Programcılar için bilgiler**

Bu hata, işletim sistemi uygulama için bellek havuzunu oluşturamadığında meydana gelir. Özellikle, hata belirten NULL döndüren `HeapCreate`Win32 işlevi adlı C çalışma zamanı (CRT) çağırdı.

Uygulama başlatma sırasında bu hata ortaya çıkarsa, sistem kusurlu sürücülerin yüklü olması sebebiyle yığın isteklerini karşılayamayabilir. Windows Update'e veya güncelleştirilmiş sürücüler için donanım satıcınızın web sitesine bakın.
