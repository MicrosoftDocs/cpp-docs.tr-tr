---
title: C Çalışma Zamanı Hatası R6028
ms.date: 11/04/2016
f1_keywords:
- R6028
helpviewer_keywords:
- R6028
ms.assetid: 81e99079-4388-4244-a4f7-4641c508871c
ms.openlocfilehash: 4992641c2456f0322b5c52eb907b159904e4c9f0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62380519"
---
# <a name="c-runtime-error-r6028"></a>C Çalışma Zamanı Hatası R6028

yığın başlatılamıyor

> [!NOTE]
> Bir uygulama çalıştırırken bu hatayla karşılaşırsanız, dahili bellek sorunu olduğundan uygulaması kapatıldı. Bu hata birçok olası nedenleri vardır, ancak bir son derece düşük bellek durumu programında bir hata veya arızalı donanım sürücüleri tarafından genellikle neden olur.
>
> Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:
>
> - Çalışan diğer uygulamaları kapatın veya belleği boşaltmak için bilgisayarınızı yeniden başlatın.
> - Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasını **Denetim Masası** onarın veya programı yeniden yükleyin.
> - Uygulamayı başka bir uygulama veya sürücü yeni bir yüklemeden önce çalıştığı kullanırsanız **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasını **Denetim Masası** kaldırmak için Yeni uygulama veya sürücü, uygulamanızı yeniden deneyin.
> - Donanım satıcınızın Web sitesini denetleyin veya **Windows Update** içinde **Denetim Masası** güncelleştirmeleri, yazılım ve sürücü.
> - Uygulamanın güncelleştirilmiş bir sürümünü denetleyin. Sorun devam ederse uygulama satıcısına başvurun.

**Programcıları için bilgi**

Bu hata, işletim sistemi uygulama için bellek havuzunu oluşturamadığında meydana gelir. Özellikle, C çalışma zamanı (CRT) Win32 işlevini çağırdı `HeapCreate`, hata olduğunu gösteren NULL döndürdü.

Uygulama başlatma sırasında bu hata ortaya çıkarsa, sistem kusurlu sürücülerin yüklü olması sebebiyle yığın isteklerini karşılayamayabilir. Windows Update'e veya güncelleştirilmiş sürücüler için donanım satıcınızın web sitesine bakın.