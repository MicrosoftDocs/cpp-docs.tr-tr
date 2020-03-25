---
title: Satır İçi Derleme Avantajları
ms.date: 08/30/2018
helpviewer_keywords:
- assembler [C++], advantages
- inline assembly [C++], about inline assembly
- inline assembly [C++], using
ms.assetid: 94364d97-faa7-4bdf-8473-570956986c51
ms.openlocfilehash: 7e634f78eca753487cf122ac95df55828bb64625
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169662"
---
# <a name="advantages-of-inline-assembly"></a>Satır İçi Derleme Avantajları

**Microsoft 'a özgü**

Satır içi derleyici ayrı derleme ve bağlantı adımları gerektirmediğinden, ayrı bir derleyiciden daha kullanışlıdır. Satır içi derleme kodu, kapsam içinde olan herhangi bir C değişkeni veya işlev adını kullanabilir; bu şekilde programınızın C kodu ile tümleştirmek de kolaydır. Derleme kodu C veya C++ deyimleri ile satır içi olarak karışık olabileceğinden, c veya C++' de bir veya imkansız olan görevleri gerçekleştirebilir.

Satır içi derlemenin kullanımları şunları içerir:

- Derleme dilinde işlevler yazılıyor.

- Kodun en iyi duruma getirilmesi-kodun önemli bölümleri.

- Cihaz sürücüleri için doğrudan donanım erişimi yapılıyor.

- "Naked" çağrıları için giriş ve bitiş kodu yazma.

Satır içi derleme özel amaçlı bir araçtır. Bir uygulamanın bağlantı noktasını farklı makinelere göre planlıyorsanız, büyük olasılıkla makineye özgü kodu ayrı bir modüle yerleştirmek isteyeceksiniz. Satır içi derleyici tüm Microsoft Macro Assembler (MASı) makrosunu ve veri yönergelerini desteklemediğinden, bu tür modüller için Masd 'yi kullanmayı daha uygun bulabilirsiniz.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Satır İçi Assembler](../../assembler/inline/inline-assembler.md)<br/>
