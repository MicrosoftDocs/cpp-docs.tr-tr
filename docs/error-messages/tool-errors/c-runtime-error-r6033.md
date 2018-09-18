---
title: C çalışma zamanı hatası R6033 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6033
dev_langs:
- C++
helpviewer_keywords:
- R6033
ms.assetid: f9cffdc9-81bd-4a64-a698-02762cbd82c9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fb107dcd2bd044ad6fb933869319bb7afd5aab72
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46049806"
---
# <a name="c-runtime-error-r6033"></a>C çalışma zamanı hatası R6033

MSIL kodunu yerel kod başlatma sırasında bu derlemedeki kullanmayı dener. Bu, uygulamanızda bir hata gösterir. Bu büyük olasılıkla bir MSIL olarak derlenmiş çağırma sonucu olan (/ clr) yerel bir oluşturucu veya DllMain işlevi.

> [!NOTE]
>  Bir uygulama çalıştırırken bu hatayla karşılaşırsanız, dahili bir sorun olduğundan uygulaması kapatıldı. Bu hata, uygulamada bir hata veya bir hatayı bir eklenti veya kullandığı uzantısında neden olabilir.
>
>  Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:
>
>  -   Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasını **Denetim Masası** onarın veya programı yeniden yükleyin.
> -   Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasını **Denetim Masası** kaldırmak onarın veya tüm eklentileri veya uzantıları yeniden yükleyin.
> -   Denetleme **Windows Update** içinde **Denetim Masası** yazılım güncelleştirmeleri için.
> -   Uygulamanın güncelleştirilmiş bir sürümünü denetleyin. Sorun devam ederse uygulama satıcısına başvurun.

**Programcıları için bilgi**

Bu tanılama MSIL yönergeleri yükleyici kilidi sırasında yürütülen gösterir. Yerel C++/CLR bayrağı kullanılarak derlenmiş ise bu durum oluşabilir. Yalnızca yönetilen kod içeren modülleri/CLR bayrağı kullanın. Daha fazla bilgi için [karışık derlemeleri başlatma](../../dotnet/initialization-of-mixed-assemblies.md).