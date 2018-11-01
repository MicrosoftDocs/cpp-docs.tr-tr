---
title: C çalışma zamanı hatası R6024
ms.date: 11/04/2016
f1_keywords:
- R6024
helpviewer_keywords:
- R6024
ms.assetid: 0fb11c0f-9b81-4cab-81bd-4785742946a5
ms.openlocfilehash: 89b99a93512603eaf2273a6ff3f434f1ad3b3bb8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50497081"
---
# <a name="c-runtime-error-r6024"></a>C çalışma zamanı hatası R6024

_onexit/atexit tablo için yeterli alan yok

> [!NOTE]
> Bir uygulama çalıştırırken bu hatayla karşılaşırsanız, dahili bellek sorunu olduğundan uygulaması kapatıldı. Bu hata genellikle bir son derece düşük bellek durumu veya nadiren de olsa bir programın hata veya tarafından kullandığı Visual C++ kitaplıklarının Bozulması neden olur.
>
> Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:
>
> - Çalışan diğer uygulamaları kapatın veya belleği boşaltmak için bilgisayarınızı yeniden başlatın.
> - Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasını **Denetim Masası** onarın veya programı yeniden yükleyin.
> - Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasını **Denetim Masası** onarın veya Microsoft Visual C++ yeniden dağıtılabilir tüm kopyalarını yeniden yükleyin.
> - Denetleme **Windows Update** içinde **Denetim Masası** yazılım güncelleştirmeleri için.
> - Uygulamanın güncelleştirilmiş bir sürümünü denetleyin. Sorun devam ederse uygulama satıcısına başvurun.

**Programcıları için bilgi**

Kullanılabilir bellek yok olduğundan, bu hata oluştuğunda `_onexit` veya `atexit` işlevi. Bir düşük bellek koşul bu hataya neden olur. Kullanıcı verilerini kaydetme ve temiz bir uygulama gerçekleştirmek yardımcı olmak için uygulama başlatma sırasında önceden ayırma arabelleklerini düşük bellek koşulları çıkmak düşünebilirsiniz.