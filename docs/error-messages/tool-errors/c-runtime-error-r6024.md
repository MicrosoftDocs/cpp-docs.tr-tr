---
title: C Çalışma Zamanı Hatası R6024
ms.date: 11/04/2016
f1_keywords:
- R6024
helpviewer_keywords:
- R6024
ms.assetid: 0fb11c0f-9b81-4cab-81bd-4785742946a5
ms.openlocfilehash: de89d2e9e2b34f40b906a5dacca4179eade23f7e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80197203"
---
# <a name="c-runtime-error-r6024"></a>C Çalışma Zamanı Hatası R6024

_onexit/atexit tablosu için yeterli alan yok

> [!NOTE]
> Bir uygulamayı çalıştırırken bu hata iletisiyle karşılaşırsanız, bir iç bellek sorunu olduğundan uygulama kapatıldı. Bu hata genellikle son derece düşük bellek koşulunun veya nadiren, programdaki bir hata veya kullandığı görsel C++ kitaplıkların bozulması nedeniyle oluşur.
>
> Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:
>
> - Çalışan diğer uygulamaları kapatın veya belleği boşaltmak için bilgisayarınızı yeniden başlatın.
> - Programı onarmak ya da yeniden yüklemek için **Denetim Masası** 'ndaki **uygulamalar ve Özellikler** veya **Programlar ve Özellikler** sayfasını kullanın.
> - **Denetim Masası** 'ndaki C++ **uygulamalar ve Özellikler** veya **Programlar ve Özellikler** sayfasını kullanarak Microsoft Visual Redistributable 'ın tüm kopyalarını onarın veya yeniden yükleyin.
> - Yazılım güncelleştirmeleri için **Denetim Masası** 'ndaki **Windows Update** kontrol edin.
> - Uygulamanın güncelleştirilmiş bir sürümünü denetleyin. Sorun devam ederse uygulama satıcısına başvurun.

**Programcılar için bilgiler**

`_onexit` veya `atexit` işlevi için kullanılabilir bellek olmadığından bu hata oluşur. Bu hata, düşük bellek koşulunun oluşmasına neden olur. Kullanıcı verilerini kaydetmeye ve düşük bellek koşullarında temiz bir uygulama çıkışı gerçekleştirmeye yardımcı olması için uygulama başlangıcında arabellekleri önceden ayırmayı düşünebilirsiniz.
