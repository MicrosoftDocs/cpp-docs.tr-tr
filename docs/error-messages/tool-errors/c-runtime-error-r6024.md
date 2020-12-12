---
description: 'Daha fazla bilgi edinin: C çalışma zamanı hatası R6024'
title: C Çalışma Zamanı Hatası R6024
ms.date: 11/04/2016
f1_keywords:
- R6024
helpviewer_keywords:
- R6024
ms.assetid: 0fb11c0f-9b81-4cab-81bd-4785742946a5
ms.openlocfilehash: 165592e87eb38ab68c2435cc0a8ca53eb3bc16ba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97237601"
---
# <a name="c-runtime-error-r6024"></a>C Çalışma Zamanı Hatası R6024

_onexit/atexit tablosu için yeterli alan yok

> [!NOTE]
> Bir uygulamayı çalıştırırken bu hata iletisiyle karşılaşırsanız, bir iç bellek sorunu olduğundan uygulama kapatıldı. Bu hata genellikle son derece düşük bellek koşulunun veya nadiren, programdaki bir hata tarafından veya kullandığı Visual C++ kitaplıklarının bozulması nedeniyle oluşur.
>
> Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:
>
> - Çalışan diğer uygulamaları kapatın veya belleği boşaltmak için bilgisayarınızı yeniden başlatın.
> - Programı onarmak ya da yeniden yüklemek için **Denetim Masası** 'ndaki **uygulamalar ve Özellikler** veya **Programlar ve Özellikler** sayfasını kullanın.
> - Yeniden dağıtılabilir Microsoft Visual C++ tüm kopyalarını onarmak ya da yeniden yüklemek için **Denetim Masası** 'ndaki **uygulamalar ve Özellikler** veya **Programlar ve Özellikler** sayfasını kullanın.
> - Yazılım güncelleştirmeleri için **Denetim Masası** 'ndaki **Windows Update** kontrol edin.
> - Uygulamanın güncelleştirilmiş bir sürümünü denetleyin. Sorun devam ederse uygulama satıcısına başvurun.

**Programcılar için bilgiler**

OR işlevi için kullanılabilir bellek olmadığından bu hata oluşur `_onexit` `atexit` . Bu hata, düşük bellek koşulunun oluşmasına neden olur. Kullanıcı verilerini kaydetmeye ve düşük bellek koşullarında temiz bir uygulama çıkışı gerçekleştirmeye yardımcı olması için uygulama başlangıcında arabellekleri önceden ayırmayı düşünebilirsiniz.
