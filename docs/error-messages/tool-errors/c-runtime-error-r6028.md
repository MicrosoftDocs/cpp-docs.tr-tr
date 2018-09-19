---
title: C çalışma zamanı hatası R6028 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6028
dev_langs:
- C++
helpviewer_keywords:
- R6028
ms.assetid: 81e99079-4388-4244-a4f7-4641c508871c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5a23fcd6ff7c5fb49e31efab831f1102bc079d91
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093395"
---
# <a name="c-runtime-error-r6028"></a>C çalışma zamanı hatası R6028

yığın başlatılamıyor

> [!NOTE]
>  Bir uygulama çalıştırırken bu hatayla karşılaşırsanız, dahili bellek sorunu olduğundan uygulaması kapatıldı. Bu hata birçok olası nedenleri vardır, ancak bir son derece düşük bellek durumu programında bir hata veya arızalı donanım sürücüleri tarafından genellikle neden olur.
>
>  Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:
>
>  -   Çalışan diğer uygulamaları kapatın veya belleği boşaltmak için bilgisayarınızı yeniden başlatın.
> -   Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasını **Denetim Masası** onarın veya programı yeniden yükleyin.
> -   Uygulamayı başka bir uygulama veya sürücü yeni bir yüklemeden önce çalıştığı kullanırsanız **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasını **Denetim Masası** kaldırmak için Yeni uygulama veya sürücü, uygulamanızı yeniden deneyin.
> -   Donanım satıcınızın Web sitesini denetleyin veya **Windows Update** içinde **Denetim Masası** güncelleştirmeleri, yazılım ve sürücü.
> -   Uygulamanın güncelleştirilmiş bir sürümünü denetleyin. Sorun devam ederse uygulama satıcısına başvurun.

**Programcıları için bilgi**

Bu hata, işletim sistemi uygulama için bellek havuzunu oluşturamadığında meydana gelir. Özellikle, C çalışma zamanı (CRT) Win32 işlevini çağırdı `HeapCreate`, hata olduğunu gösteren NULL döndürdü.

Uygulama başlatma sırasında bu hata ortaya çıkarsa, sistem kusurlu sürücülerin yüklü olması sebebiyle yığın isteklerini karşılayamayabilir. Windows Update'e veya güncelleştirilmiş sürücüler için donanım satıcınızın web sitesine bakın.