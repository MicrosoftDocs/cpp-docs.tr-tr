---
title: C çalışma zamanı hatası R6024 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6024
dev_langs:
- C++
helpviewer_keywords:
- R6024
ms.assetid: 0fb11c0f-9b81-4cab-81bd-4785742946a5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 10b258b12bb1ad7e47a7b126b8fd503814186645
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46041603"
---
# <a name="c-runtime-error-r6024"></a>C çalışma zamanı hatası R6024

_onexit/atexit tablo için yeterli alan yok

> [!NOTE]
>  Bir uygulama çalıştırırken bu hatayla karşılaşırsanız, dahili bellek sorunu olduğundan uygulaması kapatıldı. Bu hata genellikle bir son derece düşük bellek durumu veya nadiren de olsa bir programın hata veya tarafından kullandığı Visual C++ kitaplıklarının Bozulması neden olur.
>
>  Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:
>
>  -   Çalışan diğer uygulamaları kapatın veya belleği boşaltmak için bilgisayarınızı yeniden başlatın.
> -   Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasını **Denetim Masası** onarın veya programı yeniden yükleyin.
> -   Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasını **Denetim Masası** onarın veya Microsoft Visual C++ yeniden dağıtılabilir tüm kopyalarını yeniden yükleyin.
> -   Denetleme **Windows Update** içinde **Denetim Masası** yazılım güncelleştirmeleri için.
> -   Uygulamanın güncelleştirilmiş bir sürümünü denetleyin. Sorun devam ederse uygulama satıcısına başvurun.

**Programcıları için bilgi**

Kullanılabilir bellek yok olduğundan, bu hata oluştuğunda `_onexit` veya `atexit` işlevi. Bir düşük bellek koşul bu hataya neden olur. Kullanıcı verilerini kaydetme ve temiz bir uygulama gerçekleştirmek yardımcı olmak için uygulama başlatma sırasında önceden ayırma arabelleklerini düşük bellek koşulları çıkmak düşünebilirsiniz.