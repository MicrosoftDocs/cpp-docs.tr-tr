---
description: 'Daha fazla bilgi edinin: satır Içi derlemenin avantajları'
title: Satır İçi Derleme Avantajları
ms.date: 08/30/2018
helpviewer_keywords:
- assembler [C++], advantages
- inline assembly [C++], about inline assembly
- inline assembly [C++], using
ms.assetid: 94364d97-faa7-4bdf-8473-570956986c51
ms.openlocfilehash: 066824a4ad63641f33712219dd8364b0edf7259b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118075"
---
# <a name="advantages-of-inline-assembly"></a>Satır İçi Derleme Avantajları

**Microsoft'a Özgü**

Satır içi derleyici ayrı derleme ve bağlantı adımları gerektirmediğinden, ayrı bir derleyiciden daha kullanışlıdır. Satır içi derleme kodu, kapsam içinde olan herhangi bir C değişkeni veya işlev adını kullanabilir; bu şekilde programınızın C kodu ile tümleştirmek de kolaydır. Derleme kodu C veya C++ deyimleriyle satır içi karışık olabileceğinden, C veya C++ ' da daha fazla olan veya imkansız olan görevleri gerçekleştirebilir.

Satır içi derlemenin kullanımları şunları içerir:

- Derleme dilinde işlevler yazılıyor.

- Kodun en iyi duruma getirilmesi-kodun önemli bölümleri.

- Cihaz sürücüleri için doğrudan donanım erişimi yapılıyor.

- "Naked" çağrıları için giriş ve bitiş kodu yazma.

Satır içi derleme özel amaçlı bir araçtır. Bir uygulamanın bağlantı noktasını farklı makinelere göre planlıyorsanız, büyük olasılıkla makineye özgü kodu ayrı bir modüle yerleştirmek isteyeceksiniz. Satır içi derleyici tüm Microsoft Macro Assembler (MASı) makrosunu ve veri yönergelerini desteklemediğinden, bu tür modüller için Masd 'yi kullanmayı daha uygun bulabilirsiniz.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Satır içi assembler](../../assembler/inline/inline-assembler.md)<br/>
