---
title: C çalışma zamanı hatası R6026 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6026
dev_langs:
- C++
helpviewer_keywords:
- R6026
ms.assetid: 7ea751f8-fc20-46ab-99ef-84c95ca0b6b4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e5b10075912ce4fde65699cf7b2d413c0bdd10f0
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/08/2018
ms.locfileid: "48860803"
---
# <a name="c-runtime-error-r6026"></a>C çalışma zamanı hatası R6026

stdio başlatma için yeterli alan yok

> [!NOTE]
> Bir uygulama çalıştırırken bu hatayla karşılaşırsanız, dahili bellek sorunu olduğundan uygulaması kapatıldı. Bu hatanın birkaç olası nedeni vardır, ancak genellikle bir son derece düşük bellek durumu tarafından neden olur. Ayrıca uygulama bir hata, kullandığı Visual C++ kitaplıklarının Bozulması veya bir sürücü tarafından kaynaklanabilir.
>
> Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:
>
> - Çalışan diğer uygulamaları kapatın veya belleği boşaltmak için bilgisayarınızı yeniden başlatın.
> - Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasını **Denetim Masası** onarın veya programı yeniden yükleyin.
> - Uygulamayı başka bir uygulama veya sürücü yeni bir yüklemeden önce çalıştığı kullanırsanız **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasını **Denetim Masası** kaldırmak için Yeni uygulama veya sürücü, uygulamanızı yeniden deneyin.
> - Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasını **Denetim Masası** onarın veya Microsoft Visual C++ yeniden dağıtılabilir tüm kopyalarını yeniden yükleyin.
> - Denetleme **Windows Update** içinde **Denetim Masası** yazılım güncelleştirmeleri için.
> - Uygulamanın güncelleştirilmiş bir sürümünü denetleyin. Sorun devam ederse uygulama satıcısına başvurun.

**Programcıları için bilgi**

Standart g/ç destek C çalışma zamanı'nı başlatmak için kullanılabilecek yeterli bellek olmadığında bu hata oluşur. Bu hata genellikle uygulama başlatma sırasında oluşur. Uygulamanızı ve sürücüleri ve onu yükleyen DLL'leri başlatma sırasında yığın bozmadığından doğrulayın.